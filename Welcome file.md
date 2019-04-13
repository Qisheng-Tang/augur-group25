Welcome to the augur-group25 wiki!

Ryan Stephens, Matt Rockey, Qisheng Tang

Deployment Environment:
http://ec2-18-217-244-45.us-east-2.compute.amazonaws.com:3333

Functional Requirements:

## Use Case #1: Lines Changed by Week (Facade)
### User Requirements for a Contributor
* Contributors shall be able to push changes to the projects repository.
### Functional Requirements for a Contributor
* The system shall be able to display all lines changed per week per project
* Contributors shall be able to modify their usernames and passwords
### User Requirements for a Community Manager
* Community manager shall be able to view number of lines changed as a weekly report format.
### Functional Requirements for a Community Manager
* The system shall be able to display weekly report as several statistic graphs
* The system shall be able to support JavaScript as programming language
* The system shall be able to store report's title, content
* The system shall be able to set automatic generate time for report
* The community manager shall be able to set his/ her passwords
* The community manager shall be able to modify his/ her user name

## Use Case #2: Total Lines Changed (GithubAPI)
### User Requirements for a Contributor
* Contributors shall be able to submit changes to projects
### Functional Requirements for a Contributor
* The system shall be able to display all lines changed total per project
* Contributors shall be able to modify their usernames and passwords
### User Requirements for a Community Manager
* Community manager shall be able to view number of total lines changed as a report format.
### Functional Requirements for a Community Manager
* The system shall be able to display report in a statistic graph.
* The system shall be able to support JavaScript as programming language
* The system shall be able to store report's title, content
* The system shall be able to set automatic generate time for report
* The community manager shall be able to set his/ her passwords
* The community manager shall be able to modify his/ her username
## Use Case #3: Lines Changed by Month (Facade)
### User Requirements for a Contributor
* Contributors shall be able to push changes to the projects repository.
### Functional Requirements for a Contributor
* The system shall be able to display all lines changed per month per project
* Contributors shall be able to modify their usernames and passwords
### User Requirements for a Community Manager
* Community manager shall be able to view number of lines changed as a monthly report format.
### Functional Requirements for a Community Manager
* The system shall be able to display monthly report as several statistic graphs
* The system shall be able to support JavaScript as programming language
* The system shall be able to store report's title, content
* The system shall be able to set automatic generate time for report
* The community manager shall be able to set his/ her passwords
* The community manager shall be able to modify his/ her user name


Database ER Diagram:

![ERD-Group25](https://lh3.googleusercontent.com/RswN4RrBjIcxFhMV9GTKd7TKoG0imQ9CPNdAdZqRq0HvLREj7i4I8eEvQTLMnDX1a97TAUJIYN32 "ERD")

Database Description Language (SQL):

CREATE TABLE `Repo` (
	`Repo_ID` INT NOT NULL AUTO_INCREMENT,
	`Project_ID` INT NOT NULL,
	`Git` VARCHAR NOT NULL,
	`Added` DATE NOT NULL,
	`Path` VARCHAR NOT NULL,
	`Status` VARCHAR NOT NULL,
	PRIMARY KEY (`Repo_ID`)
);

CREATE TABLE `Repo_Info` (
	`RepoInfo_ID` INT NOT NULL AUTO_INCREMENT,
	`Name` VARCHAR NOT NULL,
	`URL` VARCHAR NOT NULL,
	`Goals` TEXT NOT NULL,
	`Repo_ Description` TEXT NOT NULL,
	PRIMARY KEY (`RepoInfo_ID`)
);

CREATE TABLE `Repo_Metadata` (
	`Commit_ID` INT NOT NULL AUTO_INCREMENT,
	`Contributor_Name` VARCHAR NOT NULL,
	PRIMARY KEY (`Commit_ID`)
);

CREATE TABLE `Commit_Metadata` (
	`Commit` INT NOT NULL AUTO_INCREMENT,
	`Total_Lines_Changed` INT NOT NULL,
	`Timestamp` DATE NOT NULL,
	`Commit_Comment` TEXT NOT NULL,
	`Commit_Description` TEXT NOT NULL,
	PRIMARY KEY (`Commit`)
);


Source Code:

AugurAPI.js - added two new timeseries metrics for “Lines Changed by Week” and “Lines Changed by Month”. These are then connected to the graph stubs in the ExperimentalCard.vue file.


----------------------------------------------------------------------------------------------------------------------------

ExperimentalCard.vue - added graph stubs for both “Lines Changed by Week” and “Lines Changed by Month” in the ExperimentalCard.vue file. We then connected the timeseries metric from AugurAPI.js to the graph stubs.


----------------------------------------------------------------------------------------------------------------------------

GrowthMaturityDeclineCard.vue - added graph stubs for “Lines of Code Changed” in the GrowthMaturityDeclineCard.vue file. The timeseries for lines_changed was already implemented in the AugurAPI.js so it was easy to connect to the graph stub.






Needed Languages and Skill to Grasp:
SQL:
	We will need SQL to write queries to retrieve data from the Augur database.  We can use this data to perform our functions and display the data we need.  There are some queries in the data source files we can refer to for help and we can we have a layout of the Augur database that we can use to help guide us in accessing its data. 

      2. HTML:
          This will include javascript.  This is necessary for the front end piece of our project.  The data we grab using SQL needs to be displayed, which can be done using HTML and JS.  For the most part we will be using html to just display the data we grab in our functions and put it into charts.  
      3. Python: 
          We will need this language to create our functions for the most part, this will be used to define function parameters, make SQL calls, and put the logic into functions.

Skill Gaps:
None of us are familiar with python, but we can use the ghtorreny.py file as an aid because it is full of examples for us to refer to.  For our stubs we can just follow the format of other functions and get our project a good starting point.

Who is Doing What:
Matt Rockey: created the SQL file and ERD for this doc.  Will work on the stubs in the facade.py and GithubAPI.py files.
	
Ryan Stephens: defined languages and skill gaps for project.  Will work on Python stubs and connecting them to HTML.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk2Njg5MDA2MCwyMDQxMDA4NjM5XX0=
-->