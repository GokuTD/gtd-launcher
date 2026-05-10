---
name: Bug report
about: Something doesn't work as expected
title: "[BUG] "
labels: bug
assignees: ''
---

**What happens**
A clear and concise description of the bug.

**What you expected**
What you thought should happen instead.

**Steps to reproduce**
1. Go to '...'
2. Tap on '...'
3. Press '...'
4. See error

**Device info**
- TV / device model: (e.g. Nvidia Shield TV Pro 2019, Chromecast with Google TV, Mecool KM2…)
- Android TV version: (Settings → System → About → Android TV OS version)
- Launcher version: (Settings → Premium → bottom of menu — or `adb shell dumpsys package com.gtd.tv.launcher | grep versionName`)
- Plugin version (if installed): same way for `com.gtd.tv.plugin`
- Premium status: free / premium

**Logcat**
If the bug crashes the launcher or shows an error toast, please attach a logcat. Quick way:

```
adb logcat -d -t 500 > logcat.txt
```

Then upload the file to this issue (or paste relevant lines if short).

**Screenshots / video**
If the issue is visual or about UX, drop a screenshot or short clip here.

**Anything else**
Network setup, multi-user device, recent system updates, third-party launchers also installed, etc.
