# davinci-resolve in Void Linux

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

