#!/bin/sh
GREEN='\033[1;32m'

path="/Applications/Roblox.app"
settings_path="$path/Contents/MacOS/ClientSettings"

echo "Choose the amount of frames you want"
read fps
if [ -d "/Applications/Roblox.app/Contents/MacOS/ClientSettings" ]; then
    echo "The folder exists."
    echo "{\"DFIntTaskSchedulerTargetFps\": $fps }" > "$settings_path/ClientAppSettings.json"
    echo "$GREEN FPS UNLOCKED${NC}"
else
    echo "The folder does not exist."
    mkdir -p "/Applications/Roblox.app/Contents/MacOS/ClientSettings"
    if [ -d "/Applications/Roblox.app/Contents/MacOS/ClientSettings" ]; then
        echo "The folder was successfully created."
        dasettings="/Applications/Roblox.app/Contents/MacOS/ClientSettings/ClientAppSettings.json"
        cat <<EOF > "$dasettings"
{
    "DFIntTaskSchedulerTargetFps": $fps
}
EOF
        echo "JSON file created at $dasettings"
    else
        echo "Failed to create the folder."
    fi
fi

