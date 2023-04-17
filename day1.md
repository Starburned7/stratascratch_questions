-- Find the owners who have at least one facility with all 3 grades.

```sql
select distinct owner_name from la_restaurant_health_inspections
where facility_name in(
SELECT facility_name
     FROM la_restaurant_health_inspections
     GROUP BY facility_name
     HAVING count(DISTINCT grade)=3);
```
