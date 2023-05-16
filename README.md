csv2sqlite
===================
csv2sqlite is a fast and simple to use conversion tool that converts the content of a CSV file into a table in a SQLite database file.

The number of columns is arbitrary. The CSV file must have a header row and use comma as a delimiter between columns. Values for each column may be quoted.

The tool can also be used to import the content of many CSV files into the same SQLite database file.

Developed using C++.

Usage
===================
```
usage: csv2sqlite.exe -o <db file> -f <csv file> [-t <name>] [-h]

   -o <db file>      SQLite file (REQUIRED)
   -f <csv file>     CSV file    (REQUIRED)
   -t <name>         Use this table name (OPTIONAL)
   -h                Help
```

Examples
===================
`csv2log.exe -o test.db -f statistics.csv`<br>
The data will be inserted into a table name named as the filename of the csv file. In this case to "statistics".

`csv2log.exe -o test.db -f statistics.csv -t numbers`<br>
The data will be inserted into a table name called "numbers".

<i><ins>Please notice:</ins> If the table name already exists in the SQLite database and the number of columns matches, the content of the CSV file will be added to the table like an INSERT.</i>

Execution time
===================
Below, a CSV file with a file size of 61 570 904 bytes (~61.6 MB) was used.<br>
Execution time was 311 ms on an i7-10510U running MS Windows 10 Pro (19045).

```
*** csv2sqlite ver. 1.0 (c) 2023 swepeba ***
MIT License - https://github.com/swepeba/csv2sqlite

PRE-CHECKS
---> A new database file will be created
---> Rows in CSV file: 36420
---> Cols in CSV file: 26

SUMMARY
---> Rows converted: 36420 (311 ms)
---> SUCCESS, all rows converted
```

Download
===================
A pre-built and signed [binary (.exe)](https://github.com/swepeba/csv2sqlite/releases/latest) is found in the latest release.

Planned updates
===================
* Support for bulk conversion of all CSV files in a folder. In version 1.0 the tool has to be executed for each CSV file.

Changelog
===================
ver. 1.0 (2023-05-16)
* First release.
