# [Windows Investigation Room](https://tryhackme.com/r/room/investigatingwindows) Guide
 Use the powershell for running the commands
 use can use this for [reference](https://medium.com/@haircutfish/tryhackme-investigating-windows-task-1-investigating-windows-da65f32cf67f) 

## Investigation Questions:

1. Windows Version and Year: 
   use command :

       systeminfo

3. Last Logged-in User: 
   command :

       Get-Localuser 
5. Last Login Time of User (John): 
   - command :

         net user john 
6. IP on Startup:
   open regedit click it and go to this path Computer>HKEY_LOCAL_MACHINE>SOFTWARE>MICROSOFT>WINDOWS>CurrentVersion>Run

7. Administrative Accounts:
   command :

       net localgroup administrators 

9. Malicious Scheduled Task:
  Command :

       Get-Scheduled givTask | Select TaskName, State, Actions, Description | Format-Table -AutoSize
check for the file named like clean system

10. Daily Run File (Task):
 Command :
 
        $task = Get-ScheduledTask | Where TaskName -EQ “Clean file system”
        $task.Actions

11. Listening Port (File):
 use this [reference](https://medium.com/@haircutfish/tryhackme-investigating-windows-task-1-investigating-windows-da65f32cf67f)

12. Last Login Time of Jenny:
  Command :

        net user jenny

13. Compromise Date:
    - Format: MM/DD/YYYY.
    -  use this [reference](https://medium.com/@haircutfish/tryhackme-investigating-windows-task-1-investigating-windows-da65f32cf67f)
      
 use this path :C:/

![null](https://github.com/user-attachments/assets/c4365f24-c95b-4e12-acc9-a63da11359a9)


14. Time of First Privilege Assignment (Compromise):
    - Format: MM/DD/YYYY HH:MM:SS AM/PM.
  -  use this [reference](https://medium.com/@haircutfish/tryhackme-investigating-windows-task-1-investigating-windows-da65f32cf67f)

![Screenshot at 2024-11-28 23-58-06](https://github.com/user-attachments/assets/975e687c-a1e7-4b1c-931c-e1e93e59d928)
![Screenshot at 2024-11-29 00-01-22](https://github.com/user-attachments/assets/a6d5d37f-5421-4955-9e22-16cfb32f25d6)
![Screenshot at 2024-11-29 00-02-26](https://github.com/user-attachments/assets/02ee92ec-8439-4025-9575-1a94a7f4dfa8)
![Screenshot at 2024-11-29 00-03-04](https://github.com/user-attachments/assets/1b276807-49de-4280-8d90-70e093f5bacf)
![Screenshot at 2024-11-29 00-03-22](https://github.com/user-attachments/assets/c5a4e7cf-db82-4dff-8a2a-48c70088e8c3)
![Screenshot at 2024-11-29 00-14-14](https://github.com/user-attachments/assets/81426851-934e-4038-b644-7cf631652d36)

15. Tool for Password Extraction:
    - Inspect processes, file artifacts, or Event Logs.
    - use this path : C:\TMP
    - ![Screenshot at 2024-11-29 00-23-18](https://github.com/user-attachments/assets/bfa3cfdd-0ba1-4b17-931d-37be88094c40)


16. C2 Server IP:
    - Analyze network traffic or logs.
      use path : C:\Windows\System32\drivers\etc
    - ![Screenshot at 2024-11-29 00-33-45](https://github.com/user-attachments/assets/fdb7c962-e7f4-4796-9ebf-cb83c2724d13)


17. Shell Extension Name:
    - Check uploaded files or  Event Logs.
      use path :C:\inetpub\wwwroot
    - ![Screenshot at 2024-11-29 00-37-11](https://github.com/user-attachments/assets/67765a6d-7693-47cf-b8d4-d92c6d8db7e9)


18. Last Opened Port:
    - Analyze firewall or connection logs.
   ANS : port 1337
19. DNS Poisoning Target:
    - Use this path :
  use path : C:\Windows\System32\drivers\etc
    - ![Screenshot at 2024-11-29 00-33-45](https://github.com/user-attachments/assets/fdb7c962-e7f4-4796-9ebf-cb83c2724d13)
