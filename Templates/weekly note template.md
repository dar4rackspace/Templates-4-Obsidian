---
date: <% tp.date.now("YYYY-MM-DD") %>
tema: weeklynote
tags:
  - weekly
  - note
year_week: <% tp.date.now("YYYYWW") %>
---

## Time Sheet Tracking

Total working hours for the week: 40 (adjust as needed)

```dataview
TABLE 
EBI_DR_REQUIREMENTS,
EBI_DR_SOFTWARE_DEV,
EBI_POWERBI_TRAINING,
ITS_BI_ADHOC,
ITS_MANAGEMENT_MEETINGS,
ITS_MANAGEMENT_TRAINING,
sum(EBI_DR_REQUIREMENTS + EBI_DR_SOFTWARE_DEV + EBI_POWERBI_TRAINING  + ITS_BI_ADHOC + ITS_MANAGEMENT_MEETINGS + ITS_MANAGEMENT_TRAINING) AS Total 
FROM #daily AND "Notes/Daily" 
WHERE year_week = <% tp.date.now("YYYYWW") %> OR string(year_week) = "<% tp.date.now("YYYYWW") %>"
SORT date
```
## Reminders

- Fill Time Sheet by end of friday
- You could automated with playwright if you wanted but need time on a friday