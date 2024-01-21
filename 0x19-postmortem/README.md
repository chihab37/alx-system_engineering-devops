Postmortem: Web Service Outage
Issue Summary
Duration: The outage lasted for 3 hours, starting at 2:00 PM GMT and ending at 5:00 PM GMT on November 12, 2023.

Impact: During this period, our primary web service was intermittently down, resulting in a complete loss of service for approximately 60% of our users. Users experienced time-outs and server error messages when trying to access our platform.

Root Cause: The root cause was identified as a misconfigured server update that led to memory leaks in our application servers.

Timeline
2:00 PM GMT: Outage began, initially unnoticed.
2:15 PM GMT: Issue detected via monitoring alerts indicating server unresponsiveness.
2:20 PM GMT: Initial assumption was a DDoS attack; network traffic analyzed.
2:45 PM GMT: After ruling out an external attack, focus shifted to internal server issues.
3:00 PM GMT: Issue escalated to the senior infrastructure team.
3:30 PM GMT: Memory leak suspected; servers showed abnormal memory usage.
4:00 PM GMT: Recent server updates reviewed; misconfiguration found in the latest deployment.
4:30 PM GMT: Misconfiguration corrected, servers restarted.
5:00 PM GMT: Service fully restored; monitoring continued for stability.
Root Cause and Resolution
The outage was caused by a memory leak resulting from a misconfigured server update. The update, intended to improve performance, inadvertently altered memory management settings. This caused the servers to consume excessive memory over time, eventually leading to their failure.

To resolve the issue, the team reverted the memory management settings to their pre-update state and restarted all affected servers. This immediately addressed the memory leak, bringing the system back to operational status.

Corrective and Preventative Measures
To prevent similar issues in the future, the following measures are proposed:

Review and Improve Update Procedures: All server updates should undergo a more rigorous review process, including a checklist to verify configuration changes against standard settings.
Enhance Monitoring Systems: Implement more granular monitoring alerts for memory usage anomalies.
Staff Training: Conduct training sessions for the engineering team to better recognize and diagnose issues related to server configurations and memory management.
Post-Deployment Testing: Introduce more comprehensive post-deployment tests to catch any immediate discrepancies or irregularities in server performance.
Documentation Update: Update internal documentation to include guidelines for managing and deploying server updates, emphasizing the importance of configuration management.
Specific Tasks:
Patch Server Software: Ensure all servers are running the latest stable version of their respective software.
Update Monitoring Tools: Upgrade monitoring tools to include alerts for specific memory usage thresholds.
Create a Configuration Checklist: Develop a detailed checklist for server configuration settings to be used during updates.
Schedule Training Sessions: Plan quarterly training for the technical team on server management and emergency response protocols.
Implement a Post-Deployment Review Process: Establish a mandatory review process to be conducted immediately after each deployment.
In conclusion, this incident highlighted the importance of careful configuration management and the need for robust monitoring systems to quickly detect and respond to such issues. The proposed measures aim to enhance our resilience against similar outages in the future.
