# SQL Server Export Scripts

This repository provides some simple scripts to help exporting your SQLServer code so it can be migrated to [Snowflake](https://www.snowflake.com/) using [SnowConvert](https://www.mobilize.net/products/database-migrations/snowconvert)

## Version

Version 1.1 
Release 2021-09-07

## Usage

The `extract-sql-server-ddl.ps1` script attempts to connect to an instance of SQL Server using either Windows or SQL authentication and, for each database that survives inclusion/exclusion filters, retrieves certain object definitions as individual DDL files to a local directory. 

**SQL Server tested versions**: `SQL Server 2019`, `Azure SQLDatabase`

The script use the following parameters:

* **ServerName**: Specifies the SQL Server instance to use
* **Port**: Specifies the port to use (default is 1433)
* **SqlAuthentication**: Bypass "normal" Windows Authentication when attempting to connect (default is false)
* **UserId**: Specifies the user name to use when attempting to connect (used in conjunction with -SqlAuthentication)
* **Password**: Specifies the password associated with the UserId to use when attempting to connect (used in conjunction with -SqlAuthentication)
* **IncludeSystemObjects**: Specify whether to include databases, schemas, and tables tagged as SQL Server system objects (default is false)
* **IncludeDatabases**: Specifies databases that match the listed pattern(s) be included in the extraction (default is all)
* **ExcludeDatabases**: Specifies databases that match the listed pattern(s) be excluded from the extraction (default is none)
* **ScriptDirectory**: Specifies the root directory in which the extracted files are to be stored (default is C:\MyScriptsDirectory)
* **INPUTS**: None.  You cannot pipe objects to extract-sql-server-ddl.ps1.
* **OUTPUTS**: System.String.

> **_NOTE:_**  For named instances, use  hostname\InstanceName

Here some examples of how use the script:

Example 1:

```ps
PS> .\extract-sql-server-ddl.ps1
```

Example 2:

```ps
PS> .\extract-sql-server-ddl.ps1 -ServerName foo.mydomain.com -Port 1500
```

Example 2:

```ps
PS> .\extract-sql-server-ddl.ps1 -SqlAuthentication -ServerName foo.database.windows.net
```



## Reporting issues and feedback

If you encounter any bugs with the tool please file an issue in the
[Issues](https://github.com/MobilizeNet/SnowConvertDDLExportScripts/issues) section of our GitHub repo.

## License

These scripts are licensed under the [MIT license](https://github.com/MobilizeNet/SnowConvertDDLExportScripts/blob/main/SQLServer/LICENSE.txt).
