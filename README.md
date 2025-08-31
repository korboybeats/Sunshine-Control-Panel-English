# Sunshine Foundation Edition Streaming Guide
Sunshine-Foundation is based on the official nightly branch and is modified to improve the experience of connecting various streaming devices with a Windows host.


## Download Links
[Release Sunshine-Foundation v0.1 · qiin2333/Sunshine](https://github.com/qiin2333/Sunshine/releases/foundation)  
[Direct Mirror](https://mirror.ghproxy.com/https://github.com/qiin2333/Sunshine/releases/download/foundation/sunshine-windows-installer.exe)


## Installation
##### Prompt for uninstalling old version if not the first installation
- Choosing Yes will clear all previous configuration, including virtual display resolutions.
- Choosing No will keep the previous configuration.  
21 Recommendation: No
##### Installation options
- For first-time installation, it is recommended to select all components; for subsequent installations, select as shown in the image.
- IddSampleDriver (virtual HDR display) does not support Windows 10. [Click here to download the non-HDR version for Win10](https://github.com/itsmikethetech/Virtual-Display-Driver/releases/tag/23.10.20.2)
21 Recommendation: Use the default installation directory. Do not change it arbitrarily or install in a path with Chinese characters.


## Configuration
##### Pairing (pin)
![image](https://github.com/qiin2333/sunshine-control-panel/assets/2795904/073421a9-f2da-4656-8f4d-6eb3e766c887)  
TODO: Automatically apply specific configuration for different streaming devices.


##### Games & Applications
![image (1)](https://github.com/qiin2333/sunshine-control-panel/assets/2795904/d1caf52a-4f26-4aac-b2b9-c6857ddc5f13)  
Add or edit game executable paths as shown.

21 Recommendation: Use a game management tool [r](g) to manage all games on your host, so the streaming software only needs to point to Playnite.


##### Streaming Display Behavior
Sunshine Settings → Video/Audio

![image (2)](https://github.com/qiin2333/sunshine-control-panel/assets/2795904/a580b32c-2980-426d-bdcd-0c8a5d4563ad)  

Recommended settings: Set the display device to the available virtual display, and set "Deactivate Other Active Specified" to automatically turn off the physical display during streaming and restore it after streaming ends.

The Foundation Edition’s virtual display supports multiple resolutions and refresh rates. Additional resolutions can be added or modified from the menu.

If using a physical EDID emulator, you can modify its display parameters. Reference: [Monitor Overclocking Guide](https://meowbot.page/2021/09/02/monitor-overclocking/)


##### HDR
- HDR requirements:
    - HDR must be enabled on the host OS and connected to a host PC supporting HDR (virtual display or EDID emulator).
    - You must also enable HDR in the Moonlight client, otherwise the stream will be in SDR (HDR host may be overexposed).
    - Good HDR experience depends on correct HDR calibration on the OS and in games. Calibration may differ between host and client.
Intel, AMD, and NVIDIA GPUs supporting HEVC Main 10 or AV1 10-bit profiles support HDR streaming.

21 Recommendation: Calibrate your display through [r](g) streaming to the client and save the HDR calibration profile for streaming use.


## Advanced Usage
##### Supersampling Streaming
Method 1: Use Moonlight-Android Enhanced to adjust host scaling ratio.  
Method 2: Sunshine Settings → Video/Audio → Display device options → Remap display modes.


## Q&A
Q: Sunshine streaming cannot display XBOX GAMEBAR

A: Go to Settings → Advanced → Force a Specific Capture Method → WGC. You may need to stop the service and manually run the executable to test the new capture path. A simple batch script like below works:

```powershell
cd /d "c:\program files\sunshine"
net stop sunshineservice
sunshine.exe
````

## Related Resources

[Video Guide](https://www.bilibili.com/video/BV1xu4y1M7yq/)
[Sunshine Official Documentation](https://docs.lizardbyte.dev/projects/sunshine/en/latest/index.html)
[Streaming Device Decoding Performance - Moonlight Project](https://docs.qq.com/sheet/DSGxMdUl0UVZCeFRQ?tab=BB08J2)
[Unlock Dolby Atmos Streaming](https://docs.qq.com/pdf/DSEFKbExvRXRzVktF)
[Moonlight-Android Enhanced Edition](https://github.com/qiin2333/moonlight-android/releases/shortcut)
