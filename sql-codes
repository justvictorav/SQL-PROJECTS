SELECT *
FROM [dbo].['Workplace Safety Data$']
WHERE PLANT='GEORGIA'

SELECT *
FROM [dbo].['Workplace Safety Data$']
WHERE [INCIDENT TYPE] <> 'fall'

SELECT *
FROM[dbo].['Workplace Safety Data$']
WHERE PLANT IN ('CALIFORNIA','FLORIDA')

SELECT *
FROM[dbo].['Workplace Safety Data$']
WHERE PLANT = 'CALIFORNIA' AND [INCIDENT COST]>1000

SELECT *
FROM[dbo].['Workplace Safety Data$']
WHERE PLANT = 'CALIFORNIA' OR [INCIDENT COST]>1000

select [Plant]
      ,[Gender]
      ,avg([Incident Cost]) as avg_incident_cost
      ,sum([Incident Cost]) as total_incident_cost
      ,count(*) as number_of_incident
      from[dbo].['Workplace Safety Data$']
      group by [Plant]
              ,[Gender]
      having plant in ('alabama','california','georgia')
     order by[Plant] asc

with incient_rank as
(
select * 
       ,rank () over( partition by[Plant] order by [Incident Cost] desc) as rank
from[dbo].['Workplace Safety Data$']
)
select*
from incient_rank
where rank=1 
