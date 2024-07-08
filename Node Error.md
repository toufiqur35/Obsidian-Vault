Problem
```node
npm : File C:\Program Files\nodejs\npm.ps1 cannot be loaded because running  scripts is disabled on this system. For more information, see  about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
```


#### Solution

```node
1. set-ExecutionPolicy RemoteSigned -Scope CurrentUser
2. Get-ExecutionPolicy
3. Get-ExecutionPolicy -list
```


5312 47a1 a442 e51d
376a 1bff b5de 6d7e
4649 33fd 6467 f51a
7afd 2b39 7a1c 6a03