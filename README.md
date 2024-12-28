# Infrastructure Monitor System

A comprehensive infrastructure monitoring solution using Prometheus and Grafana.

## Features
- System Resource Monitoring
- Container Metrics
- Performance Tracking
- Alerting and Notifications
- Container security metrics
- System audit logs
- Visualization

## Components
- Prometheus - Metrics collection and storage
- Node Exporter - Host-level metrics
- cAdvisor - Container metrics collection
- Grafana - Visualization and alerting
- AlertManager - Alert handling and routing

## Getting Started

### Prerequisites
- Docker
- Docker Compose

### Installation
1. Clone the repository
2. Run `docker-compose up -d`
3. Access Grafana at `http://localhost:3000`

## Monitoring Architecture
- Prometheus scrapes metrics from various exporters
- Node Exporter provides host-level metrics
- cAdvisor provides container metrics
- Grafana visualizes the collected metrics
- AlertManager handles alerting based on defined rules

## Project Structure
- `config/` - Configuration files
  - `prometheus/` - Prometheus configuration
  - `grafana/` - Grafana dashboard configurations
  - `alertmanager/` - Alert manager configuration

### Grafana Dashboard Provisioning
The System Resources dashboard is automatically provisioned when Grafana starts. The dashboard configuration is stored in:
- `config/grafana/provisioning/dashboards/system_resources.yml` - Dashboard provider configuration
- `config/grafana/provisioning/dashboards/system_resources.json` - Dashboard definition

No manual import is required - the dashboard will be available as soon as Grafana starts.

## Dashboard
The dashboard provides:
- Real-time system metrics monitoring
- Auto-refresh every 5 seconds
- Key metrics:
  - CPU usage
  - Memory utilization
  - Disk usage
  - Network traffic
- Detailed system resource tracking
- Device-specific I/O monitoring
- Smooth line interpolation

## Alert Rules
### System Resource Alerts
- Warning thresholds at 80% utilization for:
  - CPU Usage
  - Memory
  - Disk Space
- Alerts include:
  - Current value
  - Device/instance information
  - Historical context

## Best Practices
- Alert Configuration
   - Start with conservative thresholds
   - Adjust based on your specific infrastructure needs
   - Use multiple notification channels
   - Group related alerts

## Troubleshooting
- Check container logs: `docker-compose logs <service>`
- Verify Prometheus targets: `http://localhost:9090/targets`
- Check Grafana data sources: `http://localhost:3000/datasources`
