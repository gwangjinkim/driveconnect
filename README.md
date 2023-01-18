# Installation

```
pip install driveconnect
```
Or:
```
pip install git+https:\\github.com\gwangjinkim\driveconnect.git
```
Or:
```
pipenv install git+https:\\github.com\gwangjinkim\driveconnect.git#egg=driveconnect
```
Or:
```
poetry add driveconnect  # version number: driveconnect==0.1.8
```
Or (from github repo):
```
poetry add git+ssh://git@github.com/gwangjinkim/driveconnect.git#main
```

# Usage

```
import driveconnect as dcn
import pycryptaes as pca
import logging

# instanciate encryptor
ca = pca.AES()

# set logger
logging.basicConfig(filename='mylog.log', filemode='a', level=logging.DEBUG)

# test, wether a drive e.g. 'G:' is connected:
dcn.is_drive_connected(drive_letter='G') # it works also with "G:"
## False

# in the terminal/console/REPL to save some typing:
home = "C:/Users/myusername"
p = lambda x: f"{home}/{x}"   # helper function
args = (p(".key"), p(".user"), p(".pass"))

# set the credentials for the server in local folders
ca.generate_key_user_pass(*args)

# connect to the server
# leading '\\' can be left out in server address and the 'M:' as well as 'M' both work
dcn.connect_drive('G:', '\\serveraddress\folder', co=co)
# or for connections where no credentials are needed:
dcn.connect_drive('G:', '\\serveraddress\folder', _print=True)
# or with logger
dcn.connect_drive('G:', '\\serveraddress\folder', log=logging, level="info", _print=True)



# disconnect from the server
dcn.disconnect_drive('G:', _print=True)
# or with logger:
dcn.disconnect_drive('G:', log=logging, level="info")
```
