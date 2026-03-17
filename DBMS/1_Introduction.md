# LEC-1: Introduction to DBMS

---

## 1. What is Data?

- Data is a collection of **raw, unorganized facts and details** like text, observations, figures, symbols, and descriptions of things etc.
- Data does not carry any specific purpose and has **no significance by itself**.
- Data is measured in terms of **bits and bytes** – which are basic units of information in the context of computer storage and processing.
- Data can be recorded and doesn't have any meaning unless processed.

---

## 2. Types of Data

### a. Quantitative

- Numerical form
- E.g., Weight, volume, cost of an item.

### b. Qualitative

- Descriptive, but not numerical.
- E.g., Name, gender, hair color of a person.

---

## 3. What is Information?

- Information is **processed, organized, and structured data**.
- It provides **context** of the data and enables **decision making**.
- Processed data that makes sense to us.
- Information is extracted from data by **analyzing and interpreting** pieces of data.

> **Example:** You have data of all the people living in your locality — that's _Data_. When you analyze and interpret that data and conclude:
>
> - There are 100 senior citizens.
> - The sex ratio is 1.1.
> - Newborn babies are 100.
>
> These conclusions are _Information_.

---

## 4. Data vs Information

| **Data**                                          | **Information**                                    |
| ------------------------------------------------- | -------------------------------------------------- |
| Collection of raw facts                           | Facts put into context                             |
| Raw and unorganized                               | Organized and structured                           |
| Individual, sometimes unrelated points            | Maps data to provide a big-picture view            |
| Meaningless on its own                            | Meaningful — analyzed and interpreted              |
| Does not depend on information                    | Depends on data                                    |
| Presented as graphs, numbers, figures, statistics | Presented through words, language, thoughts, ideas |
| Insufficient for decision-making                  | Can be used to make decisions                      |

---

## 5. What is a Database?

- A **Database** is an electronic place/system where data is stored in a way that it can be easily **accessed, managed, and updated**.
- To make real use of data, we need **Database Management Systems (DBMS)**.

---

## 6. What is DBMS?

- A **Database Management System (DBMS)** is a collection of interrelated data and a set of programs to access those data.
- The collection of data, usually referred to as the **database**, contains information relevant to an enterprise.
- The primary goal of a DBMS is to provide a way to **store and retrieve** database information that is both **convenient and efficient**.
- A DBMS is the database itself, along with all the software and functionality.
- It is used to perform different operations: **addition, access, updating, and deletion** of data.

---

## 7. DBMS vs File Systems

File-processing systems have major disadvantages — these are also the **advantages of DBMS** (i.e., reasons to use DBMS):

| #   | Problem in File Systems                                                                               | How DBMS Solves It                                                  |
| --- | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| 1   | **Data Redundancy and Inconsistency** — same data stored in multiple places, leading to inconsistency | DBMS centralizes data, reducing redundancy and ensuring consistency |
| 2   | **Difficulty in Accessing Data** — need custom programs for every new query                           | DBMS provides query languages (e.g., SQL) for easy data access      |
| 3   | **Data Isolation** — data scattered in various files and formats                                      | DBMS integrates data in a unified structure                         |
| 4   | **Integrity Problems** — hard to enforce data constraints                                             | DBMS enforces integrity constraints at the system level             |
| 5   | **Atomicity Problems** — partial updates can leave data in inconsistent state                         | DBMS ensures atomic transactions (all-or-nothing)                   |
| 6   | **Concurrent-Access Anomalies** — simultaneous access can corrupt data                                | DBMS handles concurrency control to prevent conflicts               |
| 7   | **Security Problems** — difficult to apply fine-grained access control                                | DBMS provides robust authentication and authorization mechanisms    |

---
