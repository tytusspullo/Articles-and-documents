***Technical debt in your application and cross-platform "Migrate SqlCLient"***

Have you ever wondered why it is so difficult to migrate your application to newer technology or run it on multiple operating systems?
Sometimes cross-platform functionality is not possible due to elements related to Windows.

Let's look at something I love: ADO.NET libraries. Since the dawn of time, the most frequently chosen method of operating on a database has been SqlClient, 
unfortunately the old *System.Data.Sqlclient* is burdened with technological debt, many data types, e.g. the so-called *Spatial Types*, which allow the use 
of *SqlGeometry* and *SqlGeography* geolocation types, are closely related to SQL Server and windows system. When trying to migrate to NET core and multi-platform, 
we will probably want to use a newer version of SqlClient in the *Microsoft.Data.SQLclient* name space. In this case, you should pay attention to 
whether a given version of MDS has libraries supporting these types. There is need for *Microsoft.SqlServer.Types.dll* which is missing in older MDS NuGets.
The set of NuGet packages up to version 5.0.0 did not have this support, only from version 5.0.1 you can start migration when we use these types of data.









***Some SQL Tips***

-remember CURSOR's are slow, avoid use them first try another way to achive what you need

-every sql query is executed from backwards first is executed clause WHERE , than FROM , and SELECT statement last, 
if you want optimize your query good point to start is from WHRE to discard as many rows as possible from the query

-remember that subqueries in SELECT clause are executed for evry row, remember at least corelate them by alias at least

-do not afraid use ON DELETE CASCADE they work well with trigers

-use EXTENDED EVENTS colect lot data for you

-SQL profiler can be helpful if you want see what is executed and 

-if you can afort it use SQL Promt from Radgate , there is no other faster way to work with your SQL code :) 
best intelisence and formating and much more
