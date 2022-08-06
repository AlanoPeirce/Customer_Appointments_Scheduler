# Customer Appointments Scheduler

This Customer Appointments Scheduler is an application designed for the Langley Consulting Group ("LCG" – a fictitious company) for the purpose of maintaining customer records and scheduling appointments for those customers.

Appointments and customer records can be added, updated, and deleted using the application; all of these records will be stored in LCG's database.


## Features

* **Database storage.** The application is designed to be linked to LCG's database, and all appointment and customer records created in the application will be stored in this database. Because of this, all changes made to those records (including deletion) will be reflected in the database.
    
- **Generation of statistical reports.** The application generates three main reports. In order to view these reports,  please click on the "Appointments" button after logging into the application; then, click on the "Statistics" button in the lower left corner of the screen.
	- <ins>Report 1</ins>: The first report displays the number of appointments scheduled, sorted by both type and month.
	- <ins>Report 2</ins>: The second report displays an appointment schedule for each business contact listed in LCG's database.
	- <ins>Report 3</ins>: The third report displays the number of appointments currently scheduled for each customer; this list is in descending order.

* **Automatic time zone detection.** The time zone of the user is automatically detected, and all dates and times within the application are displayed in the user's time zone.
	
* **Automatic language translation.** The entire application automatically translates to French if it detects that the user of the application is currently in a French-speaking locale.
	
* **Record of all login attempts.** All login attempts are recorded in the file named "login_activity.txt". The details of these attempts are also recorded, including whether the attempt was successful or unsuccessful, the username used during the login attempt, and the date and time the attempt occurred.

* **Upcoming appointment notifications.** After the user logs into the application, a notification appears informing the user whether or not they have an appointment within the next fifteen minutes; if they do, the details of those appointment(s) are listed.
	
* **Overlapping appointment protection.** If a user attempts to schedule an appointment for a customer who already has an appointment during the specified timeframe, the application warns the user of this and does not allow the appointment to be scheduled.
	
* **Awareness of business hours.** If a user attempts to schedule an appointment outside of LCG's business hours (currently 8 AM to 10 PM EST), the application warns the user of this and does not allow the appointment to be scheduled.
	
* **Extensive code documentation.** The application code includes detailed Javadoc comments above every class, method, and variable, and there are even more detailed (non-Javadoc) comments explaining certain snippets of code; this comprises extensive and easily-understandable documentation.
	
* **Many other features.** The application includes many other features and error-checking attributes that have not been named here.



## Installation

### <ins>Before installing</ins>

Please ensure that your systems match the following criteria.

1. **Operating System:** 
	* Windows 10

2. **IDE (Integrated Development Environment):**
	* Apache Netbeans 12.6

3. **Database specifications:**
	* <ins>Protocol:</ins> JDBC
	* <ins>Vendor:</ins> MySQL
	* <ins>Location (relative to the program file):</ins> //localhost/
	* <ins>Database name:</ins> client_schedule
	* <ins>Database driver:</ins> mysql-connector-java-8.0.25
	* <ins>Database username:</ins> sqlUser
	* <ins>Database password:</ins> Passw0rd!

4. **Database layout:**
	* Your database must conform to the following ERD diagram:
	&nbsp;   &nbsp;   &nbsp;   &nbsp;   &nbsp;   <img src="https://i.imgur.com/3irClaD.png" alt="ERD diagram of required database layout"><p></p>
	* Furthermore, the contents of each table in the database must match the following descriptions:<p></p>
		* The <ins>Countries</ins> table must be pre-populated with the countries in which LCG does business.
		* The <ins>First_Level_Divisions</ins> table must be pre-populated with the first-level divisions (e.g. states or provinces) of each of those countries.
		* The <ins>Users</ins> table must be pre-populated with the user accounts that are authorized to access the application.
		* The <ins>Contacts</ins> table must be pre-populated with the business contacts of LCG.
		* The <ins>Customers</ins> and <ins>Appointments</ins> tables *may* be pre-populated with customer records and appointment records (respectively), but this is NOT a requirement. These tables will be the storage locations for any customer and appointment records that are created using the application.

