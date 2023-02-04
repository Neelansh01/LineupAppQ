# LineupAppQ | Basic File Submission Page


## Use Cases:
Create an application to provide an interface for users for selecting files which will be uploaded to a SQL database. Files can be of any extension.


## Tool Stack:
1. **Python-Web Development**: Used Flask and python libraries to create the APIs in the backend. Backend code can be written in python easily with minimum code length which makes even the big projects easy to maintain. Python has all the features integrated in backend to implement a secure and fully functional. Python provides an additional advantage over most of the language as it is very easy to integrate in any existing system, be it automation domain, ML, DBMS and can be easily used for for testing and sustenance.
2. **SQL Database**: Although other databases could have been used which would facilitate easier data storage of files, but we went to implement the data storage in SQL server. We used the **XAMPP** software to host the SQL server and **Apache** interface to view the data refresh in the DB.


## Features:
1. The UI is very simple implemented through HTML only. Features like loading logo script and upload notification with display of uploaded files can be added but have not been implemented yet.
2. The backend contains the **/submit** API which accepts the file selected by the user and uploads it to the SQL database.
3. The "submit" API starts and closes the connection within the API function **making it secure** from the outside world. Flask integrates features like sessions etc, so we need not take care of them explicitly. If required we can add session and cookies parameters very easily.
4. The data sent by the user is a file of any type. Being unsure of the file type and to accommodate it's storage in SQL database table, we convert the file into **binary format**. Thus our storage has two columns: **Filename(String) and File Content(Binary String)**. The functionality to reverse the parsing and enable downloading is not yet integrated in this application.
5. To **avoid data loss** in case of connection issue or file errors, we keep a backup of the files in zip format for future investigations.


## Code Walkthrough
Flask maintains a fixed structure. For our purpose, where we haven't used any CSS or Javascript, the structure is:

HOME (Flask) Folder

--|--Application.ipynb: Jupyter Notebook (or python file) containing the server script.

--|--template: HTML Files

--|--static: Backup files

Application.ipynb:
1. Contains python script to run the Flask application server.

Template:
1. test.html: The HTML file to present the user a form to slect the file of any type.

Static:
1. Contains files which were not pushed correctly to the DB in zip format for backup.


## Steps to run the code
1. **Install pre-requisites**: SQL Server (or XAMPP software which has the Apache tool as well), Anaconda (for python), Python libraries (mentioned in the notebook), Jupyter Notebook in Anaconda
2. **Host the jupyter notebook** and follow the instructions in the notebook. For hosting the Notebook just run "jupyter notebook" ommand in the Conda Prompt. This will host the application on the address which will be visible in the notebook at the bottom of the running cell (which is the last one).
3. Select file of any format and submit. File will be converted into Binarry String and stores in DB. If there is any error, then the backup zip will be maintained in the static folder.
4. For now, we are currently just saving the files in the Home Folder for testing and being sure about the selected file. This functionality can be removed.
