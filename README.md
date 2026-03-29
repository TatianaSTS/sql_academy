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
```


### Task 6: Companies that flew Boeing
```sql
SELECT DISTINCT company.name FROM company JOIN trip on company.id = trip.company where trip.plane = 'Boeing';
```

### Task 13: Full namesakes
Display the names of people who have a full namesake among the passengers
```sql
Select name from Passenger Group by Passenger.name HAVING Count(name)>1;
```


### Task 19: Who bought the potatoes?
Determine which family member bought the potatoes.
```sql
Select Distinct status from FamilyMembers join Payments on member_id=family_member join Goods on good=good_id where good_name='potato';
```

### Task 23: The Most Expensive Delicacy
Find the most expensive delicacy and display its price.
```sql
SELECT good_name, unit_price FROM Payments
JOIN Goods
ON Payments.good = Goods.good_id
JOIN GoodTypes 
ON Goods.type = GoodTypes.good_type_id
WHERE good_type_name = 'delicacies'
ORDER BY unit_price DESC
LIMIT 1;
```

### Task 38: How many students are named Anna in school?
```sql
Select COUNT(*) as count from Student where Student.first_name='Anna';
```

### Task 74: Internet Availability in the room
Print the identifier and the internet availability indicator for the premises.
If the internet is available in the rental property, print "YES"; otherwise, print "NO."
Use the "AS has_internet" construct to print the internet availability indicator for the premises.
```sql
Select Rooms.id, 
  Case 
  when has_internet=true then 'YES'
  when has_internet=false then 'NO'
  end as has_internet
  from Rooms;
```

### Task 75: Students born in May
Display the last name, first name, and date of birth of students born in May.
```sql
Select Student.last_name, Student.first_name,birthday from Student where MONTH(birthday)='5';
```

### Task 99:Revenue from female audience
```sql
Select SUM(price*items) as income_from_female from Purchases where user_gender like 'f%';
```

### Task 114: Co-pilots to New York
Write a query that will return the names of pilots who flew as co-pilots (second_pilot_id) to New York in August 2023.
```sql
Select name from Pilots join Flights on pilot_id=second_pilot_id where destination='New York' and YEAR(flight_date) = 2023 
and MONTH(flight_date) = 8
```

### Task 128: Create an index on email
Create the idx_price index on the price column of the Rooms table.
```sql
CREATE index idx_price on Rooms(price);
```



