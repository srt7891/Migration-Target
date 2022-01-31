# Modernization specific Definitions & Measurements for DM / WAF

## **DevOps Metrics Definitions**
- **Deployment Frequency** 
  - Average number of days per migration (Calculated on monthly volume migrated)   
**Example:** Given a team is migrating servers to production and migrates 50 servers in a 31 day period, the deployment frequency would be (31/50)=0.62 days per migration.
- **Cycle Time** 
  - Average Elapsed time (in days) between start of assessment to migration complete for every app migrated in the month

- **Failure Rate** 
  - \# of rollback / total migrated per month
- **Time to Restore** 
  - Average Time between the incident and the resolution (Post Migration Support) in a month

---

## **WAF Goals Definitions**

- **Cost** 
  - ACR Projection - Plan vs Actual (5%, 15%, Beyond)
  - Cost Benefit with _Optimization_
    - Calculated based on savings resulting from the optimizations during migration/modernization (Cost difference between migrating solution as-is vs optimized solution) 
- **Operations**
  -  % of deployments with Monitoring - Audit, Diagnostics Settings, Perf counters enabled (optional)
  - % of deployments with Antivirus/Backup/Patching Enabled (optional)
  - % of Migration/Modernization using Automation (optional)
- **Reliability** 
  - \% of UAT defects (P1 and P2) for the month 
  - % migrations with HA/DR (optional)
- **Security** 
  - \# of security center issues reported for the migrations completed in the month
  - \# of security controls missed (across Planning, Migration, UAT) < 1% (optional)
  - \# of issues detected by SAST and DAST tools (optional)
- **Performance** 
  - \# of apps reported with performance issues (Response time/Load time)/total number of apps migrated for the month

---

**Source**:  [Modernization Metrics & Measurements](https://dev.azure.com/VSOGD/ServicesCode-Assets/_wiki/wikis/DevSecOps/4349/Modernization)