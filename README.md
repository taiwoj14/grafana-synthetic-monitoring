# Configuring Uptime Monitoring with Grafana Synthetic Monitoring

## 1. Project Overview

This project demonstrates how to configure proactive uptime monitoring using Grafana Cloud Synthetic Monitoring.

Synthetic Monitoring performs automated checks against a target website to verify its availability, response time, and SSL certificate status. It helps identify potential service disruptions before they affect users.

The project uses an HTTP check to monitor Google's homepage from a public probe located in Ohio, USA.

## 2. Project Objectives

- Understand proactive monitoring and synthetic monitoring.
- Configure an HTTP uptime check.
- Validate HTTP response status codes.
- Monitor website availability and response latency.
- Monitor SSL certificate expiration.
- Configure alert rules and email notifications.
- Analyze monitoring metrics through Grafana dashboards.

## 3. Tools and Technologies

- Grafana Cloud
- Grafana Synthetic Monitoring
- Public Synthetic Monitoring Probe
- HTTP
- Grafana Alerting
- Email Contact Point

## 4. Synthetic Monitoring Configuration

The following HTTP check was configured:

| Configuration | Value |
|---|---|
| Check Name | google-homepage-uptime |
| Target URL | https://www.google.com |
| Check Type | HTTP |
| Request Method | GET |
| Valid Status Codes | 2xx |
| Probe Location | Ohio, USA |
| Check Frequency | 5 minutes |
| Timeout | 3 seconds |
| Environment Label | learning |

The check runs automatically every five minutes using a public probe in Ohio.

## 5. HTTP Check Validation

The HTTP check was successfully executed.

The monitoring logs confirmed:

- HTTP response status code: 200
- Check result: Successful
- Probe location: Ohio
- Configured timeout: 3 seconds

The HTTP 200 response confirms that the target website responded successfully during the observed check.

## 6. Monitoring Results

The Grafana dashboard displayed the following results during the observed monitoring period:

| Metric | Observed Result |
|---|---|
| Uptime | 100% |
| Reachability | 100% |
| Average Latency | Approximately 146.54 ms |
| SSL Expiration | Approximately 9.46 weeks |
| Check Frequency | 5 minutes |

These values represent a snapshot of the dashboard during testing and are not a guarantee of continuous future availability.

## 7. Alerting Configuration

Three alert rules were configured:

1. **HTTPRequestDurationTooHighAvg [5m]** – Monitors average HTTP response duration.
2. **ProbeFailedExecutionsTooHigh [5m]** – Monitors failed synthetic check executions.
3. **TLSTargetCertificateCloseToExpiring** – Monitors SSL certificate expiration.

An email contact point was configured, together with a notification policy to route matching alerts to the email contact point.

All three alert rules showed a Normal state during the observed period.

Note: Alert configuration was completed, but an actual alert-triggering test and email delivery verification were not performed.

## 8. Probe Location and Monitoring Frequency

A public probe in Ohio, USA, was selected to simulate external access to the monitored website.

The five-minute monitoring frequency provides regular availability checks while keeping execution usage manageable.

The configured check was estimated to generate approximately 8,928 executions per month.

Only one public probe location was configured. Therefore, the results do not represent availability or latency from all geographic regions.

## 9. Project Screenshots

Screenshots documenting the project configuration and results are available in the `screenshots/` directory.

| Screenshot | Description |
|---|---|
| 01 | Email Contact Point |
| 02 | Notification Policy |
| 03 | All Alert Rules |
| 04 | Failed Checks Alert |
| 05 | TLS Certificate Alert |
| 06 | HTTP Latency Alert |
| 07 | Synthetic Monitoring Check Overview |
| 08 | Successful HTTP Check Execution |
| 09 | Monitoring Performance Overview |

## 10. Project Limitations and Future Improvements

The following enhancements were identified for future learning:

- Configure a private synthetic monitoring probe.
- Add additional public probe locations for geographic comparison.
- Test alert triggering, notification delivery, and recovery.
- Configure Synthetic Monitoring resources using Terraform.
- Explore additional HTTP validation rules, including response body validation.

These enhancements were not included in the current assignment implementation.

## 11. Conclusion

This project provided practical experience configuring Grafana Cloud Synthetic Monitoring for proactive website availability monitoring.

I successfully created an HTTP uptime check, verified successful HTTP responses, monitored uptime, reachability, latency, and SSL expiration, and configured alert rules with an email notification policy.

The project demonstrates the importance of proactive monitoring in identifying potential service availability and performance issues before they affect users.