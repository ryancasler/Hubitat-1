# Hubitat Logitech Harmony Hub Driver 

It is used to communicate via webSockets to a Logitech Harmony Hub and it creates child devices for each Harmony Activity.  Instant status updates are included as well!  No polling necessary to keep Hubitat updated when a user changes the Activity via a Harmony Remote Control or the Harmony Mobile Phone App.

v0.1.20181225 - Initial beta release

Instructions for use

NOTE: You must be running Hubitat Elevation firem ware version v2.0.3.109 or newer! 

**Create Hubitat Driver**
- Open up the "logitech-harmony-hub-parent.groovy" driver from this repository.  Make sure you hit the "RAW" button, then select/highlight all of the source code, and COPY everything (Ctrl-C on Windows, or right click->Copy). 
- In your Hubitat Elevation Hub's admin web page, select the "Drivers Code" section and then click the "+ New Driver" button in the top right corner.  This will open a editor window for manipulating source code.
- Click in the editor window.  Then PASTE all of the code you copied in the first step.
- Click the SAVE button in the editor window.
- Repeate the above setps to install the **required** HubDuino "Child Switch" Driver.  This is avilable at https://github.com/DanielOgorchock/ST_Anything/tree/master/HubDuino/Drivers

**Create the Logitech Harmony Hub Hubitat Device**
- In your Hubitat Elevation Hub's web page, select the "Devices" section, and then click the "+ Add Virtual Device" button in the top right corner.
- In the window that appears, please fill in the "Device Name", "Device Label", and "Device Network Id" fields.  Make sure the Device Network Id field is UNIQUE!  For example:
  - "Device Name" = "Family Room"
  - "Device Label" = {optional}
  - "Device Network Id" = FamilyRoomHarmonyHub  (Note:  make sure this is unique!)
- In the "Type" field, scroll to the bottom of the list and select "Logitich Harmony Hub Parent"
- Click Save
- In the next window that appears, fill in the "Device IP Address" with values appropriate to your application.  For example:
  - "Device IP Address" = 192.168.1.137   (this is the IP Address of my Logitich Harmony Hub device)
- Click Save
- Look at Live Logs (or Past Logs if you didn't have a tab open when you clicked SAVE)
- You should see all of the Child Devices created for your Logitich Harmony Hub
- You can now add these devices to the Hubitat Dashboard, use them in Rules, etc...
- Clicking "Refresh" in the parent device will simply cause a synchronization between your Harmony Hub and your Hubitat Hub's Chile Activity Switches.  This should not be necessary very often as this driver supports INSTANT STATUS UPDATES! :) 