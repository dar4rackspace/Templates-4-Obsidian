---
date: <% tp.date.now("YYYY-MM-DD") %>
tema: dailynote
tags:
  - daily
  - note
year_week: <% tp.date.now("YYYYWW") %>
---

[[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY-MM-DD') %>|Yesterday]] | [[<%fileDate = moment(tp.file.title, 'YYYY-MM-DD').add(1, 'd').format('YYYY-MM-DD')%>|Tomorrow]] 

## Tasks of the Day
- [ ]

## Time Sheet Tracking
Use fractions of hours
Split 8 working hours 

```dataview
TABLE
(EBI_POWERBI_TRAINING + EBI_DR_REQUIREMENTS + EBI_DR_SOFTWARE_DEV + ITS_BI_ADHOC + ITS_MANAGEMENT_MEETINGS + ITS_MANAGEMENT_TRAINING) as Total
FROM #daily and "Notes/Daily"
WHERE date = date("{{date:YYYY-MM-DD}}")
```

### Timesheet
#### BI Development
EBI_DR_REQUIREMENTS:: 0
EBI_DR_SOFTWARE_DEV::0
#### BI Training
EBI_POWERBI_TRAINING::0
#### ITS other
ITS_BI_ADHOC::0
ITS_MANAGEMENT_MEETINGS::0
ITS_MANAGEMENT_TRAINING::0

![[Pasted image 20250221131116.png]]



## Follow up on

```dataviewjs
dv.taskList(dv.pages().file.tasks 
  .where(t => !t.completed)
  .where(t => t.text.includes("{{date:YYYY-MM-DD}}")))
```

## Reminders

- buscar implementar pausa activa every 1-2hrs with some workout
- Amar CEO made $13,4 millon on 2024 and my pay package USD is 42,076. He makes 318 times more than me.
- Jason Flores has been 11 years in Rackspace
- Jay Das says ODS are not archived but other data models
- Niv has been 4 years
- Para revisar que dashboards son utiles para los stakeholders, revisar quienes son sus jefes y en que se meten en tableau y revisar si su jefe esta en PTO
- `rax-enterprisebi.report_tables.gts_rackers` has a snapshot per month
- Timesheet remember:
	- Consider projects **EBI Microsoft Power Bi** , **Adhoc Run the Business**, **ITS Management Meetings, Training, etc**, **EBI Dashboard/Reporting**, **ITS BI Adhoc/RTB**
		- these have each like **Requierement meeting**, **trainings**, etc
- Extracts over Live connections in Data Sources
- Update tickets twice a week: Martes y Jueves 
- Nosotros somo ITS
- un story point son 4hrs
- Jira lingo: Epic>Story>Story Points>Issues
- Know how to slice up a request into multiple tickets: data model, reglas de negocio, visualizaciones
- Star y End date son estimaciones, pero compromiso de deathline o llevarlo al final del sprint
- Effort size: usually medium
- Know to @mention the stakeholder for them to have the notification of events in Jira. < Espanso
- En kanban board> IN UAT US> queda 5 dias
	- No se libera el producto--el ticket-- hasta que el stakeholder explicitametne lo apruebe en jira
	- most development discussion should occur en Jira tickets. or add "como lo hablamos en teams"
- Nishan hace cosas en R o Python con tableau. Puedes preguntarle que hace
- Good cop y bad cop. Mi jefe es el bad cop y siempre se las paso a el. Mi jefe me lo pidio
- Grabar las sesiones con los stakeholders
- Pregutar en las sesiones con los stakeholders y preguntar quien mas me puede ayudar
-  DONT USE q.accounts table of ODS salesforce
- Systemas de Billing
	- Raptor
	- Data Pipe
	- Encore (solo se muestra)
- Polaris Dashboard> se tiene hoja de devices
- Steve Conisbee owns updating [queue mappings]([gcs-tablea…rce-files – Bucket details – Cloud Storage – rax-enterprisebi – Google Cloud console](https://console.cloud.google.com/storage/browser/gcs-tableau-source-files/GTS;tab=objects?project=rax-enterprisebi&prefix=&forceOnObjectsSortingFiltering=false)) 
- upsi we have `vw_account_info` same name one in report tables and another in report specific


## Refreshing a Tableau Data Source
1. open git file in repo locally with tableau
2. auth bigquery
3. return to sheet 1
4. click on data 
5. select the named datasource>add to saved data sources