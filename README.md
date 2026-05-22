# C# Log Analyzer

## Overview

C# Log Analyzer is a beginner-friendly security log analysis tool built with C#. The program reads a text-based log file, identifies important activity, counts events, tracks failed login attempts by IP address, flags suspicious activity, and exports a report.

This project was created as part of my internship preparation to practice C#, file handling, dictionaries, basic log analysis, and report generation.

## Features

- Reads a `.txt` log file
- Counts failed login attempts
- Counts warnings
- Counts errors
- Tracks failed login attempts by IP address
- Flags suspicious IP addresses with repeated failed login attempts
- Generates a full text report
- Exports the report to a `.txt` file
- Uses basic error handling with `try/catch`
- Checks if the log file exists before running

## Skills Practiced

- C#
- File input/output
- Strings
- Loops
- If/else statements
- Dictionaries
- Error handling
- Basic security log analysis
- Report generation
- Git/GitHub project documentation

## Sample Log Format

2026-06-01 08:15 INFO User john logged in successfully
2026-06-01 08:21 WARNING Multiple failed login attempts detected
2026-06-01 08:22 FAILED LOGIN User admin from 192.168.1.25
2026-06-01 08:23 FAILED LOGIN User admin from 192.168.1.25
2026-06-01 08:45 ERROR Unable to connect to database

## Example Report Output

Log Analysis Report:
---------------------------
Failed Logins: 55
Warnings: 38
Errors: 25

Failed Login Attempts:
----------------------------
192.168.1.25: 9
192.168.1.30: 6
45.83.12.90: 6

Suspicious Activity:
----------------------------
192.168.1.25: 9
192.168.1.30: 6
45.83.12.90: 6
