# Versions

v1.4 - 2024-07-21
- Fixed regression from v1.3, fixed NX Game Info title and version importing, now supports CSV imports from NX Game Info (File -> Export -> CSV), now imports the entire title line, now chooses the base Title ID as Game ID instead of the latest one, now removes any punctuation not compliant with No-Intro and changes colons into dashes, now excludes any parentheses present in the update column

# To-do
- TESTING
- Add multi-title cart support
- Further polish, like a progress window for hash calculation and Full XCI generation
- Integrate NX Game Info directly (and possibly other submodules like hactoolnet) to eliminate manual copy and pasting
- Compile into a user-friendly EXE with all dependencies bundled in
- Add support for other systems? 👀

**NOTE NOTE NOTE this is in EARLY ALPHA and has been MINIMALLY TESTED so it may BREAK at any time for any reason, use at your own risk and double check its output!**

# Readme

So, you want to submit a Switch cart to No-Intro? I developed a quick and easy Python script which standardizes forum submissions into easily-imported XML files.

Download the script [here](https://raw.githubusercontent.com/rarenight/No-Intro-Switch-Cart-Submission-Tool/main/no-intro-switch-cart-submission-tool-v1.4.py) (right click -> Save As).

You'll need Python with the PyQt5 dependency installed (`pip install pyqt5`) along with [NX Game Info](https://github.com/garoxas/NX_Game_Info) (and the appropriate prod.keys) before you get started.

First, load your default XCI within NX Game Info GUI, then export a CSV (File -> Export -> CSV):

![image](https://github.com/user-attachments/assets/a3a6c27b-e37a-4e9e-91f9-8f62a7ac1baf)

Then drag and drop the CSV file into the window. The values will auto-populate:

![image](https://github.com/user-attachments/assets/e445ad23-97a6-47c6-994e-092d267e8684)

Alternatively, you can paste the output that NX Game Info CLI provides you:

![image](https://github.com/user-attachments/assets/c1493961-dd18-4d60-886a-47601ef1e932)

Then press Import. You'll (hopefully) see the Game Name, Languages, and GameID1 auto-populated. It should also populate the version and update in File Info. If for whatever reason the NX Game Info import messes up, you can always manually type the values. **NOTE: THIS IMPORT TOOL DOES NOT SUPPORT MULTI-TITLE CARTS YET.**

Add the applicable cart region so all fields are filled out:

![image](https://github.com/user-attachments/assets/98b2f17d-44e4-4589-86b9-43401e9d5ca8)

Then click the "Dump Info" tab, fill out the Dumper and Tool fields, and click "Generate Card ID Values". Drag and drop the (Card ID) binary file that nxdumptool outputs into the window and the Card ID values should (hopefully) populate like this:

![image](https://github.com/user-attachments/assets/e447a6b8-2990-4201-b608-b9d72427db26)

A custom dump date can be specified if your cart wasn't dumped the same day.

Then click the "Media Info" tab and fill out all the values manually. A dropdown menu allows you to select a downwards triangle for your convenience.

![image](https://github.com/user-attachments/assets/4626e057-effb-482c-ac26-f00bd4869e5a)

Click the File Info tab and then "Import Hashes." If you don't already have a Full XCI, click "Generate Full XCI" to build one.

Drag and drop the Default XCI, then the Initial Area BIN file, then the Full XCI file into the window and their hashes will auto-populate. Please note this takes a while for large files, please be patient.

![image](https://github.com/user-attachments/assets/2a9d0ec4-6a16-427a-bfbf-7aa6a7e4d039)

When all fields are populated as shown in the above image, click "Generate Submission" and an XML file will be generated in your chosen directory.

This program generates an XML submission file that looks like this:

![image](https://github.com/user-attachments/assets/6ba5ca81-21ae-453f-a038-6c76ca7620f4)

This XML submission file can then be easily imported into No-Intro's backend in a standardized and uniform format:

![image](https://github.com/user-attachments/assets/6fccc898-132a-4b50-81e0-5187a5e6edf8)

![image](https://github.com/user-attachments/assets/2fc094fa-6c12-4580-b9ac-3f22d6476cdf)
