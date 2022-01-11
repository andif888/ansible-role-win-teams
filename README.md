ansible-role-win-teams
=========

Installs Microsoft Teams


Role Variables
--------------

The default values for the variables are set in defaults/main.yml:

```yaml
teams_vc_redist_download_url: 'https://aka.ms/vs/17/release/vc_redist.x64.exe'
teams_vc_redist_product_id: '{6DB765A8-05AF-49A1-A71D-6F645EE3CE41}'
teams_web_rtc_download_url: 'https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWQ1UW'
teams_download_url: 'https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true'
teams_is_wvd_environment: false
teams_per_machine_install: false
teams_installer_arguments: "{{ teams_per_machine_install | bool | ternary('ALLUSER=1 ALLUSERS=1', 'ALLUSERS=1') }}"

```

Example Playbook
----------------
---
- hosts: win10
  become: true
  gather_facts: true
  vars:
    teams_is_wvd_environment: true
    teams_per_machine_install: true

  roles:
    - ansible-role-win-teams
```yaml