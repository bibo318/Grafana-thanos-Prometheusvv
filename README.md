Bắt đầu và chạy với Thanos, Prometheus, Grafana, Alertmanager, cAdvisor và node_exporter bằng tệp `docker-compose.yaml` trong vòng chưa đầy 5 phút
## Running the example

```bash
git clone https://github.com/bibo318/Grafana-thanos-Prometheusvv
cd quickstart-thanos
docker-compose up -d
```

Các dịch vụ sau sẽ được cài đặt (và một số dịch vụ có thể truy cập qua trình duyệt):

| Component                     | Description                                                               | URL                           |
| -----------------------       | ------------------------------------------------------                    | ----------------------------- |
| prometheus-1                  | Prometheus Server 1 (labels: cluster=chicago, replica=r1)                 | <http://localhost:9081/>      |
| prometheus-2                  | Prometheus Server 2 (labels: cluster=chicago, replica=r2)                 | <http://localhost:9082/>      |
| prometheus-3                  | Prometheus Server 3 (labels: cluster=seattle, replica=r1)                 | <http://localhost:9083/>      |
| prometheus-4                  | Prometheus Server 4 (labels: cluster=seattle, replica=r2)                 | <http://localhost:9084/>      |
| thanos-sidecar-1              | Thanos Sidecar for Prometheus Server 1                                    | không truy cập được qua trình duyệt    |
| thanos-sidecar-2              | Thanos Sidecar for Prometheus Server 2                                    | không truy cập được qua trình duyệt    |
| thanos-sidecar-3              | Thanos Sidecar for Prometheus Server 3                                    | không truy cập được qua trình duyệt    |
| thanos-sidecar-4              | Thanos Sidecar for Prometheus Server 4                                    | không truy cập được qua trình duyệt    |
| thanos-query-frontend         | Thanos Query Frontend                                                     | <http://localhost:10901/>   		  |
| thanos-querier                | Thanos Querier                                                            | <http://localhost:10902/>     |
| thanos-ruler                  | Thanos Ruler                                                              | <http://localhost:10903/>     |
| thanos-bucket-web             | Thanos Bucket Web                                                         | <http://localhost:10904/>     |
| thanos-store-gateway          | Thanos Store Gateway                                                      | không truy cập được qua trình duyệt    |
| thanos-compactor              | Thanos Compactor                                                          | không truy cập được qua trình duyệt    |
| minio                         | Minio - Amazon S3 Compatible Object Storage                               | <http://localhost:9000/>      |
| alertmanager                  | Alertmanager                                                              | <http://localhost:9093/>      |
| grafana                       | Grafana                                                                   | <http://localhost:3000/>      |
| cadvisor                      | cAdvisor                                                                  | <http://localhost:8080/>      |
| node-exporter                 | node_exporter                                                             | <http://localhost:9100/>      |

## Thông tin đăng nhập

Grafana:

```bash
username - admin
password - foobar (Password được lưu trong `/grafana/config monitoring` file env  )
```
  
Minio:

```bash
Access Key - smth
Secret Key - Need8Chars (Keys được lưu trong `docker-compose.yaml` file)
```

## Explore metrics

* Explore metrics via Grafana <http://localhost:3000/explore> hoặc giao diện người dùng truy vấn Thanos <http://localhost:10901>

## Notes

Dự án này nhằm mục đích bắt đầu nhanh chóng chạy với Thanos. Bảo mật không được thực hiện trong dự án này. Nó được truyền cảm hứng bởi:
- <https://github.com/vegasbrianc/prometheus> (Được forked từ dự án này  )
- <https://github.com/alexellis/quickstart-prometheus>

- Các phiên bản trong dự án: prometheus:v2.43.0 | grafana v9.4.7 | cadvisor:v0.36.0 |  alertmanager:v0.25.0 |  node-exporter:v1.5.0 | minio:RELEASE.2020-05-01T22-19-14Z | thanos:v0.31.0



