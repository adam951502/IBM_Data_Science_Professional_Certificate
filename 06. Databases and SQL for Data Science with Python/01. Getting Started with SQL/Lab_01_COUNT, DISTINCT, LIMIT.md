![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/IDSNlogo.png)

Hands-on Lab : COUNT, DISTINCT, LIMIT
=====================================

**Estimated time needed:** 35 minutes

In this lab, you will learn a few useful expressions that are used with SELECT statements. First, you will learn COUNT, which is an aggregate function that retrieves the number of rows that matches the query criteria. Next, you will learn DISTINCT, which is used to remove duplicate values from a specified result set and only return the unique values. Lastly, you will learn LIMIT, which is used for restricting the number of rows retrieved from the table.

  

Software Used in this Lab
-------------------------

In this lab, you will use [Datasette](https://github.com/simonw/datasette?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01) , an open source multi-tool for exploring and publishing data.

  

Database Used in this Lab
-------------------------

The database used in this lab comes from the following dataset source: [Film Locations in San Francisco](https://data.sfgov.org/Culture-and-Recreation/Film-Locations-in-San-Francisco/yitu-d5am?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01) under a [PDDL: Public Domain Dedication and License](https://opendatacommons.org/licenses/pddl/1-0/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01).

  

Objectives
----------

After completing this lab, you will be able to:

*   Retrieve the number of rows that match a query criteria
*   Remove duplicate values from a result set and return the unique values
*   Restrict the number of rows retrieved from a table

  

Exploring the Database
======================

Let us first explore the **SanFranciscoFilmLocations** database using the **Datasette** tool:

1.  If the first statement listed below is not already in the Datasette textbox on the right, then copy the code below by clicking on the little copy button on the bottom right of the codeblock below and then paste it into the textbox of the Datasette tool using either **Ctrl+V** or right-click in the text box and choose **Paste**.
    
        SELECT * FROM FilmLocations;
        
    
    ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/ExploringDB.1.png)
2.  Click **Submit Query**.
    
3.  Now you can scroll down the table and explore all the columns and rows of the **FilmLocations** table to get an overall idea of the table.
    
    ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/ExploringDB.2.png)
4.  These are the column attribute descriptions from the **FilmLocations** table:
    
        FilmLocations(
            Title:              titles of the films, 
            ReleaseYear:        time of public release of the films, 
            Locations:          locations of San Francisco where the films were shot, 
            FunFacts:           funny facts about the filming locations, 
            ProductionCompany:  companies who produced the films, 
            Distributor:        companies who distributed the films, 
            Director:           people who directed the films, 
            Writer:             people who wrote the films, 
            Actor1:             person 1 who acted in the films, 
            Actor2:             person 2 who acted in the films, 
            Actor3:             person 3 who acted in the films
        )
        
    

  

Exercise 1: COUNT
=================

In this exercise, you will first go through some examples of using COUNT in queries and then solve some exercise problems by using it.

Task A: Example exercises on COUNT
----------------------------------

Let us go through some examples of COUNT related queries:

  

1.  In this example, suppose we want to count the number of records or rows of the "FilmLocations" table.
    
    1.  Problem:
        
        > _Retrieve the number of rows from the "FilmLocations" table._
        
    2.  Solution:
        
            SELECT COUNT(*) FROM FilmLocations;
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/1.A.1.4.png)
2.  In this example, now we want to count the number of locations of the films. But we also want to restrict the output resultset in such a way that we only retrieve the number of locations of the films written by a certain writer.
    
    1.  Problem:
        
        > _Retrieve the number of locations of the films which are written by James Cameron._
        
    2.  Solution:
        
            SELECT COUNT(Locations) FROM FilmLocations WHERE Writer="James Cameron";
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    
      
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/1.A.2.4.png)

Task B: Practice exercises on COUNT
-----------------------------------

Now, let us practice creating and running some COUNT related queries.

1.  Problem:
    
    > _Retrieve the number of locations of the films which are directed by Woody Allen._
    
    Hint
    
    > Follow example 2 of the COUNT exercise. Use the WHERE clause comparison operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT COUNT(Locations) FROM FilmLocations WHERE Director="Woody Allen";
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/1.B.1.O.png) 
2.  Problem:
    
    > _Retrieve the number of films shot at Russian Hill._
    
    Hint
    
    > Follow example 2 of the COUNT exercise. Use the WHERE clause comparison operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT Count(Title) FROM FilmLocations WHERE Locations="Russian Hill";
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/1.B.2.O.png) 
3.  Problem:
    
    > _Retrieve the number of rows having a release year older than 1950 from the "FilmLocations" table._
    
    Hint
    
    > Follow example 1 of the COUNT exercise. Use the WHERE clause comparison operator `<` which means **"Less than"**.
    
    Solution
    
        SELECT Count(*) FROM FilmLocations WHERE ReleaseYear<1950;
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/1.B.3.O.png) 

Exercise 2: DISTINCT
====================

In this exercise, you will first go through some examples of using DISTINCT in queries, and then solve some exercise problems by using it.

