# hidpi-chrome-on-ubuntu-20.04

```
sudo vi gnome-control-center/default-apps/google-chrome.xml
```

```
- <command>/opt/google/chrome/google-chrome %s</command>
+ <command>/opt/google/chrome/google-chrome --force-device-scale-factor=1.5 %s</command>
