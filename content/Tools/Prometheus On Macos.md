---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - devops
Creation Date: 2024-11-10, 14:50
Last Date: 2024-11-12T13:38:05+08:00
References: 
draft: 
description: 
---
## 1. Install Prometheus
---
- Install [[Prometheus]] with `brew install prometheus`, the default configuration file is located at: `/usr/local/etc/prometheus.yml`
- Start Prometheus: `prometheus --config.file=/usr/local/etc/prometheus.yml`. This command runs Prometheus in the foreground, listening on port `9090`. Visit [http://localhost:9090](http://localhost:9090) in your browser to access the Prometheus Web UI
- Alternatively, start Prometheus as a background service:
	- Start: `brew services start prometheus`
	- Stop: `brew services stop prometheus`

>[!help] What is `brew services`?
> Refer to [[Launchd]] for more details.
## 2. Install Node Exporter
---
- Install Node Exporter with `brew install node_exporter`
- Start Node Exporter as a background service: `brew services start node_exporter`. Node Exporter exposes metrics on port `9100`: `http://localhost:9100/metrics`

### 2.1. Configure Prometheus to Scrape Node Exporter
- Edit your Prometheus configuration file and add the following scrape configuration under `scrape_configs`:

```yaml
scrape_configs:
  - job_name: 'node_exporter'
    static_configs:
      - targets: ['localhost:9100']
```

- Restart Prometheus with `brew services restart prometheus`

## 3. Grafana Visualisation 
---
- Install Grafana with `brew install grafana`
- Start Grafana as a background service: `brew services start grafana`
	- Grafana will be accessible at: [http://localhost:3000](http://localhost:3000)
	- Default login credentials: username - `admin`, password - `admin`
- For more information refers to [here](https://grafana.com/docs/grafana/latest/setup-grafana/installation/mac/)
- Add Prometheus as a data source, using `http://localhost:9090` as the URL
- Import the ["Node Exporter Full" dashboard](https://grafana.com/grafana/dashboards/1860-node-exporter-full/) from Grafana Labs:
