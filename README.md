# SQL Academy — Solutions
 
Solutions to tasks from the online SQL trainer SQL Academy.
 
---
 
## 📌 About the Project
 
This repository contains my solutions to exercises from 
https://sql-academy.org (https://sql-academy.org/)
 
The project is created for:
- practicing SQL
- reinforcing theoretical knowledge
- tracking personal learning progress
 
---
 
## 📚 SQL Queries
 
### Task 4: List people's names that end with "man"
```sql
Select Passenger.name from Passenger WHERE Passenger.name like '%man';
```

### Task 5: Number of flights on the TU-134
```sql
SELECT COUNT(plane)as count FROM trip WHERE  plane = 'TU-134';

