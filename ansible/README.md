# ansible

----
- [modules](#modules)
    * [ping](#ping)
        + [ping a server](#ping-a-server)
        + [ping all server](#ping-all-server)
    * [copy](#copy)
        + [copy file to target servers directory](#copy-file-to-target-servers-directory)
    * [script](#script)
        + [run script in target servers](#run-script-in-target-servers)
- [resources](#resources)
----

## modules

### ping

#### ping a server 
```shell
ansible server1 --module-name ping

ansible server1 -m ping
 
```
hosts(/etc/ansible/hosts) file
```text
server1 ansible_connection=local
server2 ansible_connection=local
server3 ansible_connection=local
```

#### ping all server
```shell
ansible all --module-name ping
```

### copy

#### copy file to target servers directory
```shell
ansible all --module-name copy --args "src=<LOCAL_FILE> dest=<DIRECTORY_IN_TARGET_SERVER>"

ansible all -n copy -a "src=<LOCAL_FILE> dest=<DIRECTORY_IN_TARGET_SERVER>"
```

### script

#### run script in target servers
```shell
ansible all --module-name script --args "<LOCAL_SCRIPT_FILE_LOCATION> <SCRIPT_ARGUMENTS_WITH_SPACE_AS_DELIMITER>"

ansible all -m script -a "<LOCAL_SCRIPT_FILE_LOCATION> <SCRIPT_ARGUMENTS_WITH_SPACE_AS_DELIMITER>"
```

## resources
- [ansible documentation](https://docs.ansible.com/ansible/latest/index.html)