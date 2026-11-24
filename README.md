# Home Lab

My self-hosted lab for learning network security and monitoring, running on VirtualBox VMs.
An OPNsense firewall routes and filters all traffic between a management network and three 802.1Q VLANs: SERVERS, DMZ and ATTACKER.
`mon01` runs Prometheus, Grafana, Loki and Alloy in Docker. It collects host metrics, system logs from `srv01` and firewall logs from OPNsense over syslog.
Grafana alerts go to Discord: host down, SSH brute force and any traffic from the ATTACKER VLAN towards the management network.
A Kali VM in the ATTACKER VLAN is used to run attacks against the lab and check what the firewall and monitoring actually catch.
Dashboards, alert rules and data sources are provisioned from files in this repo, with secrets kept in `.env`.

![Architecture](docs/architecture.png)

## Screenshots

**Security dashboard** – host status, SSH logins, sudo usage and firewall blocks per zone.

![Security dashboard](docs/dashboard.png)

**OPNsense firewall rules** – default deny between zones, only the traffic each zone needs is allowed.

![Firewall rules](docs/firewall_rules.png)

<p align="center">
  <img src="https://skillicons.dev/icons?i=linux,ubuntu,docker,prometheus,grafana,bash,git" />
  <br/>
  <img src="https://img.shields.io/badge/OPNsense-D94F00?style=for-the-badge&logo=opnsense&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white" />
  <img src="https://img.shields.io/badge/Loki-F2CC0C?style=for-the-badge&logo=grafana&logoColor=black" />
  <img src="https://img.shields.io/badge/Alloy-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" />
</p>