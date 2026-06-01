Needs processors with avx instruction set
- default processors for VMs (ex: x86-64-v2-AES on proxmox) may not have avx, so splunk 10.* will not work
- can change processor to x86-64-v3 on proxmox to use vCPUs with avx instruction set

[Install universal forwarder](https://help.splunk.com/en/splunk-cloud-platform/forward-and-process-data/universal-forwarder-manual/10.4/install-the-universal-forwarder/install-a-windows-universal-forwarder#a19ec22d_68d3_4a7f_b41c_456267545717--en__Install_a_Windows_universal_forwarder_from_an_installer) (on Windows)
[configure universal forwarder](https://help.splunk.com/en/splunk-cloud-platform/forward-and-process-data/universal-forwarder-manual/10.4/configure-the-universal-forwarder/configure-the-universal-forwarder-using-configuration-files) (on Linux)
