# DB2 Export Scripts

This repository provides some simple scripts to help exporting your DB2 code so it can be migrated to [Snowflake](https://www.snowflake.com/) using [SnowConvert](https://www.mobilize.net/products/database-migrations/snowconvert)

## Version

Version 1.1 
Release 2021-11-05

## Usage

The following are the steps to execute the DDL Code Generation. They can be executed in Linux/Unix enviroments.

## **For Linux/Unix:**

1 - Modify `createddls.sh` 
Using a text editor modify the following parameters:

    * `DATABASES_TO_EXCLUDE`

That variable will determine if there are any database that you want to exclude from the extraction

It is recommended to use a user  with administrative privileges and to run on a production-like environment with recently up to date statistics.


2 - After modifying, the `create_ddls.sh` file can be run from the command line to execute the extract.  The following files will be created in the directory `/object_extracts/DDL`:

### DDL Files
For each database a folder with the database name and a file called DDL_All.sql will be generated. It will contain the definitions of the objects in the database.

### Reports

For each database some volumetrics reports will be created:

- volumetrics_per_object.txt 
- volumetrics_per_database.txt
- db_size.txt

## Reporting issues and feedback

If you encounter any bugs with the tool please file an issue in the
[Issues](https://github.com/MobilizeNet/SnowConvertDDLExportScripts/issues) section of our GitHub repo.

## License

These scripts are licensed under the [MIT license](https://github.com/MobilizeNet/SnowConvertDDLExportScripts/blob/main/SQLServer/LICENSE.txt).
