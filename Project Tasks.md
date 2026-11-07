### Planned Security Assessments

The following assessments are planned as part of the lab's ongoing development:

1. **Firewall Security Assessment & Hardening**
   - Audit pfSense firewall rules, NAT configurations, and exposed services.
   - Identify unnecessary access and implement least-privilege restrictions.
   - Validate permitted and denied traffic against expected security policies.

2. **SSH Brute-Force Detection & Incident Investigation**
   - Simulate unauthorized SSH authentication attempts from Kali Linux.
   - Correlate Suricata alerts, pfSense logs, and Ubuntu authentication logs.
   - Investigate attack origin, authentication outcomes, and potential compromise.
   - Implement and validate appropriate remediation measures.

3. **Suricata Detection Engineering & Rule Tuning**
   - Develop custom Suricata signatures for selected network activity.
   - Generate controlled test traffic to evaluate detection accuracy.
   - Analyze alert logs, false positives, and detection gaps.
   - Refine signatures and document validation results.

4. **Network Traffic Analysis & Threat Hunting**
   - Capture network traffic using Wireshark or tcpdump.
   - Investigate simulated reconnaissance, port scanning, and suspicious connections.
   - Analyze packet-level evidence to identify traffic patterns and indicators of compromise.
   - Document findings and investigative conclusions.

5. **Security Control Validation & Regression Testing**
   - Develop repeatable tests for firewall rules, network segmentation, and service accessibility.
   - Verify that security controls enforce intended access restrictions.
   - Reassess configurations after remediation or policy changes.
   - Document expected versus observed results.
