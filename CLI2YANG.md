# CLI2YANG

## Retrieve running config on the device in CLI + count
Review the CLI running configuration.  How many CLI lines are there in the config?

1. Login to the pod using the credentials you’ve been provided.
2. Access the c9300 using `telnet c9300`. Then, use credentials `admin` / `Cisco123`.
3. Review the running configuration in the good ole fashioned CLI using `show run`. 
4. Now that you’ve seen the output, count the number of lines using the Guest Shell integration: `guestshell run 
   cli-count`.

## Retrieve running config formatted in XML for NETCONF
How many lines of code are in the output of `netconf-xml`?

1. Login to the pod using the credentials you’ve been provided by the lab proctor.
2. Access the c9300 using `telnet c9300`. Then, use credentials `admin` / `Cisco123`.
3. Format CLI to NETCONF XML using `show run | format netconf-xml`.
4. Now that you’ve seen the output, count the number of lines using `guestshell run netconf-count`. After formatting 
   CLI to NETCONF XML, find the number of lines in the output.
5. Next, enter the Guest Shell  with  `#C9300 guestshell` then,
6. Use the `[guestshell@guestshell ~]$ find .` command the see the extra files that were installed for this 
   integration.
7. Run the `netconf-format` integration and redirect the configuration output to the file `config.before`: 
   `[guestshell@guestshell ~]$ netconf-format  > config.before`.

## Retrieve run config formatted with JSON for RESTCONF
How many lines of code are in the output of `restconf-json`?

1. Login to the pod.
2. Access the c9300 using `telnet c9300`. Then, use credentials `admin` / `Cisco123`.
3. If you're currently in a Guestshell session, use `exit` to get back to the switch's console.
4. Format CLI to NETCONF XML using `show run | format restconf-json`.
5. Now that you’ve seen the output, count the number of lines using `guestshell run restconf-count`. After formatting 
   CLI to RESTCONF JSON, find the number of lines in the output.

## Update the running-config with a script
What is the printed flag when updating the configuration?

1. [guestshell@guestshell ~]$ netconf-format > config.before (this will take a few seconds to complete).
2. Escape from the c9300 using `[guestshell@guestshell ~]$ exit`.
3. Escape from the c9300 using `c9300# exit`.
4. Run the script by running the command `auto@pod5-xelab:~$ cd ~/cli2yang ; ./update-config.sh`.
5. What is the printed flag (a hashed string) when updating the configuration through the script above?

## Compare differences in the config
How many lines of config have changed after running `./cli2yang/update-config.sh`?

1. Run the following commands from the Guest Shell prompt.
  If you are not already connected to the switch, then connect with: `telnet c9300`.
  Then enter the Guest Shell from the C9300 prompt with: `guestshell`.
  
  ```
  [guestshell@guestshell ~]$ netconf-format > config.after (this will take a few seconds to complete)
  [guestshell@guestshell ~]$ diff config.before config.after | wc -l  (Use diff again while using line count tool)
  ```
2. How many lines of code changed after running the update-config.sh?

## Review the config that changed
Run the following to see the changes in the config:
```
[guestshell@guestshell ~]$ diff config.before config.after
```
There is a short amount of output and the final line is the flag, including the open and closing brackets `<` and `>`.

1. Determine which feature was added by running `[guestshell@guestshell ~]$ diff config.before config.after`.

## Which IOS feature did the script add?
After running the `update-config.sh` script, notice the new config that was added. What is the feature found using 
the `GET` method? Note: `update-config.sh` applies the changes in `terraform.tf`.

