# ssh-notify

This script uses the [Panacea Public Push Service](http://labs.panaceamobile.com/push-public-sender/) 
to send a push notification to your mobile whenever anyone logs on your server using SSH.

Requires PAM and Python 3.

## Installation

Clone it anywhere. Then, just add this line to `/etc/pam.d/sshd`

	session optional /path/to/ssh-notify /path/to/configuration.json

You may want to instruct your package manager to never override this file again.

## Configuration

The configuration file is a JSON dictionnary. Example configuration :

	{
		"api_key": "...",
		"devices": ["device-1-id", "device-2-id"],
		"ignored-users": []
	}

* `api_key`: Obtained from Panacea Public Push Service
* `device-n-id`: Obtained from Panacea mobile application
* `ignored-users`: Don’t send notification for those users
