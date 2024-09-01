# Node-Red-Http-odbc
=====================
<img width="937" alt="image" src="https://github.com/user-attachments/assets/ea703aee-6798-4ba4-9993-8be523273b3e">
Create HTTP end points using Node RED and ODBC

### About

This project offers a way to create REST APIs for retrieving infomation from IBM i tables.  This repository is for demonstration purposes only.

### Software Requirements
* [Node-RED](https://nodered.org/docs/getting-started/local) (on your local PC or on IBM i)
* [ODBC](https://ibmi-oss-docs.readthedocs.io/en/latest/odbc/installation.html)

### Required Node-RED Modules to install in the pallette
* [@ais_automation/node-red-contrib-odbc](https://flows.nodered.org/node/@ais_automation/node-red-contrib-odbc)

Steps
1. Install all required software / drivers
2. On IBM i, set up the sample IBM i tables:  `CALL QSYS.CREATE_SQL_SAMPLE ('LIBNAME');`
3. Create an ODBC DSN entry in your _~/.odbc.ini_ file.  Name it DB2CON, enter your System (DNS or IP Address), UserID, Password, and DefaultLibraries.
```
[DB2CON]
Description            = Node-RED DSN
Driver                 = IBM i Access ODBC Driver 64-bit
System                 = pub400.com
UserID                 = **********
Password               = **********
Naming                 = 0
DefaultLibraries       = LIBNAME
TrueAutoCommit         = 1
```
4. start `node-red`
5. Either start node-red in project mode and clone this project into Node-RED, or import flows.json into Node-RED.
6. Use your favorite REST client (i.e. Postman, Thunder Client, etc.) to test endpoints for employee and department.
   * http://127.0.0.1:1880/departments
   * http://127.0.0.1:1880/employees
  
7. You can also add any field names as parameters to the endpoint
   * http://127.0.0.1:1880/departments?DEPTNO=A00&MGRNO=000010
     
8. Experiment/create endpoints that return info from your own tables on IBM i.

https://github.com/user-attachments/assets/e3faeb9b-9f38-4fd4-b4bb-770e3c106852


