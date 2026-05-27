# Davinci Resolve 20/21 in Void Linux. You are going to want to compile the rocm packages and have that set up so that davinci resolve can use it (with AMD Video Card).

- Download Davinci Resolve, unzip the file and run the installer:
```
./DaVinci_Resolve_Studio_20.0_Linux.run

The installer is going to complain about missing libraries. If it does, run this command:

SKIP_PACKAGE_CHECK=1 ./DaVinci_Resolve_Studio_20.0_Linux.run 
```
- To resolve issues with these type of errors "/usr/lib/libgdk_pixbuf-2.0.so.0: undefined symbol: g_task_set_static_name", do the following:

```
mkdir /opt/resolve/libs/disabled
mv /opt/resolve/libs/libgmodule-2.0.so* /opt/resolve/libs/disabled/
mv /opt/resolve/libs/libgio-2.0.so* /opt/resolve/libs/disabled/
mv /opt/resolve/libs/libglib-2.0.so* /opt/resolve/libs/disabled/
```
```
Install the ALSA bridge and tools:
```
sudo xbps-install -S alsa-pipewire alsa-utils
```
Create a per-user ALSA default to PipeWire:
```
printf '%s\n' 'pcm.!default { type pipewire }' 'ctl.!default { type pipewire }' > ~/.asoundrc
```
Log out and back in (or restart your session).

- Davinci Resolve should now launch as expected.

