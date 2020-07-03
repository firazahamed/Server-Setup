# Server-Setup
**List of Tasks:**
```
"System Update"
"Essential packages"
"CSF Firewall Install"
"Maldet Install"
```

**Execution:**

**Upload files to the required directory**
```
root@ansible-g:~/Server-Setup# ls
MainFile.yml     csf.blocklists  essn-packages.yml   system-update.yml
csf-install.yml  csf.conf        maldet-install.yml
```
**Run the main playbook file MainFile.yml**
```
root@ansible-g:~/Server-Setup# ansible-playbook MainFile.yml

PLAY [Server Initial Setup] **************************************************************************

TASK [Gathering Facts] *******************************************************************************
ok: [35.213.xxx.xxx]

TASK [System Update] *********************************************************************************
included: /root/Server-Setup/system-update.yml for 35.213.xxx.xxx

TASK [System update - Debian] ************************************************************************
changed: [35.213.xxx.xxx]

TASK [System update - RedHat] ************************************************************************
skipping: [35.213.xxx.xxx]

TASK [Essential packages] ****************************************************************************
included: /root/Server-Setup/essn-packages.yml for 35.213.xxx.xxx

TASK [YUM] *******************************************************************************************
skipping: [35.213.xxx.xxx]

TASK [APT] *******************************************************************************************
ok: [35.213.xxx.xxx]

TASK [CSF Firewall Install] **************************************************************************
included: /root/Server-Setup/csf-install.yml for 35.213.xxx.xxx

TASK [Download Package] ******************************************************************************
changed: [35.213.xxx.xxx]

TASK [Extracting package] ****************************************************************************
changed: [35.213.xxx.xxx]

TASK [Executing install script] **********************************************************************
changed: [35.213.xxx.xxx]

TASK [Copy config file] ******************************************************************************
changed: [35.213.xxx.xxx]

TASK [Copy blocklists file] **************************************************************************
changed: [35.213.xxx.xxx]

TASK [Restarting CSF and LFD] ************************************************************************
changed: [35.213.xxx.xxx] => (item=csf)
changed: [35.213.xxx.xxx] => (item=lfd)

TASK [Maldet Install] ********************************************************************************
included: /root/Server-Setup/maldet-install.yml for 35.213.xxx.xxx

TASK [Download Package] ******************************************************************************
ok: [35.213.xxx.xxx]

TASK [Create LMD's download dir] *********************************************************************
ok: [35.213.xxx.xxx]

TASK [Extracting package] ****************************************************************************
skipping: [35.213.xxx.xxx]

TASK [Executing install script] **********************************************************************
skipping: [35.213.xxx.xxx]

TASK [Updating Maldet] *******************************************************************************
changed: [35.213.xxx.xxx]

PLAY RECAP *******************************************************************************************
35.213.xxx.xxx             : ok=16   changed=8    unreachable=0    failed=0
```


