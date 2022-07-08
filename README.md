# Installation

```
pip install driveconnect
```
Or:
```
pip install git+https:\\github.com\gwangjinkim\driveconnect.git
```

# Usage

```
import driveconnect as dcn

# test, wether a drive e.g. 'M:' is connected:
dcn.is_drive_connected(drive_letter='M') # without the ':'!
## False

# set the credentials for the server in local folders
dcn.pss.set_credentials('.\.user', '.\.pass')

# connect to the server
# cave - with or without leading '\\' for the server!
dcn.connect_drive('M:', '\\serveraddress\file', '.\.user', '.\.pass')

# disconnect from the server
dcn.disconnect_drive('M:')
```