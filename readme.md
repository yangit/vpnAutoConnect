# VPN auto connect for mac

* Open `Script Editor`

```
on idle
	tell application "System Events"
		tell current location of network preferences
			set myConnection to the service "SERVICE_NAME"
			if myConnection is not null then
				if current configuration of myConnection is not connected then
					connect myConnection
				end if
			end if
		end tell
	end tell
	return 2
end idle
```
* Change `SERVICE_NAME` in the above script to actual value
* Save script as:
  - Type: `Application`
  - Check: `Stay open after Run handler`

* Run the app, or add it to Login items.