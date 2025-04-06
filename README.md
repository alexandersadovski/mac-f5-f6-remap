# Restore Keyboard Brightness Controls on macOS

This solution restores the original functionality of the F5 and F6 keys on macOS, enabling them to control keyboard brightness. On newer MacBooks, these keys are repurposed for other functions like controlling the microphone and Do Not Disturb mode. This setup remaps F5 to decrease keyboard brightness and F6 to increase it.

## Setup Instructions

```bash
# 1️⃣ Clone the Repository
# First, clone the repository to your local machine:
git clone https://github.com/alexandersadovski/mac-f5-f6-remap.git
```
```bash
# 2️⃣ Move the .plist File
# Move the .plist file to the ~/Library/LaunchAgents/ directory:
mv com.local.KeyRemapping.plist ~/Library/LaunchAgents/
```
```bash
# 3️⃣ Load the Launch Agent
# Activate the key remapping by loading the .plist configuration:
launchctl load ~/Library/LaunchAgents/com.local.KeyRemapping.plist
```
```bash
# 4️⃣ Unload the Launch Agent (Optional)
# To deactivate the remapping, unload the Launch Agent:
launchctl unload ~/Library/LaunchAgents/com.local.KeyRemapping.plist
```
```bash
# 5️⃣ Clear Key Remappings (If Necessary)
# If unloading doesn't revert the changes, clear the remappings manually:
/usr/bin/hidutil property --set '{"UserKeyMapping": []}'
```
```bash
# 6️⃣ Revert Changes
# To permanently remove the remapping, delete the .plist file and reboot your system:
rm ~/Library/LaunchAgents/com.local.KeyRemapping.plist
```
