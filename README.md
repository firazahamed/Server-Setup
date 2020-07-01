# Server-Setup
**List of actions:**
```
"System Update"
"Essential packages"
"CSF Firewall Install"
"Maldet Install"
```

**Upload files:**
```
root@ansible-g:~/Server-Setup# ls
MainFile.yml     csf.blocklists  essn-packages.yml   system-update.yml
csf-install.yml  csf.conf        maldet-install.yml
```

**Execution:**
```
root@ansible-g:~/Server-Setup# ansible-playbook MainFile.yml

PLAY [Server Initial Setup] **************************************************************************

TASK [Gathering Facts] *******************************************************************************
ok: [35.213.187.109]

TASK [System Update] *********************************************************************************
included: /root/Server-Setup/system-update.yml for 35.213.187.109

TASK [System update - Debian] ************************************************************************
changed: [35.213.187.109]

TASK [System update - RedHat] ************************************************************************
skipping: [35.213.187.109]

TASK [Essential packages] ****************************************************************************
included: /root/Server-Setup/essn-packages.yml for 35.213.187.109

TASK [YUM] *******************************************************************************************
skipping: [35.213.187.109]

TASK [APT] *******************************************************************************************
ok: [35.213.187.109]

TASK [CSF Firewall Install] **************************************************************************
included: /root/Server-Setup/csf-install.yml for 35.213.187.109

TASK [Download Package] ******************************************************************************
changed: [35.213.187.109]

TASK [Extracting package] ****************************************************************************
changed: [35.213.187.109]

TASK [Executing install script] **********************************************************************
changed: [35.213.187.109]

TASK [Copy config file] ******************************************************************************
changed: [35.213.187.109]

TASK [Copy blocklists file] **************************************************************************
changed: [35.213.187.109]

TASK [Restarting CSF and LFD] ************************************************************************
changed: [35.213.187.109] => (item=csf)
changed: [35.213.187.109] => (item=lfd)

TASK [Maldet Install] ********************************************************************************
included: /root/Server-Setup/maldet-install.yml for 35.213.187.109

TASK [Download Package] ******************************************************************************
ok: [35.213.187.109]

TASK [Create LMD's download dir] *********************************************************************
ok: [35.213.187.109]

TASK [Extracting package] ****************************************************************************
skipping: [35.213.187.109]

TASK [Executing install script] **********************************************************************
skipping: [35.213.187.109]

TASK [Updating Maldet] *******************************************************************************
changed: [35.213.187.109]

PLAY RECAP *******************************************************************************************
35.213.187.109             : ok=16   changed=8    unreachable=0    failed=0
```


