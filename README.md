##Evaluate C# code and expression in T-SQL stored procedure, function and trigger##

**Extend SQL with the full C# Syntax and get the best of both languages:**

- Access to .NET features and objects
 - LINQ
 - Math
 - Regex
 - String Interpolation
 - Web Service
- Evaluate expression at runtime
 - Use column value as formula
 - Use column value as parameter
- Perform File Operation
 - Replace xp_cmdshell with C# Syntax
 - Use DirectoryInfo, FileInfo
 - Impersonate context
- T-SQL Function Enhancement
 - Error Handling (Try/Catch)
 - Call stored procedure
 - Modify Table State
 - Run dynamic SQL
 
    
```sql
-- Evaluate dynamically expression in T-SQL
DECLARE @tableFormula TABLE (
   Formula VARCHAR(255), X INT, Y INT, Z INT
)

INSERT  INTO @tableFormula VALUES ('x+y*z', 1, 2, 3 ), 
                                  ('(x+y)*z', 1, 2, 3 )
-- SELECT 7
-- SELECT 9
SELECT SQLNET::New(Formula)
              .ValueInt('x', X)
              .ValueInt('y', Y)
              .ValueInt('z', Z).EvalInt()
FROM @tableFormula
```

## Download
**[SQLNET.zip](https://github.com/zzzprojects/Eval-SQL.NET/releases)**

_Minimum Requirements_
- SQL CLR Permission Level: **SAFE**
- SQL 2012
- .NET Framework 4.0

Stay updated with latest changes

<a href="https://twitter.com/zzzprojects" target="_blank"><img src="http://www.zzzprojects.com/images/twitter_follow.png" alt="Twitter Follow" height="24" /></a>
<a href="https://www.facebook.com/zzzprojects/" target="_blank"><img src="http://www.zzzprojects.com/images/facebook_like.png" alt="Facebook Like" height="24" /></a>

## SQL Server Eval
Dynamically evaluate arithmetic operation and expression in SQL

```sql
CREATE PROCEDURE [dbo].[Select_Switch] @x INT, @y INT, @z INT
AS
    BEGIN
        DECLARE @result INT

        SET @result = SQLNET::New('
switch(x)
{
    case 1: return y + z;
    case 2: return y - z;
    case 3: return y * z;
    default: return Convert.ToInt32(y ^^ z); // Pow
}
   ').Val('x', @x).Val('y', @y).Val('z', @z).EvalInt()

        SELECT  @result
    END

GO

-- RETURN 5
EXEC Select_Switch 1, 2, 3
-- RETURN -1
EXEC Select_Switch 2, 2, 3
-- RETURN 6
EXEC Select_Switch 3, 2, 3
-- RETURN 8
EXEC Select_Switch 4, 2, 3
```

**[Learn more](https://github.com/zzzprojects/Eval-SQL.NET/wiki/SQL-Server-Eval-%7C-Dynamically-evaluate-arithmetic-operation-and-expression-in-SQL)**

## SQL Server Regex
Use regular expression to search, replace and split text in SQL

```sql
DECLARE @s VARCHAR(MAX) = '1, 2, 3; 4; 5'
DECLARE @sqlnet SQLNET = SQLNET::New('Regex.Split(input, ",|;")')

SELECT  *
FROM    dbo.SQLNET_EvalTVF_1(@sqlnet.ValueString('input', @s))
```

**[Learn more](https://github.com/zzzprojects/Eval-SQL.NET/wiki/SQL-Server-Regex-%7C-Use-regular-expression-to-search,-replace-and-split-text-in-SQL)**

## SQL Server File Operation 
xp_cmdshell alternative to read and write files in SQL

```sql
-- REQUIRE EXTERNAL_ACCESS permission
DECLARE @sqlnet SQLNET = SQLNET::New('
string path = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);

var dir = new DirectoryInfo(path);
return dir.GetFiles("*.*").Select(x => x.FullName).OrderBy(x => x).ToList();')
    .Impersonate()

-- SELECT * FROM DesktopFiles ORDER BY File.Fullname
EXEC dbo.SQLNET_EvalResultSet @sqlnet
```

**[Learn more](https://github.com/zzzprojects/Eval-SQL.NET/wiki/SQL-Server-File-Operation-%7C-xp_cmdshell-alternative-to-read-and-write-files-in-SQL)**

## Security
You can install Eval SQL.NET with any SQL CLR permissions
- SAFE
- EXTERNAL_ACCESS
- UNSAFE


## Performance
Eval SQL.NET is fast, very fast! The performance is very close to SQL CLR.

You can evaluate over **150,000** expression in a loop under one seconds and over *1,000,000* expression from a table!

## FREE vs PRO

Every month, a **[FREE trial](https://github.com/zzzprojects/Eval-SQL.NET/releases)** of the PRO version is available to let you evaluate all its features without limitations.

Features | FREE Version | PRO Version
------------ | :-------------: | :-------------:
Maximum Characters | 50 | Unlimited
Commercial License | No | Yes
Support & Upgrades (1 year) | No | Yes

Learn more about the **[PRO Version](http://eval-sql.net/#pro)**

## Contribution

Supporting & developing FREE features takes **hundreds** and **thousands** of hours! If you like our product please consider making a donation to keep us running.

<a href="http://www.zzzprojects.com/contribute/" target="_blank"><img src="http://www.zzzprojects.com/images/paypal-contribute-2.png" alt="Contribute" height="48"></a>

Contribution isn't all about money!
 - Blog it
 - Comment it
 - Fork it
 - Star it
 - Share it

A **HUGE thanks** for your extra support.

## More Projects

**Entity Framework**
- [Entity Framework Extensions](http://www.zzzprojects.com/products/dotnet-development/entity-framework-extensions/)
- [Entity Framework Plus](https://github.com/zzzprojects/EntityFramework-Plus)

**Bulk Operations**
- [NET Entity Framework Extensions](http://www.zzzprojects.com/products/dotnet-development/entity-framework-extensions/)
- [NET Bulk Operations](http://www.zzzprojects.com/products/dotnet-development/bulk-operations/)

**Expression Evaluator**
- [Eval SQL.NET](https://github.com/zzzprojects/Eval-SQL.NET)
- [Eval Expression.NET](https://github.com/zzzprojects/Eval-Expression.NET)

**Others**
- [Extension Methods Library](https://github.com/zzzprojects/Z.ExtensionMethods/)
- [LINQ Async](https://github.com/zzzprojects/Linq-AsyncExtensions)

**Need more info?** info@zzzprojects.com

Contact our outstanding customer support for any request. We usually answer within the next business day, hour, or minutes!
