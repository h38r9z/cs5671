java cCoursework 2: Database + web interface project
Due date – 13th December 2024, submitted via Moodle
Coursework 2 is INDIVIDUAL WORK
Coursework Deliverables 
WARNING: If you submit any non-ZIP formatted archives instead of ZIPs (e.g., RAR) your submission may appear corrupt to markers and therefore parts of it could receive ZERO marks.
Overview. You must provide the following deliverables in a single directory, ZIPped up and submitted by the due date. You must submit the following core directory structure with the following labels (replacing yourusername and studentID with your university username and your student ID number respectively):
COMP4039-CW2-yourusername-studentID/     [dir]
├── yourusername-studentID_CW2_cover.txt [txt file]
├── yourusername-studentID_Docker/       [dir]
│   ├── html/cw2/index.php               [php file]
│   ├── html/cw2/...                     [other files]
│   ├── mariadb/cw2-database.sql         [phpMyAdmin export]
│   └── mariadb-data/                    [dir]
├── yourusername_Technical.pdf           [pdf file]
└── yourusername_UserManual.pdf          [pdf file]
To summarise, you must include:
-A cover text called yourusername-studentID_CW2_cover.txt
-html/cw2/index.php as the entry point into the system
-The contents of your mariadb-data directory (this contains your working databse)
-mariadb/cw2-database.sql i.e., an export from phpMyAdmin of your Coursework 2 database schema (that you have adapted from what was provided to you)
-Two manuals in PDF form

Hint:

Further details elaborating the Overview. In your ZIP file: 
The cover text file (named yourusername-studentID_CW2_cover.txt) must contain your name, your student ID and your username (please use .txt / plain text file format). In this file you should provide a list of all the core files you submitted for this coursework, i.e., including the full contents of the html directory. NOTE: There is no need to include the contents of mariadb-data!
yourusername-studentID_CW2_cover.txt must also list  specify the origin of ALL resources (e.g., frameworks, assets, styles, JS libraries, code adapted / used from internet sources, code generators, etc.) that you have used that are not solely your own work. Please also include references to resources you have used in comments within your code. If you do not do so we may consider the absence of such a declaration as indicating academic misconduct. 
The copy of your Docker directory (i.e., yourusername-studentID_Docker) must contains all necessary files so that it can be run on an equivalent Docker instance (i.e., based off the github Docker configuration provided). The safest way to ensure this is simply to rename dis-docker-main to yourusername-studentID_Docker and include the whole Docker directory in your submission, as noted above.
You must include the SQL definitions file that describes your database and data i.e., mariadb/cw2-database.sql. You must also include your working database as found in the mariadb-data directory. This is so that we can reconstruct your database using phpMyAdmin or simply deploy it in our own Docker instance; including both forms ensures redundancy during marking. If you are unsure how to export your database, you will need to click on your database in phpMyAdmin to export in the left panel, then select the Export tab (if you are unsure still, use Google to search for this operation – it is very simple). If SQL files are not present we may be unable to mark your coursework and you will receive ZERO marks.
The two documentation files (PDF only please or else these components will be marked ZERO) are described in the specification below in greater detail.
Late submissions will be accepted, but they will be penalised at the University standard rate of 5% per working day. 
It is assumed you have read and understood the module’s Academic Misconduct Policy document.
Coursework Specification
The coursework scenario is described in the associated file in Moodle – coursework-2-scenario.docx. You will need a database definition and data, a draft version of which is provided in Moodle as coursework-2-database.sql (also available in your Docker in mariadb/2_coursework-2-database.sql). Note this will need modification and extension. 

The task is to create a usable end to end system that will allow police officers to record and retrieve information about vehicles, people and traffic incidents. Although the database provided is small you should consider how your design solutions would scale to a much larger amount of data. It is important to provide a task-focussed interface that supports required user tasks, not simply an administration interface to database tables.

