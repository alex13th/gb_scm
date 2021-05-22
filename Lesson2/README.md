# Системы управления конфигурациями - Урок 2

## Задание

Установить и настроить Ansible. Результатом работы должен быть вывод Ansible -m setup.

## Результат

**~/.../Lesson2$ansible -m setup -i inventory/hosts cos7-server1**
<pre>
cos7-server1 | SUCCESS => {
    "ansible_facts": {
        "ansible_all_ipv4_addresses": [
            "192.168.0.25"
        ],
        "ansible_all_ipv6_addresses": [
            "fe80::a1a1:ba0d:bb50:6d83"
        ],
        "ansible_apparmor": {
            "status": "disabled"
        },
        "ansible_architecture": "x86_64",
        "ansible_bios_date": "12/01/2006",
        "ansible_bios_vendor": "innotek GmbH",
        "ansible_bios_version": "VirtualBox",
        "ansible_board_asset_tag": "NA",
        "ansible_board_name": "VirtualBox",
        "ansible_board_serial": "0",
        "ansible_board_vendor": "Oracle Corporation",
        "ansible_board_version": "1.2",
        "ansible_chassis_asset_tag": "NA",
        "ansible_chassis_serial": "NA",
        "ansible_chassis_vendor": "Oracle Corporation",
        "ansible_chassis_version": "NA",
        "ansible_cmdline": {
            "BOOT_IMAGE": "/vmlinuz-3.10.0-1160.el7.x86_64",
            "LANG": "en_US.UTF-8",
            "crashkernel": "auto",
            "quiet": true,
            "rd.lvm.lv": "centos/swap",
            "rhgb": true,
            "ro": true,
            "root": "/dev/mapper/centos-root"
        },
        "ansible_date_time": {
            "date": "2021-05-22",
            "day": "22",
            "epoch": "1621676366",
            "hour": "05",
            "iso8601": "2021-05-22T09:39:26Z",
            "iso8601_basic": "20210522T053926926433",
            "iso8601_basic_short": "20210522T053926",
            "iso8601_micro": "2021-05-22T09:39:26.926433Z",
            "minute": "39",
            "month": "05",
            "second": "26",
            "time": "05:39:26",
            "tz": "EDT",
            "tz_offset": "-0400",
            "weekday": "Суббота",
            "weekday_number": "6",
            "weeknumber": "20",
            "year": "2021"
        },
        "ansible_default_ipv4": {
            "address": "192.168.0.25",
            "alias": "enp0s3",
            "broadcast": "192.168.0.255",
            "gateway": "192.168.0.1",
            "interface": "enp0s3",
            "macaddress": "08:00:27:d1:39:4b",
            "mtu": 1500,
            "netmask": "255.255.255.0",
            "network": "192.168.0.0",
            "type": "ether"
        },
        "ansible_default_ipv6": {},
        "ansible_device_links": {
            "ids": {
                "dm-0": [
                    "dm-name-centos-root",
                    "dm-uuid-LVM-QW4Qv2RMmBiFsSh8r5I7YkFCWYLV0PEvQDCJ3fgf6L1dFAJiBD7R08NxQ0G9WvCc"
                ],
                "dm-1": [
                    "dm-name-centos-swap",
                    "dm-uuid-LVM-QW4Qv2RMmBiFsSh8r5I7YkFCWYLV0PEvnTqcimSuCXb7HVu8XlJkz3qwySwIFEVX"
                ],
                "sda": [
                    "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5"
                ],
                "sda1": [
                    "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5-part1"
                ],
                "sda2": [
                    "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5-part2",
                    "lvm-pv-uuid-STDeGb-9CID-ZhSl-7rKc-mcEq-lkFT-ueHHuA"
                ],
                "sr0": [
                    "ata-VBOX_CD-ROM_VB2-01700376"
                ]
            },
            "labels": {},
            "masters": {
                "sda2": [
                    "dm-0",
                    "dm-1"
                ]
            },
            "uuids": {
                "dm-0": [
                    "2a33dc53-5887-4bf0-9493-36d0426cb12e"
                ],
                "dm-1": [
                    "2545940a-7462-484e-8f76-62263389acc2"
                ],
                "sda1": [
                    "454a7eec-127e-4d00-a01a-fd14ddf80da3"
                ]
            }
        },
        "ansible_devices": {
            "dm-0": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [
                        "dm-name-centos-root",
                        "dm-uuid-LVM-QW4Qv2RMmBiFsSh8r5I7YkFCWYLV0PEvQDCJ3fgf6L1dFAJiBD7R08NxQ0G9WvCc"
                    ],
                    "labels": [],
                    "masters": [],
                    "uuids": [
                        "2a33dc53-5887-4bf0-9493-36d0426cb12e"
                    ]
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "",
                "sectors": "35643392",
                "sectorsize": "512",
                "size": "17.00 GB",
                "support_discard": "0",
                "vendor": null,
                "virtual": 1
            },
            "dm-1": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [
                        "dm-name-centos-swap",
                        "dm-uuid-LVM-QW4Qv2RMmBiFsSh8r5I7YkFCWYLV0PEvnTqcimSuCXb7HVu8XlJkz3qwySwIFEVX"
                    ],
                    "labels": [],
                    "masters": [],
                    "uuids": [
                        "2545940a-7462-484e-8f76-62263389acc2"
                    ]
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "",
                "sectors": "4194304",
                "sectorsize": "512",
                "size": "2.00 GB",
                "support_discard": "0",
                "vendor": null,
                "virtual": 1
            },
            "sda": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [
                        "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5"
                    ],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": "VBOX HARDDISK",
                "partitions": {
                    "sda1": {
                        "holders": [],
                        "links": {
                            "ids": [
                                "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5-part1"
                            ],
                            "labels": [],
                            "masters": [],
                            "uuids": [
                                "454a7eec-127e-4d00-a01a-fd14ddf80da3"
                            ]
                        },
                        "sectors": "2097152",
                        "sectorsize": 512,
                        "size": "1.00 GB",
                        "start": "2048",
                        "uuid": "454a7eec-127e-4d00-a01a-fd14ddf80da3"
                    },
                    "sda2": {
                        "holders": [
                            "centos-root",
                            "centos-swap"
                        ],
                        "links": {
                            "ids": [
                                "ata-VBOX_HARDDISK_VB16809ac9-5bf026e5-part2",
                                "lvm-pv-uuid-STDeGb-9CID-ZhSl-7rKc-mcEq-lkFT-ueHHuA"
                            ],
                            "labels": [],
                            "masters": [
                                "dm-0",
                                "dm-1"
                            ],
                            "uuids": []
                        },
                        "sectors": "39843840",
                        "sectorsize": 512,
                        "size": "19.00 GB",
                        "start": "2099200",
                        "uuid": null
                    }
                },
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "deadline",
                "sectors": "41943040",
                "sectorsize": "512",
                "size": "20.00 GB",
                "support_discard": "0",
                "vendor": "ATA",
                "virtual": 1
            },
            "sr0": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [
                        "ata-VBOX_CD-ROM_VB2-01700376"
                    ],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": "CD-ROM",
                "partitions": {},
                "removable": "1",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "deadline",
                "sectors": "2097151",
                "sectorsize": "512",
                "size": "1024.00 MB",
                "support_discard": "0",
                "vendor": "VBOX",
                "virtual": 1
            }
        },
        "ansible_distribution": "CentOS",
        "ansible_distribution_file_parsed": true,
        "ansible_distribution_file_path": "/etc/redhat-release",
        "ansible_distribution_file_variety": "RedHat",
        "ansible_distribution_major_version": "7",
        "ansible_distribution_release": "Core",
        "ansible_distribution_version": "7.9",
        "ansible_dns": {
            "nameservers": [
                "77.37.251.33",
                "77.37.255.30",
                "192.168.0.1",
                "fe80::1%enp0s3"
            ]
        },
        "ansible_domain": "",
        "ansible_effective_group_id": 0,
        "ansible_effective_user_id": 0,
        "ansible_enp0s3": {
            "active": true,
            "device": "enp0s3",
            "features": {
                "busy_poll": "off [fixed]",
                "fcoe_mtu": "off [fixed]",
                "generic_receive_offload": "on",
                "generic_segmentation_offload": "on",
                "highdma": "off [fixed]",
                "hw_tc_offload": "off [fixed]",
                "l2_fwd_offload": "off [fixed]",
                "large_receive_offload": "off [fixed]",
                "loopback": "off [fixed]",
                "netns_local": "off [fixed]",
                "ntuple_filters": "off [fixed]",
                "receive_hashing": "off [fixed]",
                "rx_all": "off",
                "rx_checksumming": "off",
                "rx_fcs": "off",
                "rx_gro_hw": "off [fixed]",
                "rx_udp_tunnel_port_offload": "off [fixed]",
                "rx_vlan_filter": "on [fixed]",
                "rx_vlan_offload": "on",
                "rx_vlan_stag_filter": "off [fixed]",
                "rx_vlan_stag_hw_parse": "off [fixed]",
                "scatter_gather": "on",
                "tcp_segmentation_offload": "on",
                "tx_checksum_fcoe_crc": "off [fixed]",
                "tx_checksum_ip_generic": "on",
                "tx_checksum_ipv4": "off [fixed]",
                "tx_checksum_ipv6": "off [fixed]",
                "tx_checksum_sctp": "off [fixed]",
                "tx_checksumming": "on",
                "tx_fcoe_segmentation": "off [fixed]",
                "tx_gre_csum_segmentation": "off [fixed]",
                "tx_gre_segmentation": "off [fixed]",
                "tx_gso_partial": "off [fixed]",
                "tx_gso_robust": "off [fixed]",
                "tx_ipip_segmentation": "off [fixed]",
                "tx_lockless": "off [fixed]",
                "tx_nocache_copy": "off",
                "tx_scatter_gather": "on",
                "tx_scatter_gather_fraglist": "off [fixed]",
                "tx_sctp_segmentation": "off [fixed]",
                "tx_sit_segmentation": "off [fixed]",
                "tx_tcp6_segmentation": "off [fixed]",
                "tx_tcp_ecn_segmentation": "off [fixed]",
                "tx_tcp_mangleid_segmentation": "off",
                "tx_tcp_segmentation": "on",
                "tx_udp_tnl_csum_segmentation": "off [fixed]",
                "tx_udp_tnl_segmentation": "off [fixed]",
                "tx_vlan_offload": "on [fixed]",
                "tx_vlan_stag_hw_insert": "off [fixed]",
                "udp_fragmentation_offload": "off [fixed]",
                "vlan_challenged": "off [fixed]"
            },
            "hw_timestamp_filters": [],
            "ipv4": {
                "address": "192.168.0.25",
                "broadcast": "192.168.0.255",
                "netmask": "255.255.255.0",
                "network": "192.168.0.0"
            },
            "ipv6": [
                {
                    "address": "fe80::a1a1:ba0d:bb50:6d83",
                    "prefix": "64",
                    "scope": "link"
                }
            ],
            "macaddress": "08:00:27:d1:39:4b",
            "module": "e1000",
            "mtu": 1500,
            "pciid": "0000:00:03.0",
            "promisc": false,
            "speed": 1000,
            "timestamping": [
                "tx_software",
                "rx_software",
                "software"
            ],
            "type": "ether"
        },
        "ansible_env": {
            "HOME": "/root",
            "LANG": "en_US.UTF-8",
            "LC_ADDRESS": "ru_RU.UTF-8",
            "LC_IDENTIFICATION": "ru_RU.UTF-8",
            "LC_MEASUREMENT": "ru_RU.UTF-8",
            "LC_MONETARY": "ru_RU.UTF-8",
            "LC_NAME": "ru_RU.UTF-8",
            "LC_NUMERIC": "ru_RU.UTF-8",
            "LC_PAPER": "ru_RU.UTF-8",
            "LC_TELEPHONE": "ru_RU.UTF-8",
            "LC_TIME": "ru_RU.UTF-8",
            "LESSOPEN": "||/usr/bin/lesspipe.sh %s",
            "LOGNAME": "root",
            "LS_COLORS": "rs=0:di=38;5;27:ln=38;5;51:mh=44;38;5;15:pi=40;38;5;11:so=38;5;13:do=38;5;5:bd=48;5;232;38;5;11:cd=48;5;232;38;5;3:or=48;5;232;38;5;9:mi=05;48;5;232;38;5;15:su=48;5;196;38;5;15:sg=48;5;11;38;5;16:ca=48;5;196;38;5;226:tw=48;5;10;38;5;16:ow=48;5;10;38;5;21:st=48;5;21;38;5;15:ex=38;5;34:*.tar=38;5;9:*.tgz=38;5;9:*.arc=38;5;9:*.arj=38;5;9:*.taz=38;5;9:*.lha=38;5;9:*.lz4=38;5;9:*.lzh=38;5;9:*.lzma=38;5;9:*.tlz=38;5;9:*.txz=38;5;9:*.tzo=38;5;9:*.t7z=38;5;9:*.zip=38;5;9:*.z=38;5;9:*.Z=38;5;9:*.dz=38;5;9:*.gz=38;5;9:*.lrz=38;5;9:*.lz=38;5;9:*.lzo=38;5;9:*.xz=38;5;9:*.bz2=38;5;9:*.bz=38;5;9:*.tbz=38;5;9:*.tbz2=38;5;9:*.tz=38;5;9:*.deb=38;5;9:*.rpm=38;5;9:*.jar=38;5;9:*.war=38;5;9:*.ear=38;5;9:*.sar=38;5;9:*.rar=38;5;9:*.alz=38;5;9:*.ace=38;5;9:*.zoo=38;5;9:*.cpio=38;5;9:*.7z=38;5;9:*.rz=38;5;9:*.cab=38;5;9:*.jpg=38;5;13:*.jpeg=38;5;13:*.gif=38;5;13:*.bmp=38;5;13:*.pbm=38;5;13:*.pgm=38;5;13:*.ppm=38;5;13:*.tga=38;5;13:*.xbm=38;5;13:*.xpm=38;5;13:*.tif=38;5;13:*.tiff=38;5;13:*.png=38;5;13:*.svg=38;5;13:*.svgz=38;5;13:*.mng=38;5;13:*.pcx=38;5;13:*.mov=38;5;13:*.mpg=38;5;13:*.mpeg=38;5;13:*.m2v=38;5;13:*.mkv=38;5;13:*.webm=38;5;13:*.ogm=38;5;13:*.mp4=38;5;13:*.m4v=38;5;13:*.mp4v=38;5;13:*.vob=38;5;13:*.qt=38;5;13:*.nuv=38;5;13:*.wmv=38;5;13:*.asf=38;5;13:*.rm=38;5;13:*.rmvb=38;5;13:*.flc=38;5;13:*.avi=38;5;13:*.fli=38;5;13:*.flv=38;5;13:*.gl=38;5;13:*.dl=38;5;13:*.xcf=38;5;13:*.xwd=38;5;13:*.yuv=38;5;13:*.cgm=38;5;13:*.emf=38;5;13:*.axv=38;5;13:*.anx=38;5;13:*.ogv=38;5;13:*.ogx=38;5;13:*.aac=38;5;45:*.au=38;5;45:*.flac=38;5;45:*.mid=38;5;45:*.midi=38;5;45:*.mka=38;5;45:*.mp3=38;5;45:*.mpc=38;5;45:*.ogg=38;5;45:*.ra=38;5;45:*.wav=38;5;45:*.axa=38;5;45:*.oga=38;5;45:*.spx=38;5;45:*.xspf=38;5;45:",
            "MAIL": "/var/mail/root",
            "PATH": "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin",
            "PWD": "/root",
            "SELINUX_LEVEL_REQUESTED": "",
            "SELINUX_ROLE_REQUESTED": "",
            "SELINUX_USE_CURRENT_RANGE": "",
            "SHELL": "/bin/bash",
            "SHLVL": "2",
            "SSH_CLIENT": "192.168.0.14 51462 22",
            "SSH_CONNECTION": "192.168.0.14 51462 192.168.0.25 22",
            "SSH_TTY": "/dev/pts/0",
            "TERM": "xterm-256color",
            "USER": "root",
            "XDG_RUNTIME_DIR": "/run/user/0",
            "XDG_SESSION_ID": "5",
            "_": "/usr/bin/python"
        },
        "ansible_fibre_channel_wwn": [],
        "ansible_fips": false,
        "ansible_form_factor": "Other",
        "ansible_fqdn": "cos7-server1",
        "ansible_hostname": "cos7-server1",
        "ansible_hostnqn": "",
        "ansible_interfaces": [
            "lo",
            "enp0s3"
        ],
        "ansible_is_chroot": false,
        "ansible_iscsi_iqn": "",
        "ansible_kernel": "3.10.0-1160.el7.x86_64",
        "ansible_kernel_version": "#1 SMP Mon Oct 19 16:18:59 UTC 2020",
        "ansible_lo": {
            "active": true,
            "device": "lo",
            "features": {
                "busy_poll": "off [fixed]",
                "fcoe_mtu": "off [fixed]",
                "generic_receive_offload": "on",
                "generic_segmentation_offload": "on",
                "highdma": "on [fixed]",
                "hw_tc_offload": "off [fixed]",
                "l2_fwd_offload": "off [fixed]",
                "large_receive_offload": "off [fixed]",
                "loopback": "on [fixed]",
                "netns_local": "on [fixed]",
                "ntuple_filters": "off [fixed]",
                "receive_hashing": "off [fixed]",
                "rx_all": "off [fixed]",
                "rx_checksumming": "on [fixed]",
                "rx_fcs": "off [fixed]",
                "rx_gro_hw": "off [fixed]",
                "rx_udp_tunnel_port_offload": "off [fixed]",
                "rx_vlan_filter": "off [fixed]",
                "rx_vlan_offload": "off [fixed]",
                "rx_vlan_stag_filter": "off [fixed]",
                "rx_vlan_stag_hw_parse": "off [fixed]",
                "scatter_gather": "on",
                "tcp_segmentation_offload": "on",
                "tx_checksum_fcoe_crc": "off [fixed]",
                "tx_checksum_ip_generic": "on [fixed]",
                "tx_checksum_ipv4": "off [fixed]",
                "tx_checksum_ipv6": "off [fixed]",
                "tx_checksum_sctp": "on [fixed]",
                "tx_checksumming": "on",
                "tx_fcoe_segmentation": "off [fixed]",
                "tx_gre_csum_segmentation": "off [fixed]",
                "tx_gre_segmentation": "off [fixed]",
                "tx_gso_partial": "off [fixed]",
                "tx_gso_robust": "off [fixed]",
                "tx_ipip_segmentation": "off [fixed]",
                "tx_lockless": "on [fixed]",
                "tx_nocache_copy": "off [fixed]",
                "tx_scatter_gather": "on [fixed]",
                "tx_scatter_gather_fraglist": "on [fixed]",
                "tx_sctp_segmentation": "on",
                "tx_sit_segmentation": "off [fixed]",
                "tx_tcp6_segmentation": "on",
                "tx_tcp_ecn_segmentation": "on",
                "tx_tcp_mangleid_segmentation": "on",
                "tx_tcp_segmentation": "on",
                "tx_udp_tnl_csum_segmentation": "off [fixed]",
                "tx_udp_tnl_segmentation": "off [fixed]",
                "tx_vlan_offload": "off [fixed]",
                "tx_vlan_stag_hw_insert": "off [fixed]",
                "udp_fragmentation_offload": "on",
                "vlan_challenged": "on [fixed]"
            },
            "hw_timestamp_filters": [],
            "ipv4": {
                "address": "127.0.0.1",
                "broadcast": "",
                "netmask": "255.0.0.0",
                "network": "127.0.0.0"
            },
            "ipv6": [
                {
                    "address": "::1",
                    "prefix": "128",
                    "scope": "host"
                }
            ],
            "mtu": 65536,
            "promisc": false,
            "timestamping": [
                "rx_software",
                "software"
            ],
            "type": "loopback"
        },
        "ansible_local": {},
        "ansible_lsb": {},
        "ansible_lvm": {
            "lvs": {
                "root": {
                    "size_g": "17.00",
                    "vg": "centos"
                },
                "swap": {
                    "size_g": "2.00",
                    "vg": "centos"
                }
            },
            "pvs": {
                "/dev/sda2": {
                    "free_g": "0",
                    "size_g": "19.00",
                    "vg": "centos"
                }
            },
            "vgs": {
                "centos": {
                    "free_g": "0",
                    "num_lvs": "2",
                    "num_pvs": "1",
                    "size_g": "19.00"
                }
            }
        },
        "ansible_machine": "x86_64",
        "ansible_machine_id": "5957b06a40251d41b779468f78ba2394",
        "ansible_memfree_mb": 536,
        "ansible_memory_mb": {
            "nocache": {
                "free": 802,
                "used": 188
            },
            "real": {
                "free": 536,
                "total": 990,
                "used": 454
            },
            "swap": {
                "cached": 0,
                "free": 2047,
                "total": 2047,
                "used": 0
            }
        },
        "ansible_memtotal_mb": 990,
        "ansible_mounts": [
            {
                "block_available": 224536,
                "block_size": 4096,
                "block_total": 259584,
                "block_used": 35048,
                "device": "/dev/sda1",
                "fstype": "xfs",
                "inode_available": 523962,
                "inode_total": 524288,
                "inode_used": 326,
                "mount": "/boot",
                "options": "rw,seclabel,relatime,attr2,inode64,noquota",
                "size_available": 919699456,
                "size_total": 1063256064,
                "uuid": "454a7eec-127e-4d00-a01a-fd14ddf80da3"
            },
            {
                "block_available": 4108896,
                "block_size": 4096,
                "block_total": 4452864,
                "block_used": 343968,
                "device": "/dev/mapper/centos-root",
                "fstype": "xfs",
                "inode_available": 8883695,
                "inode_total": 8910848,
                "inode_used": 27153,
                "mount": "/",
                "options": "rw,seclabel,relatime,attr2,inode64,noquota",
                "size_available": 16830038016,
                "size_total": 18238930944,
                "uuid": "2a33dc53-5887-4bf0-9493-36d0426cb12e"
            }
        ],
        "ansible_nodename": "cos7-server1",
        "ansible_os_family": "RedHat",
        "ansible_pkg_mgr": "yum",
        "ansible_proc_cmdline": {
            "BOOT_IMAGE": "/vmlinuz-3.10.0-1160.el7.x86_64",
            "LANG": "en_US.UTF-8",
            "crashkernel": "auto",
            "quiet": true,
            "rd.lvm.lv": [
                "centos/root",
                "centos/swap"
            ],
            "rhgb": true,
            "ro": true,
            "root": "/dev/mapper/centos-root"
        },
        "ansible_processor": [
            "0",
            "AuthenticAMD",
            "AMD Ryzen 7 3700X 8-Core Processor"
        ],
        "ansible_processor_cores": 1,
        "ansible_processor_count": 1,
        "ansible_processor_nproc": 1,
        "ansible_processor_threads_per_core": 1,
        "ansible_processor_vcpus": 1,
        "ansible_product_name": "VirtualBox",
        "ansible_product_serial": "0",
        "ansible_product_uuid": "5957B06A-4025-1D41-B779-468F78BA2394",
        "ansible_product_version": "1.2",
        "ansible_python": {
            "executable": "/usr/bin/python",
            "has_sslcontext": true,
            "type": "CPython",
            "version": {
                "major": 2,
                "micro": 5,
                "minor": 7,
                "releaselevel": "final",
                "serial": 0
            },
            "version_info": [
                2,
                7,
                5,
                "final",
                0
            ]
        },
        "ansible_python_version": "2.7.5",
        "ansible_real_group_id": 0,
        "ansible_real_user_id": 0,
        "ansible_selinux": {
            "config_mode": "enforcing",
            "mode": "enforcing",
            "policyvers": 31,
            "status": "enabled",
            "type": "targeted"
        },
        "ansible_selinux_python_present": true,
        "ansible_service_mgr": "systemd",
        "ansible_ssh_host_key_ecdsa_public": "AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBPve+22YoOcBitFdn71QMHHzJSottAEh3ofbNP3XzXFa6CKOE05P1p6ACaxntlY2xFZr/GrEk51K9Bn4OXBZIdE=",
        "ansible_ssh_host_key_ecdsa_public_keytype": "ecdsa-sha2-nistp256",
        "ansible_ssh_host_key_ed25519_public": "AAAAC3NzaC1lZDI1NTE5AAAAIAg3a+zzDG1nvgzCIsWdvIfToCvp11HEMfRO+q26qiwy",
        "ansible_ssh_host_key_ed25519_public_keytype": "ssh-ed25519",
        "ansible_ssh_host_key_rsa_public": "AAAAB3NzaC1yc2EAAAADAQABAAABAQCnFN/eWwes4jEHQEIyblPd09Lqd4wWHuPO/s67KfUWcatWUIClWe6AjvcRKcE92rxVJVfOXvbT3wusiLW7TxduxI3DkkVTe++AR705u8i6wrRKHByPL8u15glwbcfi2u8XEfpZmqHHkfXyVpprat/A35ypPCR3p223ssP1dNIRXamVO1zlkIo4+zXre/gLZhAL+z9MIRA1yK10TcglYZdb98nvYX9FMb3AwjVn1M1qgw4MRNycE4o7Ld+ZPayZo16OQvXLiaK4vdkF229KvcimBt7R8NOBOhIeyg2g9VpsJOkGV7fHxlNwRQUhOJyb/BTYXoID8S8FeWMnXsPHWuSn",
        "ansible_ssh_host_key_rsa_public_keytype": "ssh-rsa",
        "ansible_swapfree_mb": 2047,
        "ansible_swaptotal_mb": 2047,
        "ansible_system": "Linux",
        "ansible_system_capabilities": [
            "cap_chown",
            "cap_dac_override",
            "cap_dac_read_search",
            "cap_fowner",
            "cap_fsetid",
            "cap_kill",
            "cap_setgid",
            "cap_setuid",
            "cap_setpcap",
            "cap_linux_immutable",
            "cap_net_bind_service",
            "cap_net_broadcast",
            "cap_net_admin",
            "cap_net_raw",
            "cap_ipc_lock",
            "cap_ipc_owner",
            "cap_sys_module",
            "cap_sys_rawio",
            "cap_sys_chroot",
            "cap_sys_ptrace",
            "cap_sys_pacct",
            "cap_sys_admin",
            "cap_sys_boot",
            "cap_sys_nice",
            "cap_sys_resource",
            "cap_sys_time",
            "cap_sys_tty_config",
            "cap_mknod",
            "cap_lease",
            "cap_audit_write",
            "cap_audit_control",
            "cap_setfcap",
            "cap_mac_override",
            "cap_mac_admin",
            "cap_syslog",
            "35",
            "36+ep"
        ],
        "ansible_system_capabilities_enforced": "True",
        "ansible_system_vendor": "innotek GmbH",
        "ansible_uptime_seconds": 1638,
        "ansible_user_dir": "/root",
        "ansible_user_gecos": "root",
        "ansible_user_gid": 0,
        "ansible_user_id": "root",
        "ansible_user_shell": "/bin/bash",
        "ansible_user_uid": 0,
        "ansible_userspace_architecture": "x86_64",
        "ansible_userspace_bits": "64",
        "ansible_virtualization_role": "guest",
        "ansible_virtualization_type": "virtualbox",
        "discovered_interpreter_python": "/usr/bin/python",
        "gather_subset": [
            "all"
        ],
        "module_setup": true
    },
    "changed": false
}
</pre>