# SQL-Tables
Sql Kod Databas
                
  CREATE TABLE DOG (DOG_ID INTEGER PRIMARY KEY, DOGNAME VALCHAR(50));              
                                         
```sql
                                              ###Breeder
CREATE TABLE breeder (id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));
CREATE TABLE Veterinarian (id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));
CREATE TABLE Clinic (id INTEGER PRIMARY KEY, clinic_name VARCHAR(50));
```
-------------------------------------------------------------------------------------------------

                                         
```sql 
                                             ###Veterinarian
CREATE TABLE Veterinarian (Veterinarian_id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));
```
                                        
```sql
                                            ###Clinic
CREATE TABLE Clinic (Clinic_id INTEGER PRIMARY KEY, clinic_name VARCHAR(50));
```

```cs
-- Daniels anteckningar --

select * from ownerperson;

select * from Dog;

UPDATE Dog
set Owner_ID = 3
where Dog_ID = 2;

ALTER TABLE OwnerPerson ADD CONSTRAINT FK_Dog_ID FOREIGN KEY (Dog_ID) REFERENCES Dog(Dog_ID);

Update OwnerPerson
set Dog_ID = 2
where owner_id = 3 ;

UPDATE Dog

select * from Dog
inner join
OwnerPerson on Dog.Dog_id = OwnerPerson.dog_id;

Update 

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

EXEC sp_help 'dbo.dog';
```
--------------------

SELECT Dog.Dog_ID, OwnerPerson.Owner_ID
FROM Dog
INNER JOIN OwnerPerson
ON Dog.Owner_ID = OwnerPerson.Owner_ID;

UPDATE Dog
SET Race = 'Terrier'
WHERE Dog_ID = 1;

ALTER TABLE Dog
ADD Mother VARCHAR(20);
ALTER TABLE Dog
ADD Father VARCHAR(20);

ALTER TABLE Dog
ADD Gender VARCHAR(20);