You must implement an interactive web frontend for your database using PHP, PHP’s SQL interface, and HTML (as well as other technologies such as CSS or JavaScript, as you see fit).
This package / your system should be installable on any machine with a MySQL / Apache / PHP stack (e.g., LAMP)—so you should avoid absolute pathnames and you should use header files to ensure configuration (e.g., MySQL hostname etc.) is held in one file only. For example, see db.inc.php in the PHP demo code available on Moodle (use require("path/to/db.inc.php") in your other PHP files to include this common header.
We will be using Google Chrome (available on CS machines) to test your coursework (so make sure web interface elements function correctly in that browser).
Marking criteria
Coursework 2 is worth a total of 70% of the total marks for this module. Coursework 2 is marked out of 100. The mark will be scaled to provide the final mark for this coursework. Most marks are allocated for specific required features, although to achieve the higher end of marking we encourage you to go beyond what is required. There are a few general mark categories that are awarded for the coursework as a whole which will also benefit from creatively going beyond the bare minimum of functionality specified in the questions. Finally, we note that marking will take into account specific code fragments (e.g., PHP, SQL, JS, etc.) that you have been provided with by convenors. 

Marking criteria for features/requirements
0 (zero)	1-3	4-5	6-7	8-9	10
No attempt is made to implement this feature. 
No documentation	An attempt has been made to implement the feature, but it is significantly flawed in some way, and there is no evidence that this approach will fulfil the requirements of the specification. 
Flawed or very incomplete documentation	The approach is fundamentally sound, but may include some flaws, such as not producing the correct results. 
Functionality that mostly works but include some bugs or problematic methods of implementation would fall into this category.
UI elements may have inconsistencies or other flaws.
Basic documentation, although perhaps lacking structure or richness.	Implementation works and produces the expected results, meets and moderately exceeds core functionality required. 
UI elements are well designed and代 写program、Java
代做程序编程语言 implemented correctly to support flexible interaction with the database, as well as other aspects such as error handling, feedback, etc. 
Underlying SQL takes full advantage of querying flexibility and combines multiple data sources where relevant. 
Documentation is well presented and clear.	Previous requirements are met, but offers substantive additional functionality beyond this. More advanced use of styling and dynamic elements (e.g., application of JS). Overall implementation and UI should be of fairly high quality, but it is likely to lack the polish of a professional solution.
Documentation approaching professional standard.	Previous requirements are met, and the code and its structure are of very high quality, well documented and easily reusable.
Implementation including UI of professional production quality, follow standard usability guidelines and practices. Goes significantly and creatively beyond core functionality.
Documentation should be of production level quality.

Core required features [76 marks total]
NOTE: For each core required feature, relevant aspects of the UI will be taken into account, with an additional overall assessment provided under “Other required features” (below).
1.A police officer should be able to log into the system using one of the following usernames/password combinations: 
Username	Password
mcnulty	plod123 
moreland 	fuzz42 

Once logged in the police officer should have the ability to manage their account with a reasonable number of basic functionality, e.g., change their password, log out, etc. 
IMPORTANT NOTE – in any real world system involving a database and web frontend, security would be paramount. However, addressing security is beyond the scope of this module, so you should ignore this. For example, usernames and passwords can be stored as plain text fields in your database – do not attempt to encrypt them or secure your database in any way. 
[10 marks]

2.The police officer should be able to flexibly search for / look up people by their names or their driving licence number and retrieve information related to the person(s). If the person is not in the system you should provide an appropriate message.
[6 marks]

3.The police officer should be able to flexibly search for / look up vehicle registration (plate) numbers. The system will then show car details and related information (e.g., the owner’s name and license number, associated incidents including who was involved as it may not be the owner, etc.). Allow for missing data in the system (e.g., the vehicle might not be in the system, or the vehicle might be in the system but the owner might be unknown).
[6 marks]

4.The police officer should be able to enter details for a new vehicle. This will include the registration (plate) number, make, model and colour of the vehicle, as well as its owner. If the owner is already in the database, then you need to provide a way to associate that person to the new vehicle as part of this process. If the owner is not in the database they will need to be added (along with personal information including the license number) as part of this process.
[14 marks]

5.The police officer should be able to file a report for an incident and retrieve existing reports (e.g., via a search). Filing new ones will involve submitting a textual statement, the offence in question, recording the time of the incident and the vehicle and person involved (who may or may not be the owner). If either the person or the vehicle are new to the system, then you will need to add them as part of this process. NOTE: a fine is not to be stored at this stage, because the fine will be issued by a court at a later time, and added by an administrator. The officer should be able to retrieve and edit all aspects of the reports they file. 
[14 marks]

6.Administrators should be able to log into the system with a specified username (please include at least one user named “daniels” with the password “copper99”). Administrators should be able to do everything that an ordinary police officer can do with the following additions: 
Administrators should be able to create new police officer accounts 
Administrators should be able to associate fines to reports
[10 marks]

7.To support various regulatory and statutory requirements, police need to have access to an audit trail to account for database record accesses and changes that are made (e.g., deletions, updates, etc.). Implement an auditing feature in the web interface which will enable administrators to review the above, on a per user basis (you may extend this to provide other auditing views e.g., per record, filtering by user, editing facilities, etc.).
[16 marks]

Other required features [24 marks total]
Documentation. You should produce two documentation manuals – a user manual and technical documentation. The user manual should explain to a user (i.e., a police officer or an administrator) how to use the system. It is extremely important that all of the software features you have implemented should be described in this manual (otherwise you might not get marks for them!). The user manual should be no more than 500 words, though it may have screen shots if you so wish. 
The technical manual should contain all of the information that would be needed if you were handing this project over to another developer to take it further. It should briefly explain how to install your software (you may assume that MySQL, and a web server implementing PHP are already installed and configured). It should also contain a detailed description (including diagrams) of architecture / structure of your system, together with a brief rationale for its design. For example, you could include explanations of key flows of data / interaction, key PHP components, etc. Your technical manual must include an Entity-Relationship diagram to that represents your final database design. You should show all entities together with their attributes and the relationships between these entities. You should annotate the cardinality ratios of each relationship. You may use an ERD tool or similar, alternative digital option (e.g., Powerpoint), or draw by hand and photo (note that if your photo is illegible in some way you may lose marks). Note: Please avoid including screenshots of code or large amounts of code listings. The technical manual should be no more than 700 words (diagrams, screenshots, etc. do not count for words).
[14 marks]
User interface (overall assessment). This component of marking represents an assessment of the UI as a whole, including visual design, interaction design and usability. You might pick up a few marks for creating a beautiful user interface, but not many if it is not functional. What is more important is that your system is usable, in this case with minimal or ideally no training. We strongly advise you primarily examine Nielsens’s 10 heuristics and secondarily look for existing best practices in web interface design to guide you. 
[10 marks]

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
