# Student Information LangChain Agent

A LangChain agent built with Google Gemini that answers student-related questions using multiple custom tools and a SQLite database.

## Features

The agent can:

- Retrieve student name and department
- Retrieve student marks
- Calculate total and average marks
- Retrieve university passing rules
- Determine whether a student satisfies the passing requirements

## Technologies Used

- Python
- LangChain
- Google Gemini
- SQLite
- Google Colab

## Database

The project uses a SQLite database named `students.db`.

The database contains the following information:

| Student ID | Name | Department | Python | Database | AI | Web |
|---|---|---|---:|---:|---:|---:|
| 22CS045 | Dhanushya | Computer Science | 85 | 72 | 90 | 78 |
| 22CS046 | Rahul | Computer Science | 65 | 70 | 68 | 72 |
| 22CS047 | Priya | Information Technology | 92 | 88 | 95 | 90 |
| 22CS048 | Arun | Information Technology | 55 | 60 | 58 | 62 |
| 22CS049 | Meena | Computer Science | 78 | 85 | 80 | 88 |

## Tools

The agent has four tools:

### 1. `get_student_info(student_id)`

Retrieves:

- Student name
- Department

### 2. `get_student_marks(student_id)`

Retrieves:

- Python mark
- Database mark
- AI mark
- Web mark

### 3. `calculator(expression)`

Used to calculate:

- Total marks
- Average marks

### 4. `get_passing_rules()`

Returns the university passing requirements:

- Minimum overall average: 40%
- Minimum mark in each subject: 35%

## How the Agent Works

The important part of this project is that the tools are not called in a fixed sequence.

The user asks a question:

User Question
      ↓
     Gemini
      ↓
Select required tool
      ↓
     Tool
      ↓
   Tool result
      ↓
     Gemini
      ↓
Need another tool?
      ↓
     Tool
      ↓
   Final Answer

The LLM decides which tools are required based on the question.

## Example Questions

### Student Information

```text
What is the name and department of student 22CS045?
