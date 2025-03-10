# What is SQLi?
SQLi is a web app vulnerability that allows threat actors to input queries to a database. This allows for attackers to view hidden data including private information of users. 

# Detecting SQLi 
Systematic tests against every entry point in the application can be used to detect SQLi. Here are some simple items testers can use:
- a single quote '
- Boolean conditions
- Payloads designed for triggering time delays
- OAST payloads designed to trigger out of band network interaction when executed within a SQL query.
- Burp Scanner

# Retrieving Data
Most SQLi occur within WHERE and SELECT statements. They can also occur in these:
- UPDATE with updated values or the WHERE clause 
- INSERT within inserted values
- SELECT within table or column name
- SELECT within ORDER BY

  # Lab 1: Using SQLi in WHERE clause
  ~~~
  category=Corporate+gifts%27%20OR%201=1--
  ~~~
  # Lab 2: Bypassing Login
  ~~~
  Login:
  Administrator'--

  Password:
  Random Characters?
  ~~~

  # SQLi Union Attacks
  UNION is an operator that combines results from two or more SELECT statements. Here is some example code:
  ~~~
  SELECT a, b FROM table1 UNION SELECT c, d FROM table2
  ~~~
  For this query to work, two conditions must be met: individual queries must return the same columns and data types in each column must be compatible between both queries. TO determine column numbers,
  attackers can use the ORDER BY clause to increment column index until an error occurs.
  ~~~
  ' ORDER BY 1--
  ' ORDER BY 2--
  ~~~

  

  
