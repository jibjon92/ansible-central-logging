## 🔍 Architecture Overview

Rather than managing decoupled log endpoints across an enterprise footprint, this automation establishes a standardized logging framework:

* **Log Collector (ServerA):** Opens UDP Port `514`, dynamically creates host-segmented logging vectors at `/var/log/remote/%HOSTNAME%/`, and handles SELinux/Firewalld controls seamlessly.
* **Log Clients (All other nodes):** Provisions automated forwarding pipes (`*.* @<Hub-IP>:514`) targeting the central aggregator.

## 📁 Project Directory Layout
ansible-central-logging/
1. rsyslog_server.yml     # Core automation orchestrator (Hub & Client configurations)
2. inventory.ini          # Environmental node layout mapping target system IPs
3. images/                # Visual validation and architecture blueprints
