
# Problem 1
 - write the queries and submit that
 - use the patients table

- find no of patients grouped by severity
```js
select severity, count(*) as counts from patients group by severity;
```
- find no of patients grouped by hospital
```js
select hospital, count(*) as counts from patients group by hospital;
```
- find average age grouped by hosptial
```js
select AVG(age) from patients group by hospital;
```
- find the average BMI of all patients
```js
select (weight/(height*height)) as bmi from patients;
```
- find average BMI grouped by Hospital
```js
select (weight/(height*height)) as bmi from patients group by hospital;
```
- find average BMI grouped by Severity
```js
select (weight/(height*height)) as bmi from patients group by severity;
```
- find date (diagnosis date) wise in ascending order total no of patients
```js
select * from patients order by date_of_diagnosis asc;
```
- show all users who bmi is between two values ( you can decide the values ) 
```js
select * from (select (weight/(height*height)) as bmi from patients group by bmi between 0.0021 and 0.0038) patients;
```
- show top 10 weighing patients
```js
select patient_name, weight from patients order by weight desc limit 10;
```
- show second top 10 weighing patients
```js
 select patient_name, weight from patients order by weight desc limit 10, 10;
```
- show count of users with name which start with B
```js
select count(*) from patients where patient_name like "B%";
```
- show count of users whose name end with E
```js
select count(*) from patients where patient_name like "%E";
```
- show count of users whose name have LL on it
```js
 select count(*) from patients where patient_name like "%LL%";
```

## Problem 2
- create a country table
- it should have id, and name, id is the primary key
- create a users table
- it needs to have a primary key
- id, name, country id
- id is primary key
- country is a foreign key to country table primary key

```js
create table country (
  id int NOT NULL AUTO_INCREMENT,
  name varchar(255) NOT NULL,
  PRIMARY KEY (id)
);

create table users (
  id int NOT NULL AUTO_INCREMENT,
  name varchar(255) NOT NULL,
  country_id int NOT NULL,
  PRIMARY KEY (id),
  FOREIGN KEY (country_id) REFERENCES country (id)
);
```