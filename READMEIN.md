# Inlämning template 

```SQL




CREATE OR ALTER PROCEDURE Statistics_Get
AS
BEGIN

	Select count (dogid) as 'Antal hundar'
	from dog
	RETURN 

END
GO


CREATE OR ALTER PROCEDURE Gender_GetAll
@Gender varchar(10)
AS
BEGIN

Select dogname from dog inner join Gender on dog.GenderID = gender.GenderID
where sex = @Gender

	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Breed_GetAll
AS
BEGIN

	select distinct race_name from race
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_Find 
    @name varchar(50),
    @chipid varchar(50)
	-- osv
AS
BEGIN

    select dogname, ChipID from Dog
    where dogname like  @Name OR ChipID like  @chipid
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetInfo
	@DogId int
AS
BEGIN

    select DogName, ChipID, firstname, lastname, racename, sex
    from
    ((Dog Inner join OwnerPerson on dog.ownerid = ownerperson.ownerid)
    inner join race on dog.raceid = race.raceid
    inner join gender on dog.genderid = gender.genderid)
    where DogID = @Dogid
    
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetOwner
	@DogId int
AS
BEGIN

	select firstname, lastname, Adress, Telefonnummer, dogname from OwnerPerson
    inner join Dog 
    on dog.OwnerID = OwnerPerson.OwnerID
    where DogID = @dogid
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetJournal
	@DogId int
AS
BEGIN

	select examinationDate, Result, dogname, clinicname
    from ((dog
    inner join Veterinaryexamination on dog.dogid= Veterinaryexamination.dogid)
    inner join clinic on dog.clinicid = clinic.ClinicID)
    where dog.DogID = @DogId
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetBreeder
	@DogId int
AS
BEGIN

	select BreederName, Place
	from Breeder inner join Litter on Litter.BreederID = Breeder.BreederID 
	inner join Dog on Dog.LitterID = Litter.LitterID
	where Dog.DogID = @DogId
	RETURN 

END
GO


CREATE OR ALTER PROCEDURE Dog_GetLittermates
	@DogId int
AS
BEGIN

	select DogName, NameOfLitter
from Dog full join Litter on Dog.LitterID = Litter.LitterID
where Dog.LitterID = @DogId
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_GetOffspring
	@DogId int
AS
BEGIN

	select DogName from Dog inner join Litter on Dog.LitterID = Litter.LitterID
where LitterMom = @DogId or LitterDad = @DogId
	RETURN 

END
GO

-- Övriga funktioner

CREATE OR ALTER PROCEDURE Dog_Add 
       @dogid int,
       @DogName VARCHAR(50),
       @OwnerID INT,
       @ChipID VARCHAR(20),
       @LitterID INT NULL,
       @RaceID INT,
       @GenderID INT,
       @ClinicID INT null
AS
BEGIN
	INSERT INTO Dog
          ( 
            DogID,
            DogName,
            OwnerID,                 
            ChipID,
            LitterID,
            RaceID,
            GenderID,
            ClinicID
          ) 
     VALUES 
          ( 
            @dogid,
            @DogName,
            @OwnerID,
            @ChipID,
            @LitterID,
            @RaceID,
            @GenderID,
            @ClinicID
          ) 
	
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
        @dogID int,
        @dogname varchar(30),
        @ownerID int

AS
BEGIN

	UPDATE Dog
        set ownerid = @ownerid
        where dogname = @dogname and
        dogid = @dogid
	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_ReportMissing
	  @dogid INT
AS
BEGIN

	UPDATE DOG
    SET
    StatusId = 2
    WHERE dogid = @Dogid

	RETURN 

END
GO

CREATE OR ALTER PROCEDURE Dog_ReportFound
	 @dogid INT
AS
BEGIN

	UPDATE DOG
    SET
    StatusId = 1
    WHERE dogid = @Dogid
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

