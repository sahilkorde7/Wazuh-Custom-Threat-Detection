# Custom Threat Detection Rule Using Wazuh and Sysmon

## 1. Objective
To create and test a custom Wazuh detection rule that identifies PowerShell process activity on a Windows system.

## 2. Lab Environment
- **Host OS:** Windows 11
- **Virtual Machine:** Kali Linux
- **SIEM:** Wazuh v4.14.7
- **Log Source:** Microsoft Sysmon
- **Agent:** Wazuh Windows Agent

## 3. Implementation
Sysmon collects Windows process events and the Wazuh Agent forwards them to the Wazuh Manager. A custom rule with ID `100010` was created in `local_rules.xml`.

- **Rule ID:** 100010
- **Alert Level:** 10
- **Detection:** PowerShell process spawned
- **MITRE ATT&CK:** T1059.001 — PowerShell

## 4. Test and Result
A benign PowerShell command, `Get-Date`, was executed to test the detection pipeline. The custom rule successfully generated an alert in `alerts.json`.

## 5. Conclusion
The test confirms that Wazuh can process Sysmon events and trigger a custom detection rule for the configured PowerShell activity.

**Note:** This test validates detection functionality; it does not indicate malicious activity.
