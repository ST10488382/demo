## Student Information
- Student Name: Sphetho
- Student Number: ST10488382
- Institution: Rosebank College / The Independent Institute of Education (IIE)
- Module: Programming
- Submission: Part 3 POE


## How to run the project
1. Open the solution file (.sln) in Visual Studio
2. Make sure all NuGet packages are restored (right click solution → Restore NuGet Packages)
3. Add your logo image named logo.png to the project root and set it to Resource
4. Add your greeting audio named greet.wav to the project root
5. Press F5 or click the Start button to run

## How to use the app
1. Click Get Started on the home screen
2. Enter your username and click Continue
3. You will land on the Chat page — type any cybersecurity question and press Ask
4. To add a task type: add task (your task name)
5. The bot will ask how many days — reply: yes remind me in (number) days
6. Click Task Reminders in the menu to see your tasks
7. Double click a task to mark it done, double click again to delete it
8. Click Activity Log to see everything that happened in the app
9. Click Game to take the cybersecurity quiz

## Project structure

# CyberGuard AI — Cybersecurity Awareness Chatbot

## What is this?
CyberGuard AI is a desktop application built with C# and WPF. It is a cybersecurity awareness chatbot that helps users learn how to stay safe online. It includes a chat assistant, task reminders, an activity log, and a cybersecurity quiz game.

## Features
- **Chat** — ask questions about cybersecurity topics like phishing, passwords, firewalls, VPNs and more
- **Task Reminders** — add tasks and set due date reminders, stored in a local database
- **Activity Log** — tracks everything you do in the app automatically
- **Quiz Game** — test your cybersecurity knowledge with multiple choice questions
- **Memory** — the chatbot remembers your name and your interests across sessions
- **Voice Greeting** — plays an audio greeting when the app starts

## Requirements
- Windows 10 or 11
- Visual Studio 2019 or later
- .NET Framework 4.7.2 or later
- Microsoft.ML NuGet package
- SQL Server LocalDB (comes with Visual Studio)

## How to set up the database
1. Open Visual Studio
2. Go to View → SQL Server Object Explorer
3. Expand (localdb)\MSSQLLocalDB
4. Right click on the connection → New Query
5. Paste and run this:

```sql
CREATE DATABASE prog_tasks;
GO
USE [prog_tasks];
GO
CREATE TABLE demo_tasks (
    task_id          INT IDENTITY(1,1) PRIMARY KEY,
    task_name        VARCHAR(100) NOT NULL,
    task_description VARCHAR(100) NOT NULL,
    task_dueDate     VARCHAR(20),
    task_status      VARCHAR(20) DEFAULT 'pending'
);
GO
```

6. In tasks.cs, make sure your connection string is: