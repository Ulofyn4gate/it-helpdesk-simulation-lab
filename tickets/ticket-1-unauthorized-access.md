Ticket 1: Unauthorized Access to HR Folder

Issue

User john.doe was able to access the HR folder despite not being part of the HR department.

⸻
Investigation

* Checked folder permissions
* Identified presence of Authenticated Users group
* Confirmed this group grants access to all logged-in users

⸻

Resolution

1. Opened folder properties → Security → Advanced
2. Disabled permission inheritance
3. Removed Authenticated Users
4. Ensured only:
    * HR group
    * Administrators
    * SYSTEM
        had access

⸻

✅ Result

User john.doe now receives an Access Denied error when attempting to access the HR folder.
(Screenshots stored in /screenshots)

