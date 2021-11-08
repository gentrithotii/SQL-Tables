# SQL-Tables
```sql

DROP TABLE IF EXISTS Veterinary_Examination;
CREATE TABLE Veterinary_examination(Id INTEGER PRIMARY KEY, examination_date DATE NOT NULL, clinic_id INTEGER NOT NULL, dog_id INTEGER NOT NULL, result VARCHAR(20)NOT NULL);

select*from Veterinary_examination;

ALTER TABLE Veterinary_examination ADD CONSTRAINT FK_Clinic_id FOREIGN KEY (clinic_Id) REFERENCES Clinic(Clinic_ID);
ALTER TABLE Veterinary_examination ADD CONSTRAINT FK_Dog_id FOREIGN KEY (dog_Id) REFERENCES Dog(Dog_ID);

INSERT INTO Veterinary_examination(Id, examination_date, clinic_id, dog_id, result) VALUES (1, '2021-10-22', 1, 4, 'All good');

DROP TABLE IF EXISTS Breeder;
CREATE TABLE Breeder(Id INTEGER PRIMARY KEY, Breeder_name VARCHAR(20), Place VARCHAR(20), Litter_id INTEGER);
INSERT INTO Breeder(Id, Breeder_name) VALUES (1, 'Golden Puppies');


CREATE TABLE Veterinary_examination(Id INTEGER PRIMARY KEY, examination_date DATE, clinic_id INTEGER, dog_id INTEGER, result VARCHAR(20));

Sql Kod Databas
select * from dog
inner join OwnerPerson
on dog.owner_id = OwnerPerson.Owner_Id
update Dog set Race = 'schäfer' where dog_id = 1
                
  CREATE TABLE DOG (DOG_ID INTEGER PRIMARY KEY, DOGNAME VALCHAR(50));              
                                         

                                              ###Breeder
CREATE TABLE breeder (id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));
CREATE TABLE Veterinarian (id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));
CREATE TABLE Clinic (id INTEGER PRIMARY KEY, clinic_name VARCHAR(50));

-------------------------------------------------------------------------------------------------

                                         

                                             ###Veterinarian
CREATE TABLE Veterinarian (Veterinarian_id INTEGER PRIMARY KEY, firstname VARCHAR(50), lastname VARCHAR(50));

                                        

                                            ###Clinic
CREATE TABLE Clinic (Clinic_id INTEGER PRIMARY KEY, clinic_name VARCHAR(50));



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


```
