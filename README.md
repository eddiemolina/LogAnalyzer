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
- String parsing
- Loops
- If/else statements
- Dictionaries
- Error handling
- Basic security log analysis
- Report generation
- Git/GitHub project documentation

## Running the Application

### Prerequisites

- [Visual Studio](https://visualstudio.microsoft.com/) with the .NET desktop development workload, or
- [.NET SDK](https://dotnet.microsoft.com/download)

### Option 1: Visual Studio

1. Clone or download this repository.
2. Open `LogAnalyzer.slnx` in Visual Studio.
3. Build the solution.
4. Click **Start** to run the application.

### Option 2: .NET CLI

1. Clone the repository:

   ```bash
   git clone YOUR_REPOSITORY_URL
   cd LogAnalyzer
   ```

2. Navigate to the project directory:

   ```bash
   cd LogAnalyzer
   ```

3. Build the project:

   ```bash
   dotnet build
   ```

4. Run the application:

   ```bash
   dotnet run
   ```

### Sample Input

The repository includes `sample-log.txt`, which contains example security log entries for testing.

The application reads the configured log file, analyzes its contents, and generates a text report.

Make sure the sample log file is available at the path expected by the application.

## Sample Log Format

```text
2026-06-01 08:15 INFO User eddie logged in successfully
2026-06-01 08:21 WARNING Multiple failed login attempts detected
2026-06-01 08:22 FAILED LOGIN User admin from 192.168.1.25
2026-06-01 08:23 FAILED LOGIN User admin from 192.168.1.25
2026-06-01 08:45 ERROR Unable to connect to database
2026-06-01 09:10 INFO Backup completed successfully
2026-06-01 09:30 WARNING Disk space running low
2026-06-01 10:00 FAILED LOGIN User test from 192.168.1.30
```

## Example Report Output

```text
Log Analysis Report:
---------------------------
Failed Logins: 4
Warnings: 2
Errors: 1

Failed Login Attempts:
----------------------------
192.168.1.25: 2
192.168.1.30: 1

Suspicious Activity:
----------------------------
192.168.1.25: 2
```

## How It Works

The program reads each line from a log file and checks whether the line contains specific keywords:

- `FAILED LOGIN`
- `WARNING`
- `ERROR`

When a failed login is found, the program extracts the IP address from the end of the line and stores it in a dictionary.

The dictionary uses this structure:

```text
IP Address → Number of Failed Login Attempts
```

Example:

```text
192.168.1.25 → 2
192.168.1.30 → 1
```

If an IP address appears more than once, the program flags it as suspicious activity.

## Future Improvements

Possible improvements include:

- Let the user type the log file path instead of hardcoding it
- Export the report as a `.csv` file
- Sort IP addresses by highest failed login count
- Add severity levels such as Low, Medium, and High
- Detect failed login attempts by username
- Add timestamps to suspicious activity
- Create a simple GUI version
- Add unit tests
- Connect the project to real Windows Event Logs
