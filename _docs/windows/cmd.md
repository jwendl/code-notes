---
title: Windows Commands
category: Windows
order: 1
---
# Windows Commands

## Find Ports in Use with PID

``` cmd
netstat -aon | find /i 127.0.0.1:7071
```

## Kill a Task from PID

``` cmd
taskkill /F /PID 27668
```
