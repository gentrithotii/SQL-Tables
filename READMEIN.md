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

