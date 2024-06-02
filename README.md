# AutoGen-101

Steps to try out the AutoGen on Windows:

 - First step is to crete a system environment variable on Windows by using the following steps:
Method 1: Through the Control Panel
Open the Control Panel:

Press the Windows key and type "Control Panel", then open the application.
Go to System and Security:

Click on "System and Security", then "System".
Advanced System Settings:

In the left panel, click on "Advanced system settings".
Environment Variables:

In the window that opens, click on "Environment Variables".
Add the Variable:

Under "System variables", click "New".
Variable name: OPENAI_API_KEY
Variable value: your_openai_api_key (replace with your actual API key)
Click "OK" to close all windows.
Method 2: Through the Command Prompt
Open Command Prompt as Administrator:

Press the Windows key, type "cmd", right-click on "Command Prompt" and select "Run as administrator".
Set the Environment Variable:

cmd
setx OPENAI_API_KEY "your_openai_api_key" /M
/M means that the variable will be set at the system level (for all users).
Method 3: Through PowerShell
Open PowerShell as Administrator:

Press the Windows key, type "PowerShell", right-click on "Windows PowerShell" and select "Run as administrator".
Set the Environment Variable:

powershell
[System.Environment]::SetEnvironmentVariable("OPENAI_API_KEY", "your_openai_api_key", "Machine")
Method 4: Using a .env Configuration File
You can use a .env configuration file to set environment variables. This method is especially useful for projects using a virtual environment or specific frameworks like Django or Flask.

Create a .env File in Your Project Directory:

makefile
OPENAI_API_KEY=your_openai_api_key
Load the .env File in Your Python Script:

python
from dotenv import load_dotenv
import os

load_dotenv()  # Load environment variables from .env file

api_key = os.getenv("OPENAI_API_KEY")
Ensure you install the python-dotenv package:

bash
pip install python-dotenv
Method 5: Modifying the Registry (Advanced)
Note: Modifying the registry can be risky. Proceed with caution and, if possible, back up the registry before making changes.

Open the Registry Editor:

Press Windows + R, type regedit, and press Enter.
Navigate to the Appropriate Key:

Go to HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Environment.
Add a New Environment Variable:

Right-click on "Environment", select "New" -> "String Value".
Name: OPENAI_API_KEY
Double-click the new entry and enter your API key as the value.
By using one of these methods, you can set the OPENAI_API_KEY environment variable on Windows.


Once you have already configured and set the utils.py by adding the OPENAI_API_KEYS you can download the repo and perform the following commands to testing out AutoGen:
pip install autogen pprint utils
python testing-autogen.py

and here are the results:
python testing-auogen.py
Sure! Here's a joke for you:

Why don't skeletons fight each other?

They don't have the guts!
Of course! Which joke would you like me to repeat for you?
joe (to cathy):

I'm Joe. Cathy, let's keep the jokes rolling.

--------------------------------------------------------------------------------
cathy (to joe):

Sure thing, Joe! So, I recently started taking up yoga to ease my stress. Now, I'm stressed about not being able to touch my toes. It's a downward facing spiral!

--------------------------------------------------------------------------------
joe (to cathy):

Haha, Cathy, that's quite the predicament. I tried yoga once, but I quickly realized that my favorite pose is the "child's pose" - you know, the one where you just lie down and take a nap.

--------------------------------------------------------------------------------
cathy (to joe):

I feel that, Joe! Sometimes that child's pose can be all too tempting, especially when the instructor starts throwing around words like "downward dog" and "warrior pose". I'm here for a relaxing stretch, not a battle scene enactment!

--------------------------------------------------------------------------------
[{'content': "I'm Joe. Cathy, let's keep the jokes rolling.",
  'role': 'assistant'},
 {'content': 'Sure thing, Joe! So, I recently started taking up yoga to ease '
             "my stress. Now, I'm stressed about not being able to touch my "
             "toes. It's a downward facing spiral!",
  'role': 'user'},
 {'content': "Haha, Cathy, that's quite the predicament. I tried yoga once, "
             'but I quickly realized that my favorite pose is the "child\'s '
             'pose" - you know, the one where you just lie down and take a '
             'nap.',
  'role': 'assistant'},
 {'content': "I feel that, Joe! Sometimes that child's pose can be all too "
             'tempting, especially when the instructor starts throwing around '
             'words like "downward dog" and "warrior pose". I\'m here for a '
             'relaxing stretch, not a battle scene enactment!',
  'role': 'user'}]
{'usage_excluding_cached_inference': {'gpt-3.5-turbo-0125': {'completion_tokens': 138,
                                                             'cost': 0.00033650000000000005,
                                                             'prompt_tokens': 259,
                                                             'total_tokens': 397},
                                      'total_cost': 0.00033650000000000005},
 'usage_including_cached_inference': {'gpt-3.5-turbo-0125': {'completion_tokens': 138,
                                                             'cost': 0.00033650000000000005,
                                                             'prompt_tokens': 259,
                                                             'total_tokens': 397},
                                      'total_cost': 0.00033650000000000005}}
("I feel that, Joe! Sometimes that child's pose can be all too tempting, "
 'especially when the instructor starts throwing around words like "downward '
 'dog" and "warrior pose". I\'m here for a relaxing stretch, not a battle '
 'scene enactment!')

![image](https://github.com/Reyzenello/AutoGen-101/assets/43668563/1c6a3d3f-ce72-4780-b68e-5913f96b7d85)


