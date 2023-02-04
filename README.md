# LineupAppQ | Basic File Submission Page


## Use Cases:
Create an application to provide an interface for users for selecting files which will be uploaded to a SQL database. Files can be of any extension.


## Tool Stack:
1. **Python-Web Development**: Used Flask and python libraries are used to create the APIs and the backend. Backend code can be written in python easily with minimum code length which makes even the big projects easy to maintain. Python has all the features integrated in backend to implement a secure and fully functional backend using APIs. Python provides an additional advantage over most of the language for it is very easy to be integrated to any existing system be it automation systems, Machine Learning or Data maintenance systems or for testing and sustenance.
2. **SQL Database**: Although other databases could have been used which would facilitate easier data storage in our use case, but we went to implement the data storage in SQL server. We used the **XAMPP** software to host the SQL server and **Apache** interface to view the data refresh in the DB.


## Features:
1. The UI is very simple implemented through only HTML. Features like loading logo script and upload notification with display of uploaded files can be added but are yet not implemented yet.
2. The backend contains of **/submit** API which accepts the file selected by the user and uploads it to the SQL database.
3. The "submit" API starts and closes the connection within the API function making it secure from the outside world. Python integrates features like sessions etc, so we need not take care of them explicitly. If required we can add session and cookies parameters very easily.
4. The data sent by the user is a file of any type. Being unsure of the file type and to accommodate it's storage in SQL database table, we convert the file into **binary format**. Thus our storage has two columns: Filename(String) and File Content(Binary String). The functionality to reverse the parsing and enable downloading is not yet integrated in this application.
5. To avoid data loss in case of connection issue or file errors, we keep a backup of the files in zip format for future investigations.


## Code Walkthrough
Flask maintains a fixed structure. For our purpose, where we haven't used any CSS or Javascript, the structure is:

Flask

|--Server: Jupyter Notebook or python file containing the server script.

|--template: HTML Files

|--static: Backup files

Server:
1. Contains python script to run the Flask application server.

Template:
1. test.html: The HTML file to present the user a form to slect the file of any type.

Static:
1. Contains files which were not pushed correctly to the DB in zip format for backup.
