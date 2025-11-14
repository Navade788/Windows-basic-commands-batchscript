# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript
```
Developed by : S.Navadeep
Reg.No : 212224230180
```
# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 



# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"


## COMMAND AND OUTPUT


```bash
mkdir my-folder
```
<img width="1015" height="108" alt="image" src="https://github.com/user-attachments/assets/093647f1-8607-4fab-b8ef-0fbd9c6aff65" />




Remove the directory "my-folder"

## COMMAND AND OUTPUT

```bash
rmdir my-folder
```
<img width="996" height="103" alt="image" src="https://github.com/user-attachments/assets/415f51ff-bd17-48ef-a583-1ebb77945cf3" />



Create the file Rose.txt

## COMMAND AND OUTPUT

```bash
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z

dir Rose.txt
```

<img width="1007" height="470" alt="image" src="https://github.com/user-attachments/assets/06fd7c8f-57e4-4297-8819-f8ab913999ee" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

```bash
echo “hello world” > hello.txt
type hello.txt

```

<img width="998" height="100" alt="image" src="https://github.com/user-attachments/assets/fe84a219-ae0c-49f0-936a-e957784f2cf8" />



Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT


```bash
copy hello.txt hello1.txt

```

<img width="957" height="115" alt="image" src="https://github.com/user-attachments/assets/cada12b5-5a78-487e-ab3f-ad658ad68010" />


Remove the file hello1.txt

## COMMAND AND OUTPUT

```bash
del hello1.txt


```

<img width="1014" height="75" alt="image" src="https://github.com/user-attachments/assets/bb3570af-0a34-4a76-92b9-f6ab0f76b4a0" />


List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT

```bash
dir hello1.txt
```

<img width="967" height="233" alt="image" src="https://github.com/user-attachments/assets/973da44e-5227-48f7-921b-b310c22b36fb" />


List out all the associated file extensions 

## COMMAND AND OUTPUT

```bash
assoc | more
```

<img width="885" height="1077" alt="8" src="https://github.com/user-attachments/assets/3092196a-d9a0-47ec-a87f-684b77a820ae" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

```bash
fc hello.txt Rose.txt

```

<img width="1005" height="318" alt="image" src="https://github.com/user-attachments/assets/aa72d08f-1a5b-4383-a299-ee993f88d2b0" />



## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".


```bash

@echo off
set name=John
echo Hello, %name%!
pause


```



## OUTPUT


<img width="980" height="152" alt="image" src="https://github.com/user-attachments/assets/0ac53bf7-f6d6-487f-9c50-10995e6429fb" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

```bash

@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

```

## OUTPUT


<img width="961" height="348" alt="image" src="https://github.com/user-attachments/assets/0b1e6989-60c5-4407-b87d-fbd9f7941733" />


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.


```bash

@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

```


## OUTPUT

<img width="958" height="220" alt="image" src="https://github.com/user-attachments/assets/3837244a-1488-496f-b94f-ce238b872e5a" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```bash
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

```

## OUTPUT

<img width="1184" height="351" alt="13" src="https://github.com/user-attachments/assets/989e07fe-313c-4188-9927-a3879bab996e" />




Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

```bash
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```

## OUTPUT

<img width="1085" height="506" alt="14" src="https://github.com/user-attachments/assets/f6aeea9e-02cc-4e89-8c7f-679240c53cd7" />



# RESULT:
The commands/batch files are executed successfully.
