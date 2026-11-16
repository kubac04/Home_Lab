# Home Lab

My self-hosted lab for learning monitoring and security, running on VirtualBox VMs.
`mon01` runs Prometheus, Grafana and Loki in Docker, `srv01` is the monitored server.
Metrics are scraped by Prometheus, and system logs are shipped to Loki by Grafana Alloy.
Grafana shows host health and failed SSH logins per source IP.

<p align="center">
  <img src="https://skillicons.dev/icons?i=ubuntu,docker,prometheus,grafana,bash,git" />
  <br/>
  <img src="https://img.shields.io/badge/Loki-F2CC0C?style=for-the-badge&logo=grafana&logoColor=black" />
  <img src="https://img.shields.io/badge/Alloy-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
</p>

_Work in progress — next: alerting to Discord._
