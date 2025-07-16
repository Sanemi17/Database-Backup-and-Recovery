# Database-Backup-and-Recovery

COMPANY NAME: CODTECH IT SOLUTIONS

NAME: SANEMI VALECHA

INTERN ID : CT04DZ135

DOMAIN NAME: SQL

DURATION: 4 WEEKS

MENTOR: NEELA SANTOSH


Databases are the backbone of any application, storing everything from customer records to transactions, inventory data, and more. Because data is so critical, protecting it from loss or corruption is essential. That’s where Database Backup and Recovery comes in. In Task 4 of the SQL internship, I explored how to create a backup of a SQL Server database and restore it using standard SQL commands. These operations are critical in both development and production environments.

🔒 Why Backup and Recovery Is Important
Accidental deletion, hardware failure, software bugs, malware, and user errors can all lead to data loss. Without a backup system in place, such events can cause serious harm to an organization, including financial loss, legal issues, and business disruption.

A good backup strategy ensures that data can be recovered and business can resume quickly in case of a problem. Recovery operations ensure that the backed-up data is successfully restored, bringing the database back to a usable state.

🔄 Steps Performed in This Task
For this task, I worked with a sample database named INTERNSHIP in Microsoft SQL Server Management Studio (SSMS). I simulated the backup and restore process using SQL commands that are commonly used in real-world environments.

✅ Step 1: Backup the Database
To create a full backup of the INTERNSHIP database, I used the BACKUP DATABASE command:

sql
Copy
Edit
BACKUP DATABASE INTERNSHIP
TO DISK = 'C:\\SQL BACKUP\\INTERNSHIP.bak'
WITH FORMAT, INIT, NAME = 'INTERNSHIP';
📌 Explanation:

TO DISK specifies the location where the .bak (backup) file will be stored.

WITH FORMAT initializes a new media set for the backup.

INIT overwrites any existing backup at that location.

NAME is a label for the backup set.

This command ensures that a full backup of the INTERNSHIP database is created and stored at the specified location. The output typically looks like:

nginx
Copy
Edit
BACKUP DATABASE successfully processed 323 pages in 1.432 seconds.
✅ Step 2: Restore the Database
To restore the database from the backup file, I used:

sql
Copy
Edit
USE master;
GO
RESTORE DATABASE INTERNSHIP
FROM DISK = 'C:\\SQL BACKUP\\INTERNSHIP.bak'
WITH REPLACE;
📌 Explanation:

USE master is used because SQL Server cannot restore a database while it’s in use. We need to switch to a different context.

RESTORE DATABASE restores the data from the backup file.

WITH REPLACE allows SQL Server to overwrite the existing INTERNSHIP database if it exists.

The output typically looks like:

nginx
Copy
Edit
RESTORE DATABASE successfully processed 323 pages in 1.721 seconds.
⚠️ Challenges Faced
During the task, I encountered a few errors like:

"Cannot open backup device" – due to permission or path issues

"RESTORE cannot process database because it is in use" – resolved by switching to the master database
These errors helped me learn how to troubleshoot SQL Server problems, which is a very important skill in database management.

🧠 What I Learned
This task helped me:

Understand the syntax and structure of SQL Server backup and restore commands.

Recognize the importance of file paths and permissions in SQL operations.

Learn best practices for disaster recovery and data protection.

In real companies, this task would translate into scheduled automatic backups, off-site storage of .bak files, and restore procedures tested regularly to ensure data integrity.

✅ Conclusion
Task 4 was one of the most important topics in this internship. Backup and recovery aren’t just about writing queries — they’re about ensuring business continuity. I now understand the real-world relevance of disaster recovery planning and how database administrators ensure data is never lost. The commands I used simulate what real professionals do every day to secure their systems and protect users' trust.

OUTPUTS

"https://github.com/user-attachments/assets/ba4fdab9-d330-44af-97a2-a1cbb3fbabe8"
