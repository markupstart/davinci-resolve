# Davinci Resolve 20 in Debian 13. You are going to want to install the rocm packages and have that set up so that davinci resolve can use it.

- Download Davinci Resolve, unzip the file and run the installer:
```
./DaVinci_Resolve_Studio_18.6.6_Linux.run
```
- To resolve issues with these type of errors "/usr/lib/libgdk_pixbuf-2.0.so.0: undefined symbol: g_task_set_static_name", do the following:

```
mkdir /opt/resolve/libs/disabled
mv /opt/resolve/libs/libgmodule-2.0.so* /opt/resolve/libs/disabled/
mv /opt/resolve/libs/libgio-2.0.so* /opt/resolve/libs/disabled/
mv /opt/resolve/libs/libglib-2.0.so* /opt/resolve/libs/disabled/
```
- You will also need to add glu in order for Davinci Resolve to launch:

```
sudo xbps-install glu
```
- Davinci Resolve should now launch as expected.

