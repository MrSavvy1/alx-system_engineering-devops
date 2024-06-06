# Postmortem Report: June 5, 2024 Outage

## Overview

**Duration:** June 5, 2024, 14:00 UTC - 16:30 UTC  
**Impact:** 75% of users experienced timeouts and 500 errors due to web service outage.  
**Root Cause:** Misconfigured database parameter causing resource exhaustion.

## Timeline

- **14:00 UTC:** Issue detected via monitoring alerts.
- **14:05 UTC:** Service confirmed unresponsive.
- **14:10 UTC:** Code deployment rollback initiated.
- **14:30 UTC:** Issue persisted; escalated to database team.
- **14:45 UTC:** Investigation revealed high memory usage.
- **15:00 UTC:** Misleading assumption of traffic spike.
- **15:30 UTC:** Identified misconfigured max connections parameter.
- **15:45 UTC:** Corrected parameter and restarted database.
- **16:00 UTC:** System stability monitored; error rates decreased.
- **16:30 UTC:** Incident resolved; services operational.

## Root Cause and Resolution

**Root Cause:** Misconfigured max connections parameter in the database settings, leading to crashes under regular load.  
**Resolution:** Adjusted the parameter to a suitable value and restarted the database server.

## Corrective and Preventative Measures

1. **Database Configuration Review:** Implement checklist and thorough review of settings.
2. **Enhanced Testing:** Include stress and load testing in staging.
3. **Improved Monitoring:** Increase monitoring of database performance metrics and set up alerts.
4. **Specific Actions:**
   - Patch Nginx server.
   - Add memory usage monitoring.
   - Update configuration documentation.
   - Conduct team training on best practices.

## Conclusion

Failures offer growth opportunities. This outage taught us valuable lessons on configuration management, testing, and monitoring. We are committed to improving our processes to ensure a reliable platform.

---
Sharing our experience fosters a culture of transparency and continuous improvement.

