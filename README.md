# ansible-role-win-teams

Role to install Microsoft Teams on Windows

## Table of content

- [Default Variables](#default-variables)
  - [teams_installer_arguments](#teams_installer_arguments)
  - [teams_installer_arguments_autostart](#teams_installer_arguments_autostart)
  - [teams_installer_run_uninstall_first](#teams_installer_run_uninstall_first)
  - [teams_is_32bit](#teams_is_32bit)
  - [teams_is_wvd_environment](#teams_is_wvd_environment)
  - [teams_no_autostart](#teams_no_autostart)
  - [teams_per_machine_install](#teams_per_machine_install)
  - [teams_register_addinloader](#teams_register_addinloader)
  - [teams_remove_hklm_autorun](#teams_remove_hklm_autorun)
  - [teams_vc_redist_download_url](#teams_vc_redist_download_url)
  - [teams_vc_redist_product_id](#teams_vc_redist_product_id)
  - [teams_web_rtc_download_url](#teams_web_rtc_download_url)
  - [teams_x64_download_url](#teams_x64_download_url)
  - [teams_x86_download_url](#teams_x86_download_url)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### teams_installer_arguments

Teams installer arguments

#### Default value

```YAML
teams_installer_arguments: "{{ teams_per_machine_install | bool | ternary('ALLUSER=1\
  \ ALLUSERS=1', 'ALLUSERS=1') }}"
```

### teams_installer_arguments_autostart

Teams installer arguments regarding autostart

#### Default value

```YAML
teams_installer_arguments_autostart: "{{ teams_no_autostart | bool | ternary('OPTIONS=\"\
  noAutoStart=true\"','') }}"
```

### teams_installer_run_uninstall_first

Set to true to uninstall Teams first. This cause the machine-wide installer to truly update.

#### Default value

```YAML
teams_installer_run_uninstall_first: false
```

### teams_is_32bit

Set to true to install 32-bit version of Teams

#### Default value

```YAML
teams_is_32bit: false
```

### teams_is_wvd_environment

Set to true if installed in Azure Virtual Desktop environment

#### Default value

```YAML
teams_is_wvd_environment: false
```

### teams_no_autostart

Set to true if Teams should not autostart at logon

#### Default value

```YAML
teams_no_autostart: false
```

### teams_per_machine_install

Set to true if installed as machine-wide installation

#### Default value

```YAML
teams_per_machine_install: false
```

### teams_register_addinloader

Set to true to register Teams addin loader machine-wide

#### Default value

```YAML
teams_register_addinloader: false
```

### teams_remove_hklm_autorun

Set to true to remove autorun setting in HKLM

#### Default value

```YAML
teams_remove_hklm_autorun: false
```

### teams_vc_redist_download_url

VC Redistributable download URL

#### Default value

```YAML
teams_vc_redist_download_url: https://aka.ms/vs/17/release/vc_redist.x64.exe
```

### teams_vc_redist_product_id

VC Redistributable product ID

#### Default value

```YAML
teams_vc_redist_product_id: '{A181A302-3F6D-4BAD-97A8-A426A6499D78}'
```

### teams_web_rtc_download_url

Web RTC download URL

#### Default value

```YAML
teams_web_rtc_download_url: https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWQ1UW
```

### teams_x64_download_url

Teams 64-bit download URL

#### Default value

```YAML
teams_x64_download_url: https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true
```

### teams_x86_download_url

Teams 32-bit download URL

#### Default value

```YAML
teams_x86_download_url: https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
