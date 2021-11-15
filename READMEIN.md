# Inlämning template 

```SQL




CREATE OR ALTER PROCEDURE Statistics_Get
AS
BEGIN

	-- Implementera
	-- hundar.skk.se/hunddata/
	RETURN 

END
GO


CREATE OR ALTER PROCEDURE Gender_GetAll
AS
BEGIN

	-- Implementera
	-- hundar.skk.se/hunddata/Hund_sok.aspx
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Breed_GetAll
AS
BEGIN

	-- Implementera
	-- hundar.skk.se/hunddata/Hund_sok.aspx
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_Find 
	@Regno varchar(50), 
	@Name varchar(50) 
	-- osv
AS
BEGIN

	-- Implementera
	-- hundar.skk.se/hunddata/Hund_sok.aspx
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetInfo
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Den "grå informationen"
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetOwner
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Fliken Ägare
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetJournal
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Fliken Vetrinär
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetBreeder
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Fliken Uppfödare
	RETURN 

END
GO


CREATE OR ALTER PROCEDURE Dog_GetLittermates
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Fliken Kullsyskon
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetOffspring
	@DogId int
AS
BEGIN

	-- Implementera
	-- https://hundar.skk.se/hunddata/Hund.aspx?hundid=2201379
	-- Fliken avkommor
	RETURN 

END
GO

-- Övriga funktioner

CREATE OR ALTER PROCEDURE Dog_Add 
	-- parametrar?
AS
BEGIN

	-- Implementera
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Owner_Add 
    @ownerID int,
    @FirstName varchar(40),
    @LastName varchar(40),
    @Telefonnummer varchar(20),
    @Adress varchar(50)
AS
BEGIN

    insert into OwnerPerson
    (
    OwnerID,
    FirstName,
    LastName,
    Telefonnummer,
    Adress
    )
    values
    (
    @ownerID,
    @FirstName,
    @LastName,
    @Telefonnummer,
    @Adress
    )
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_ChangeOwner
	-- parametrar?
AS
BEGIN

	-- Implementera
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_ReportMissing
	-- parametrar?
AS
BEGIN

	-- Implementera
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_ReportFound
	-- parametrar?
AS
BEGIN

	-- Implementera
	RETURN 

END
GO

```

Reflektioner av grupp Svart(Är vi ute och cyklar?

1. Vi har lärt oss hur vi skapar och hur index används.

2. Vi har lärt oss hur vi använder stored procedures.

3. Vi har fått repetera mycket av det som vi redan lärt oss tex inner join, ändra i tables, skapa tabeller och ER-diagram.

4. En reflektion är hur viktigt det är att alla förstår och löser problemen ihop.

Vad kunde vi gjort annorlunda?

En funktion som vi inte är helt nöjda med är att en icke bortsprungen hund kan bli upphittad i vår tabell.

Vi hade också kunnat göra tabellerna betydligt större men vi hade de nedbantade för att få en bra och enkel översikt.
