# Davinci Resolve 20 in Debian 13. You are going to want to install the rocm packages and have that set up so that davinci resolve can use it.

- Download Davinci Resolve, unzip the file and run the installer:
```
./DaVinci_Resolve_Studio_18.6.6_Linux.run

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
- Davinci Resolve should now launch as expected.

