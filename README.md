
Change Local Group Policy Editors Settings

start menu
gpedit.msc
right click and open as administrator
browse to 

# Full Encryption + USB Key At Boot

Administrative Templates 
'-> Windows Components
  '-> Bitlocker Drive Encryption
    '-> Operating System Drives
     '-> Require Additional Authentication At Startup
      '-> Press enable

### Settings should be set as:

![Screenshot](pics/group_policys.png)

      Configure TPM startup: Allow TPM
      Configure TPM Startup PIN: Allow Startup with TPM
      Conifgure TPM Startup Key. Require startup key with TPM
      Configure TPM startup key and PIN: Allow startup key and PIN with TPM

### Add keys to your USB:

![Screenshot](pics/bitlocker_require_usbkey.gif)

     manage-bde -protectors -add c: -TPMAndStartupKey usb_drive: 

### Delete Old Keys

     manage-bde -protectors -delete c:
