# Fakebook JDBC

## Overview
This project implements a Java application that executes SQL queries against a relational database using JDBC and processes the results into structured data objects. The goal is to practice writing correct, efficient SQL queries and integrating them into a real database-backed application.

The application queries a “Fakebook” dataset (a Facebook-like social network schema) and answers a series of analytical questions about users, friendships, photos, events, and social relationships.

---

## Project Structure
The project is built on top of provided starter code. The overall directory structure is unchanged from the starter files.

Key files:
- **StudentFakebookOracle.java**  
  Main implementation file. All required SQL queries are written and executed here.
- **FakebookOracle.java**  
  Abstract base class defining the required query interfaces and output formatting.
- **FakebookOracleDataStructures.java**  
  Custom data structures used to store and report query results.
- **FakebookOracleUtilities.java**  
  Utility classes for handling result lists and formatted output.
- **PublicFakebookOracleConstants.java**  
  Defines schema names and table references (must not be modified).
- **FakebookOracleMain.java**  
  Application driver for running queries and measuring runtime.
- **Makefile**  
  Used to compile, run queries, and measure performance.

---

## Dataset
The Fakebook dataset is stored in an Oracle database and includes the following public tables:

- Public_Users  
- Public_Friends  
- Public_Cities  
- Public_User_Current_Cities  
- Public_User_Hometown_Cities  
- Public_Programs  
- Public_Education  
- Public_User_Events  
- Public_Albums  
- Public_Photos  
- Public_Tags  

Friendship relationships are stored with the invariant `user1_id < user2_id`, ensuring no duplicates or self-friendships.

---

## Implemented Queries
The project requires implementing **9 SQL queries** (Query 1–Query 9). Each query is implemented in its corresponding method in `StudentFakebookOracle.java`.

The queries cover tasks such as:
- Identifying longest/shortest and most common first names
- Finding users with no friends
- Comparing current city vs. hometown
- Identifying highly tagged photos
- Suggesting potential friendships based on shared attributes
- Computing mutual friends
- Analyzing event-heavy states
- Finding oldest and youngest friends
- Identifying potential sibling relationships

Each query:
- Executes SQL through JDBC
- Processes results using provided data structures
- Ensures correct ordering, formatting, and handling of edge cases
- Is designed to work on both public and private datasets

---

## Implementation Notes
- SQL queries are written to offload as much computation as possible to the database (e.g., joins, grouping, sorting).
- Table names are referenced **only** through constants provided in `PublicFakebookOracleConstants.java` (no hard-coded table names).
- Additional tables are not created; temporary views may be created and dropped when needed.
- JDBC resources (Statements and ResultSets) are carefully managed and closed to avoid runtime errors.
- Performance considerations are taken into account to meet autograder time limits.

---

## Compilation and Execution
From the project root directory:

```bash
make compile
