# File & Folder Permissions

| Special Permissions          | Full Control | Modify | Read & Execute | List Folder Contents | Read | Write |
| ---------------------------- | ------------ | ------ | -------------- | -------------------- | ---- | ----- |
| Traverse Folder/Execute File | x            | x      | x              | x                    |      |       |
| List Folder/Read Data        | x            | x      | x              | x                    | x    |       |
| Read Attributes              | x            | x      | x              | x                    | x    |       |
| Read Extended Attributes     | x            | x      | x              | x                    | x    |       |
| Create Files/Write Data      | x            | x      |                |                      |      | x     |
| Create Folders/Append Data   | x            | x      |                |                      |      | x     |
| Write Attributes             | x            | x      |                |                      |      | x     |
| Write Extended Attributes    | x            | x      |                |                      |      | x     |
| Delete Subfolders & Files    | x            |        |                |                      |      |       |
| Delete                       | x            | x      |                |                      |      |       |
| Read Permissions             | x            | x      | x              | x                    | x    | x     |
| Change Permissions           | x            |        |                |                      |      |       |
| Take Ownership               | x            |        |                |                      |      |       |
| Synchronise                  | x            | x      | x              | x                    | x    | x     |

See [[powershell#Permissions|changing permissions using Powershell]].


