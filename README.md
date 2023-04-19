# IOS - Operating systems

## Introduction
The goal of the task is to create a shell script for analyzing records of people with proven infection with the coronavirus
the disease of COVID-19 in the territory of the Czech Republic. The script will filter records and provide basic statistics according to user input.

## Running
```c++
    ./corona [-h] [FILTERS] [COMMAND] [LOG [LOG2 [...]]
```
+ -h - prints help message

+ FILTERS could be combination:
    * -a DATETIME - after: only records AFTER this date are considered
    * -b DATETIME - before: only records BEFORE this date are considered
    * -g GENDER - considered only records of giving gender, for Male "M", for Female "Z"
    * -s [WIDTH] - for the commands ```gender```, ```age```, ```daily```, ```monthly```, ```yearly```, ```countries```, ```districts``` and ```regions```, it lists the data not numerically, but graphically in the form of histograms.

+ COMMAND could be only one:
    * infected - prints count of infected people
    * merge — merges several files with records into one
    * gender - prints count of infected people by gender
    * age - prints count of infected people by age
    * daily - prints count of infected people for individual days
    * monthly - prints count of infected people for individual monthes
    * yearly - prints count of infected people for individual years
    * countries - prints count of infected people for regions(e.g. for Czech Republic - CZ)
    * districts - prints count of infected people for districts
    * regions - prints count of infected people for regions

## Examples
```c++
    $ ./corona infected osoby.csv
    3510360
```
```c++
    $ cat osoby.csv | ./corona gender
    M: 1703679
    Z: 1806681
```
```c++
    $ ./corona -s 20 yearly osoby.csv
    2020: ########
    2021: ####################
    2022: ###########

```
