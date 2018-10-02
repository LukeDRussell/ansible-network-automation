# Ansible tips and tricks
- [Ansible tips and tricks](#ansible-tips-and-tricks)
    - [Executable playbooks](#executable-playbooks)
    - [Better handling for high latency links](#better-handling-for-high-latency-links)

## Executable playbooks
To save time and typing when running playbooks over and over, you can make playbooks executable, like so:
```
$ ./get-facts.yaml
```
To set it up:
1. Add a shebang and executable to the start of the playbook yaml file
2. Make the file executable
3. (optional) Include any other arguments that are always required when running the playbook e.g. `-k` for passing an SSH password to `network_cli` based playbooks.
_Note: Step 3 doesn't work on every distribution i.e. works on MacOS but not on RHEL._
```
#!/usr/bin/env ansible-playbook -k
chmod +x get-facts.yaml
```

## Better handling for high latency links
If you have devices with a poor connection, for example on the other side of a satellite link, you can make ansible more tolerant by changing the default timouts in your ansible.cfg file.
```
[persistent_connection]
connect_timeout = 60
command_timeout = 30
```