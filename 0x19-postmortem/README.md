# Postmortem Document to Resolve a 500 Error from an Apache Server
[image here](https://jamboard.google.com/d/1YKWlLWB_m6oYsTauHcgwnzPMR9XORE6UIFGj0m0KCow/edit?usp=sharing)

## Summary
This is a hypothetical incident to explore the concept of web debugging and how to write a comprehensive postmortem. 

In this project I presented an incident of a 500 server error which is one of the project I completed as part of my ALX-SE deliverables.
* Duration: The outage occurred from 1:20 am to 2:30 am in WAT.
* Impact: The Apache server experienced a 500 error, resulting in service disruption. Approximately 10% of users were affected.
* Root Cause: The root cause of the issue was after a bad phpp extensions inclusion in the WordPress file wp-settings. 

## Timeline:
1:20 am: The issue was detected through the monitoring tool New Relic, which alerted the on-call team via the on-call management system, PageDuty.
* Actions Taken: The on-call team used strace to attach to the Apache process and analyzed the system calls to identify the root cause.
* Misleading Paths: During the investigation, certain paths were explored that were found to be unrelated to the root cause.
* Escalation: The incident was escalated within the on-call team, and relevant experts were involved.
Resolution: The issue was resolved by updating the Apache configuration using Puppet to address the root cause.

## Root Cause and Resolution:
* Root Cause: The 500 error was caused by a cannot found "/var/www/html/wp-includes/class-wp-locale.php" file. The process was looking for this file, but cannot be found. It says "No such file or directory".
* Resolution: The issue was fixed by updating the Apache configuration to reflect the necessary changes using Puppet.

## Corrective and Preventative Measures:
### Improvements/Fixes: 
Broadly speaking, the following areas can be improved/fixed:
- Regular patching and updates of the server operating system and Apache software.
- Implementing a robust monitoring system to proactively detect and alert on Apache errors and failures.
- Implementing automated configuration management with Puppet to ensure consistent and reliable Apache configurations.

## Task List:
- Upgrade the Ubuntu server from version 14 to the latest supported version.
- Install security updates and patches for both the operating system and Apache.
- Configure a monitoring tool Nagios to track Apache server health and performance metrics.
- Automate the Apache server configuration using Puppet manifests to ensure consistency and ease of management.
- Conduct regular audits and reviews of Apache configurations to identify and address any misconfigurations or vulnerabilities.

See the diagram above to better understand what I have been saying throughout this document

## Author:
NGWERE CLIFORD 
