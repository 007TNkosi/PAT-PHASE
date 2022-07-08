# Grade 12 IT PAT 2022 #

> BY: Luthando Mashabane

## PAT Phase outline ##

1. Scenario and scope
2. User requirements
3. Navigation (Description of flow diagram)
4. Database design
5. Class description and class diagram
6. Text files and arrkay/advanced programming concepts
7. GUI design
8. Data input
9. Data processing
10. Data output

---

> ## Scenario and Scope ##

### Scenario ###

Living in the fourth industrial revolution(4IR) has forced us to rapidly digitalise. Over the past years, updates to technology have been introduced. Although most industries, businesses and even people themselves were not ready to adapt to these new systems and software, the whole world was struck by a global pandemic that forced us to enforce these changes into our lives. </br>
COVID-19 had the greatest impact on the education sector. Online classes were introduced via Zoom, Google Classroom and other virtual collaboration platform. However, these solutions still were not enough. With walk-in applications not being accepted under COVID-19 restrictions, many educational institutions had to provide online solutions to ensure safety of those involved and those who needed to equip themselves with the necessary skill-set to execute their work regardless of the unprecedented circumstances.

### Scope ###

Therefore, I have decided to design and create an online platform that will allow students to register for online courses - Accessible anytime and anywhere in their convenient and safe environment. </br> The software application will store information about the student, duration of module and costs included which can be accessed by the user and administrator under certain restrictions. Logins and passwords will be used to enable access control between the user and the administrator. The user will not be able to make changes to the database. The administrator and the user will be able to delete, update and insert new records in the database. The updates on remaining cost will be sent to the user regularly.

> ## User requirements ##

User | Admistrator
-|-
As a **user**, I ... | As an **administrator**, I...
Can update personal information | Can insert, update and delete records in studentTable.db
Can update module(s) | Can insert, update and delete records in moduleTable.db
Can insert a new module | Can view tables
Can delete a module | Can modify the interface
Can sign up | Can access and change the code
Can access login screen | Maintain the database

> ## Navigation ##

### Flow diagram ###

![Flow diagram](/Images/Flow%20Diagram.png)

### Simplified flow diagram ###

![Flow diagram](/Images/schema.png)

---

> ## Database Design ##

Following are screenshots of each table and the relationships that exist between tables.

### Student Table ###

![Student table](/Images/studentTable.png)

### Module Table ###

![Module table](/Images/moduleTable.png)

### Relationship ###

![Relationship table](/Images/relationships.png)

---

> ## Class description and class diagram ##

Object login | -
-|-
Attributes | fStudentID: string; fPassword: string;
Methods | Constructor methods; Accessor method
Return types | GET; POST
Parameters | pStudentID; pPassword
Scope of method: Constructor | The constructor will receive the StudentID and Password. These values will be assigned to the respective fields.
Scope of method: Accessor | Will receive the value of the StudentID and Password, it will test whether the password and username exist and will return an error message if it does not exist and will be able to access the tab sheet if it does exist.

> ## Text files and array/advanced programming concepts ##

1. I am going to use a textfile to store the Student IDs and Passwords.
2. I will read the textfile into an array, when the user logins the program will loops through the array to test if they exist.
3. When a person sign’s up for the first time, their newly generated student ID and password will be added to the textfile and they will be able to log in like everyone else.

> ## GUI Design ##

### Login Screen ###

![Login Screen](/Images/loginScreen.png)

### Sign Up ###

![Sign up VS Login](/Images/signUplogin.png)

### Admin GUI ###

![Administrator UI](/Images/adminTable.png)

![Administrator Ui](/Images/adminUI.png)

![Administrator Ui](/Images/adminUI-2.png)

![Administrator UI](/Images/adminUI-3.png)

> ## Data Input ##

### Input Interfaces, input validation and data output ###

Object | Format of input | Data Type | Input | Processing | Output | Validation w/ processing and error message
-|-|-|-|-|-|-|
edtStudentID | text | string | User input | sStudentID := edtStudent.text; | N/A | Presence check if: length(sStudentID) = 0; THEN showMessage('Empty field');
edtName | text |string | keyboard | sName := edtName.text; | N/A | Data type check if edtName,sName = false then showmessage(‘Invalid data type’);
edtID | text | string | keyboard | sID := edtID.text; | N/A | Format check If length(sID)<> 13 then showmessage(‘Invalid ID’);
DBGStudent | Database | string | database | A connection between the database module and the unit needs to be made. The DBGrid needs to be connected to the table. | The StudentTable will be displayed. | N/A
btnLogin | textfile | txt | textfile | AssignFile(myFile,’Module.txt’) Reset(myFile); iCount := 0; while not EOF(myFile) and (iCount <20) do begin ReadLn(myFile,sLine); Inc(iCount); iPos := pos(‘#’,sLine); arrStudentID[iCount] := copy(sLine,1,iPos-1 | Student tabsheet will be displayed. | Presence check If Fileexists(Module.txt) <> true then showmessage(‘file does not exist’); Exit;
btnNoAccount | N/A | N/A | Mouse(onClick) | TForm.ShowModal; | The user will be taken the sign up screen | N/A
btnAdmin | N/A | N/A | Mouse(on Click) | TForm.ShowModal; | The user will be taken to the admin login screen; | N/A
CmbProject | Selection | string | Mouse | If the ItemIndex is 0 on the Combobox then there is a project for the module. If the ItemIndex is 1 then there is no project for the modules. | This information will be added to the table along with the other information for this record. | If the ItemIndex on the Combobox is equal to -1 then nothing has been selected. A message will be displayed informing the user that nothing has been selected.
sedAPS | Value | integer | keyboard | iAPS :=strtoint(sedAPS.Value); | N/A | If tryStrint(SedAPS.Value,iAPS) = False;
imgShowHide | N/A | N/A | Mouse | When the user holds the mouse when it is on the image, the password will show in normal characters. | The password will show on the edit. | The program will test if the image exists which will change the eye to a scarred eye when the person leaves the mouse.
