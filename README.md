# Elastic SIEM Lab Project
A practical lab setup for learning and showcasing skills in Security Information and Event Management (SIEM) using Elastic Stack.

## Overview
This project demonstrates:
- Setting up Elastic Cloud for log monitoring and security analysis.
- Configuring Elastic Agent on Kali Linux to forward logs.
- Simulating security events for testing.
- Analyzing logs, creating dashboards, and setting up alerts.

## Setup Instructions
### Prerequisites
- Elastic Cloud account (free trial).
- Kali Linux VM.
- Basic understanding of Linux commands.

### Steps
1. Set up Elastic Cloud deployment.
2. Configure Elastic Agent on Kali Linux.
3. Simulate security events (e.g., Nmap scans, failed SSH attempts).
4. Use Kibana for querying logs, building dashboards, and creating alerts.

## Challenges and Insights
### 1. **Elastic Agent Installation on Kali Linux**
   - **Challenge**: Encountered an infrastructure compatibility issue during the installation of Elastic Agent, as my Kali Linux environment is based on an ARM64 architecture. The Elastic documentation did not address this scenario, and the error messages displayed on the terminal were not descriptive enough to pinpoint the root cause.
   - **Resolution**: Researched in the Elastic forums and identified the issue as an infrastructure mismatch. Downloaded and installed the appropriate Elastic Agent version compatible with ARM64, successfully resolving the problem.

### 2. **Simulating Security Events**
   - **Challenge**: Simulated Nmap scans were not being captured in the logs as expected, likely due to misconfigured logging policies in Elastic Cloud.
   - **Resolution**: Revised the agent policies in Kibana to ensure comprehensive logging of all network activities. Performed additional tests using various Nmap flags to verify that the simulated events were being accurately recorded.

### 3. **Building Dashboards**
   - **Challenge**: Designing meaningful visualizations required a deep understanding of the structure of ingested logs and the indexing of specific fields within Elastic.
   - **Resolution**: Utilized Kibana's Discover feature to analyze the log data and identify key fields such as `source.ip`, `destination.ip`, and `event.action`. This groundwork enabled the creation of dashboards that effectively highlighted suspicious activity and provided actionable insights.

### 4. **Configuring Alerts**
   - **Challenge**: Initial alert rules were overly broad, resulting in numerous false positives that diminished their value.
   - **Resolution**: Refined the alert rules to focus on specific patterns indicative of potential threats, such as multiple failed SSH login attempts from a single IP address within a short time frame. This adjustment significantly reduced noise and improved the relevance of alerts.

### Insights
- **Proactive Troubleshooting**: Systematic testing of each component—network connectivity, log ingestion, and alerting—ensured that issues were identified and resolved early in the process.
- **Incremental Refinement**: Iterative adjustments to configurations and policies led to substantial enhancements in system performance and usability.
- **Practical Expertise**: Addressing these challenges provided hands-on experience with Elastic SIEM, deepening my knowledge of its capabilities and practical applications in detecting and analyzing security incidents.


## Screenshots
### Elastic Agent Setup
![Screenshot 2024-11-15 at 6 14 38 PM](https://github.com/user-attachments/assets/ecb919c8-c7b5-4d6c-b5d1-4722d972f509)

### Kibana Dashboard
![Screenshot 2024-11-15 at 6 05 25 PM](https://github.com/user-attachments/assets/fb8b7da9-93a4-4ad6-8f40-9a4874adbcec)

### Alerts
![Screenshot 2024-11-15 at 6 09 20 PM](https://github.com/user-attachments/assets/79c5177e-f5ec-409b-b3b2-210d3a5169b3)
