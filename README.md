# sql-imp-queries
## create table 
```sql
create table GuestList(
[GueastId] int not null IDENTITY(1,1) PRIMARY KEY,
[Name] varchar (50) not null,
[Email] varchar (50) not null,
[Phone] int not null,
WillAttend bit

);

```

## create procedure
```sql
ALTER PROCEDURE [dbo].[UserDBOperation]
@Action varchar(50)=NULL,
@UserId INT=0,
@FirstName VARCHAR(30)=NULL,
@LastName VARCHAR(30)=NULL,
@Email VARCHAR(20)=NULL,
@DateOfBirth VARCHAR(30)=NULL,
@Gender VARCHAR(16)=NULL,
@education VARCHAR(30)=NULL,
@Country VARCHAR(30)=NULL,
@City VARCHAR(30)=NULL,
@UserName VARCHAR(10)=NULL,
@UserPassword DATE=NULL
As

BEGIN
 IF @Action = 'SELECT'
 BEGIN 
  SELECT  [FirstName]
		  ,[LastName]
		  ,[Email]
		  ,[DateOfBirth]
		  ,[Gender]
		  ,[Country]
		  ,[City]
		  ,[UserName]
		  ,[UserPassword]
		  ,[UserId]
  FROM UserData;
 END

 IF @Action = 'INSERT'
 BEGIN
  INSERT INTO UserData ([FirstName]
      ,[LastName]
      ,[Email]
      ,[DateOfBirth]
      ,[Gender]
      ,[Country]
      ,[City]
      ,[UserName]
      ,[UserPassword]) 
    VALUES
      (@FirstName
      ,@LastName
      ,@Email
      ,@DateOfBirth
      ,@Gender
      ,@Country
      ,@City
      ,@UserName
      ,@UserPassword);
 END

 IF @Action ='DELETE'
 BEGIN
  DELETE FROM UserData
  WHERE UserId=@UserId;
 END

 IF @Action ='UPDATE'
 BEGIN
  UPDATE UserData
  SET [Firstname]=@FirstName
   ,[Lastname]=@LastName
   ,[Email]=@Email
   ,[DateOfBirth]=@DateOfBirth
   ,[Gender]=@Gender
   ,[Country]=@Country
   ,[City]=@City
   ,[UserName]=@UserName
   ,[UserPassword]=@UserPassword
  WHERE UserId=@UserId; 
 END
END
```



Important links:

https://forums.asp.net/t/2133883.aspx?How+to+send+data+from+_Layout+to+controller+

https://codeburst.io/getting-started-with-angular-7-and-bootstrap-4-styling-6011b206080?source=search_post&gi=1d973c784052

https://medium.com/better-programming/the-differences-between-a-junior-mid-level-and-senior-developer-bb2cb2eb000d

