---
id: 1buiybkrabkm13cvlcksahk
title: 3 Use of Bashrc and Zshrc
desc: ''
updated: 1705006930168
created: 1705004705242
---

The file **.zshrc** and **.bashrc** are the configuration files for this types of shells.


This section is simply, to see something thins, imagine you want to show your private ip:
- TO get you private ip there are several ways, a one of them is: `ip addr show enp8s0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}'`
- In your console you can write: `echo "My private IP is: $( ip addr show enp8s0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')"`
- But, also in your **.zshrc** you can write this to do this in a more confortable way:
  ```bash
  function seemyip(){
    echo "My private IP is: $( ip addr show enp8s0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')"
  }
  ```
- Then, in your console you can write `seemyip`.

## How can I know what Shell im using

- `ps -p $$` or `echo "$SHELL"`