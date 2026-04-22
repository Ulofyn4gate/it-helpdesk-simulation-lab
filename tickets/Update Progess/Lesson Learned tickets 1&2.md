 Challenges Encountered & How They Were Resolved

1. Folder Visibility Issue (Wrong Directory)

Issue:
Folders created via Command Prompt were not visible in File Explorer.

Cause:
The folders were created in: C:\Users\IT Admin\Company
instead of: C:\Company

Resolution:
* Identified incorrect working directory
* Moved the folder to the correct root path: move "C:\Users\IT Admin\Company" C:\


2. Permission Inheritance Blocking Changes
   
Issue:
Unable to remove the “Users” group from folder permissions.

Cause:
Folder was inheriting permissions from its parent directory.

Resolution:

* Navigated to Advanced Security Settings
* Disabled inheritance
* Converted inherited permissions to explicit permissions
* Removed unnecessary groups

3. Unauthorized Access Despite Restrictions

Issue:
User john.doe could still access the HR folder after restrictions were applied.

Cause:
The Authenticated Users group was still present, granting access to all logged-in users.

Resolution:

* Removed Authenticated Users from permissions
* Verified access control by testing with a non-authorized user
  

4. Password Reset Behavior in VM Environment (ticket 2)

Issue:
Forcing password change at next login triggered an error:

“This feature requires removable media such as a USB flash drive”

Cause:
Limitation of local accounts within a virtual machine (UTM / ARM-based Windows)

Resolution:

* Reset password without enforcing change: net user jane.smith NewPass123!
* Successfully logged in without forcing password update

Key Takeaways

* File path awareness is critical in troubleshooting
* Permission inheritance can override manual configurations
* Broad groups like Authenticated Users can unintentionally grant access
* Some Windows features behave differently in local vs domain environments
* Virtualization (Mac + ARM + Windows) introduces unique limitations

⸻

Next Steps

* Simulate account lockout scenarios
* Continue building real-world helpdesk cases
* Improve documentation and troubleshooting depth