Task A: Example exercises of DISTINCT
-------------------------------------

Let us go through some examples of DISTINCT related queries:

  

1.  In this example, we want to retrieve the title of all films in the table in such a way that duplicates will be discarded in the output resultset.
    
    1.  Problem:
        
        > _Retrieve the name of all films without any repeated titles._
        
    2.  Solution:
        
            SELECT DISTINCT Title FROM FilmLocations;
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/2.A.1.4.png)

  
  

2.  In this example, we want to retrieve the count of release years of the films produced by a specific company in such a way that duplicate release years of those films will be discarded in the count.
    
    1.  Problem:
        
        > _Retrieve the number of release years of the films distinctly, produced by Warner Bros. Pictures._
        
    2.  Solution:
        
            SELECT COUNT(DISTINCT ReleaseYear) FROM FilmLocations WHERE ProductionCompany="Warner Bros. Pictures";
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/2.A.2.4.png)

Task B: Practice exercises on DISTINCT
--------------------------------------

Now, let us practice creating and running some DISTINCT related queries.

  

1.  Problem:
    
    > _Retrieve the name of all unique films released in the 21st century and onwards, along with their release years._
    
    Hint
    
    > Follow example 1 of DISTINCT. Use WHERE clause comparsion operator `>=` which means **"Greater than or equal to"**.
    
    Solution
    
        SELECT DISTINCT Title, ReleaseYear FROM FilmLocations WHERE ReleaseYear>=2001;
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/2.B.1.O.png) 
2.  Problem:
    
    > _Retrieve the names of all the directors and their distinct films shot at City Hall._
    
    Hint
    
    > Follow example 1 of DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT DISTINCT Title, Director FROM FilmLocations WHERE Locations="City Hall";
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/2.B.2.O.png) 
3.  Problem:
    
    > _Retrieve the number of distributors distinctly who distributed films acted by Clint Eastwood as 1st actor._
    
    Hint
    
    > Follow example 2 of DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT COUNT(DISTINCT Distributor) FROM FilmLocations WHERE Actor1="Clint Eastwood";
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/2.B.3.O.png) 

Exercise 3: LIMIT
=================

In this exercise, you will first go through some examples of using LIMIT in queries and then solve some exercise by using it.

Task A: Example exercises of LIMIT
----------------------------------

Let us go through some examples of LIMIT related queries:

  

1.  In this example, let us retrieve a specific number of rows from the top of the table in such a way that rows other than those are not in the output resultset.
    
    1.  Problem:
        
        > _Retrieve the first 25 rows from the "FilmLocations" table._
        
    2.  Solution:
        
            SELECT * FROM FilmLocations LIMIT 25;
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/3.A.1.4.png)
2.  In this example, let us take the first example to a more advanced level. Now we want to retrieve a specific number of rows from the table, but thid time, not from the top of the table. This time we want to retrieve a specific number of rows starting from a specific row in the table.
    
    1.  Problem:
        
        > _Retrieve the first 15 rows from the "FilmLocations" table starting from row 11._
        
    2.  Solution:
        
            SELECT * FROM FilmLocations LIMIT 15 OFFSET 10;
            
        
    3.  Copy the solution code above by clicking on the little copy button on the bottom right of the codeblock below and paste it to the textbox of the Datasette tool. Then click **Submit query**.
        
    4.  Your output resultset should look like the image below:
        
        ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/3.A.2.4.png)

  

Task B: Practice exercises on LIMIT
-----------------------------------

Now, let us practice creating and running some LIMIT related queries.

  

1.  Problem:
    
    > _Retrieve the name of first 50 films distinctly._
    
    Hint
    
    > Follow example 1 of LIMIT. Use DISTINCT.
    
    Solution
    
        SELECT DISTINCT Title FROM FilmLocations LIMIT 50;
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/3.B.1.O.png) 
2.  Problem:
    
    > _Retrieve first 10 film names distinctly released in 2015._
    
    Hint
    
    > Follow example 1 of LIMIT. Use DISTINCT. Use WHERE clause comparsion operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 10;
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/3.B.2.O.png) 
3.  Problem:
    
    > _Retrieve the next 3 film names distinctly after first 5 films released in 2015._
    
    Hint
    
    > Follow example 2 of the LIMIT exercise to learn how to use OFFSET. Use DISTINCT and use the WHERE clause comparison operator `=` which means **"Equal to"**.
    
    Solution
    
        SELECT DISTINCT Title FROM FilmLocations WHERE ReleaseYear=2015 LIMIT 3 OFFSET 5;
    Output ![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/Labs_Coursera_V5/labs/Lab%20-%20COUNT%20-%20DISTINCT%20-%20LIMIT/images/3.B.3.O.png) 

### Congratulations! You have completed this Lab.

###   

Author(s)
---------

*   [Sandip Saha Joy](https://www.linkedin.com/in/sandipsahajoy/?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01)
  

### © IBM Corporation 2020. All rights reserved.

window.addEventListener('load', function() { snFaculty.inject(); });