5. **Other prerequisites:**
	* Please follow the instructions below so that the application can accurately detect users' time zone.<p></p>
	
		<div>
		    <ol type="a">
		        <li>
			    Click on the Start icon of your computer and select the "Settings" application.<p></p>
			    <details>
			        <summary><b>&nbsp;Show image</b></summary>
			        <br>
			        &nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/ocOKayp.png" alt="Settings icon in the Start Menu" width=35%><p></p>
			    </details>
			</li>
			<li>
			    Once the setting application opens, select the "Time and Language" option.<p></p>
			    <details>
			        <summary><b>&nbsp;Show image</b></summary>
			        <br>
			        &nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/9VChGDF.png" alt="Time and Language option in the Settings app" width=75%><p></p>
			    </details>
			</li>
			<li>
			    Next, select the "Date & time" tab.<p></p>
			    <details>
			        <summary><b>&nbsp;Show image</b></summary>
			        <br>
			        &nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/duZ90LL.png" alt="Date & time tab in the Settings app" width=33%><p></p>
			    </details>
			</li>
			<li>
			    Finally, scroll down within the "Date & time" tab to look for the "Adjust for daylight saving time automatically" option. Please ensure 				that the toggle switch associated with this option is set to "On".<p></p>
			    <details>
			        <summary><b>&nbsp;Show image</b></summary>
			        <br>
			        &nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/sMG0Hcn.png" alt="DST toggle option in the Settings app" width=75%><p>&nbsp;</p>
			    </details>
			</li>
		    </ol>
		</div>
		&nbsp;

### <ins>Installation instructions</ins>

1. Starting from <a href="https://github.com/AlanoPeirce/Customer_Appointments_Scheduler">the main project page on Github</a>, click on the green "Code" button that appears above the upper right corner of the application files (see blue rectangle below).<p></p>
From the drop-down menu that opens, click "Download ZIP" (see red rectangle below). This will download the application onto your computer as a ZIP file.<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/KQmp87l.png" alt="How to download application files from Github" width=90%><p>&nbsp;</p>

2. Open up NetBeans and click on File -> Import Project -> From ZIP.<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/lSEA6V1.png" alt="How to import project into NetBeans"><p>&nbsp;</p>

3. A popup window will appear. On this popup window, click the "Browse" button that appears next to the "ZIP File:" label (see image below).<p></p>
Now, navigate through your local directories to find the ZIP file that you downloaded in step 1. Open and then import this ZIP file.<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/6rEBl5e.png" alt="NetBeans import project popup window"><p>&nbsp;</p>

4. Now, you can build the project. To do this, first highlight the project file by clicking on it (see rectangle #1 in the image below). Then, click the "Clean and Build" button (see rectangle #2).<p></p>
After waiting for the project to finish building, you should see a message in the Output window that says "BUILD SUCCESSFUL" (see rectangle #3).<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/c0PH2H0.png" alt="How to build NetBeans project" width=90%><p>&nbsp;</p>

5. Lastly, you need to run the project. Make sure the project file is still highlighted from step 4 — then, click on the "Run" button (which looks like a green arrow) in NetBeans' toolbar.<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/GWZ8jKd.png" alt="NetBeans Run button"><p>&nbsp;</p>

6. The application should now start up! The first page you should see is the login page of the application, which looks like this:<p></p>
&nbsp;   &nbsp;   &nbsp;<img src="https://i.imgur.com/mmHjG3x.png" alt="Login page of application"><p>&nbsp;</p>


## Usage


 •  AUTHOR: The author of this application is Alian Peirce.
    CONTACT INFORMATION: The author may be reached at the email apeirc2@wgu.edu .
    STUDENT APPLICATION VERSION: This is application version 1.0 .
    DATE: The current date is 08/01/2022.



 •  IDE SPECIFICATIONS: The IDE used for this project is Apache Netbeans 12.6 .
    JDK SPECIFICATIONS: The version of JDK used is Java SE 17.0.2 .
    JAVAFX SPECIFICATIONS: The version of JavaFX used is JavaFX-SDK-17.0.1 .



 • INSTRUCTIONS FOR RUNNING THE PROGRAM: 

   Before running the program, if you are planning to run it in Windows 10 (and perhaps 
   Windows in general), please make sure to go to the Windows settings, navigate to 
   the "Date & time" section, and ensure that the "Adjust for daylight saving time 
   automatically" option is turned on. If it is left off, the java.time package will 
   NOT work correctly - it will output something like "GMT-07:00" anytime an attempt 
   is made to output the display name of the local time zone or the local zone ID.
  
   Additionally, please make sure you have a database installed that matches the 
   ERD diagram and has the following specifications:
  
       ◦  Protocol: JDBC
       ◦  Vendor: MySQL
       ◦  Location (relative to the program file): //localhost/
       ◦  Database name: client_schedule
       ◦  Database driver: mysql-connector-java-8.0.25
       ◦  Database username: sqlUser
       ◦  Database password: Passw0rd!

   The application also expects that the database already contains certain populated 
   tables; these tables contain business data necessary for the application to 
   function properly. These expected tables must be named Contacts (referring to the 
   business's contacts), Countries (referring to the countries in which the business 
   operates), First_Level_Divisions (referring to the first-level divisions of the 
   given Countries), and Users (a.k.a. the accounts that are allowed access to the 
   application).
  
   Once all the prerequisites are met, all that is left to do is import the project 
   ZIP file into Netbeans, build the project, and then execute it.



 •  MySQL CONNECTOR DRIVER VERSION NUMBER:
    The driver version number is mysql-connector-java-8.0.25


