# Play Docker

##  Basic Tech

## Linux Namespace

Linux Namespace是Kernel一个功能，用来隔离一系列系统资源

| Namespace 类型    | 系统调用参数  |
| ----------------- | ------------- |
| Mount Namespace   | CLONE_NEWNS   |
| UTS Namespace     | CLONE_NEWUTS  |
| IPC Namespace     | CLONE_NEWIPC  |
| PID Namespace     | CLONE_NEWPID  |
| Network Namespace | CLONE_NEWNET  |
| User Namespace    | CLONE_NEWUSER |

- UTS Namespace
  - 隔离nodename和domainname两个系统标识。每个Namespace允许有自己的hostname
- IPC Namespace
  - 隔离System V IPC 和 POSIX message queues。每个IPC namespace都有自己的System V IPC 和 POSIX message queues
- PID Namespace
  - 隔离进程ID的。同一个进程在不同PID Namespace里可以拥有不同PID。
- Mount Namespace
  - 隔离各个进程看到的挂载点视图
  - docker volume利用这个特性
- User Namespace
  - 隔离用户的用户组ID。一个进程的UserID和GroupID在User Namesapce内外是可以不同的。
- Network Namespace
  - 隔离网络设备、IP地址端口等网络栈Namespace
  - Net Namespace可以让每个容器拥有自己独立的虚拟网络设备