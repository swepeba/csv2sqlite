![Banner](csv2sqlite-banner.jpg)
csv2sqlite
===================
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT) 
<img src="https://img.shields.io/badge/Windows-Executable-green">
<br>
csv2sqlite is a fast and simple to use conversion tool that converts the content of one or many CSV files into tables in a SQLite database file. Supports [RFC 4180](https://www.ietf.org/rfc/rfc4180.txt).

* Comma character has to be used between columns.
* Double quote characters (") can be used to mark the start and end of a column.
* The number of columns is automatically found.
* The tool will assume that the first row is a header row including the column names.

The tool can also be used to bulk import the content of many CSV files into the same SQLite database file.

Developed using C++.

Usage
===================
```
usage: csv2sqlite.exe -o <db file> -f <csv file> [-t <name>] [-p <path>] [-h]

   -o <db file>      SQLite file (REQUIRED)
   -f <csv file>     CSV file    (REQUIRED)
   -t <name>         Use this table name                    (OPTIONAL)
   -p <path>         Path to CSV files, ignores -f and -t   (OPTIONAL)
   -h                Help
```

Examples
===================
`csv2sqlite.exe -o test.db -f statistics.csv`<br>
The data will be inserted into a table name named as the filename of the csv file. In this case to "statistics".

`csv2sqlite.exe -o test.db -f statistics.csv -t numbers`<br>
The data will be inserted into a table name called "numbers".

`csv2sqlite.exe -o test.db -p c:\temp`<br>
The data from all existing CSV files found in the path will be inserted into the same database file.

<i><ins>Please notice:</ins> If the table name already exists in the SQLite database and the number of columns matches, the content of the CSV file will be added to the table like an INSERT.</i>

Execution time
===================
Below, a CSV file with a file size of 61 570 904 bytes (~61.6 MB) was used.<br>
Execution time was 297 ms on an i7-10510U running MS Windows 10 Pro (19045).

```
*** csv2sqlite ver. 1.1 (c) 2023, swepeba ***
MIT License - https://github.com/swepeba/csv2sqlite

INFORMATION
---> A new database file will be created

---> CSV file: test.csv
------> Rows in CSV file: 36420
------> Cols in CSV file: 26
------> Rows converted: 36420 (297 ms)
------> SUCCESS, all rows converted
```

Download
===================
A pre-built and signed [binary (.exe)](https://github.com/swepeba/csv2sqlite/releases/latest) is found in the latest release.

Release notes
===================
<b>ver. 1.1 (2023-05-17)</b>
* Support for `-p <path>` added.

<b>ver. 1.0 (2023-05-16)</b>
* First release.

License
===================
Copyright (c) swepeba.
Licensed under the [MIT License](LICENSE).
