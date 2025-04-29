# Windows Hacks

This repository holds information on how to get around working with windows when you are actually in love with UNIX, or
you interested in coding and feeling like hacking, or you simply never want to leave the terminal.


## WSL2

Obviously the easist way is to simply use WSL2. If set-up correctly, it allows you to feel like working on UNIX (most
distros are actually enable by default) without the overhead of a virtual machine. Some tricks are required to 
visualize GUI's and the network. However, it is generally hard to get access to all the devices connected to your 
machine. That can be very problamitic when trying to get cameras or robots in general to work.
More on that in [WSL-README](wsl/README.md).

## MSYS2

A recent things that I am delighted to have found out about is MSYS2. I have yet to understand what it actually is, but 
it says something about `native` and `pacman` so I was hooked. I will try to gather my setup here, but for now, I refer
to [MSYS2.org](https://www.msys2.org/).

The thing about startup speed and speed in general. Often times, these solutions result in authentifaction loops making
in highly slow to work with. A quick fix with explaination can be found at 
[Chennas blog](https://chenna.me/blog/2019/09/11/msys2-fix-slow-startup/).

## Git Bash

GIT Bash is on old classic to bring the unix world to Windows and should not be forgotten. My biggest drawback with
this is lacking support for many unix programs like tmux and grep.


## Terminal

The terminal application allows you to start whatever interface of the above you want to use. It can be configured via 
a json file and allows to have everything in the same place. Several `profiles` can be setup and my prefered is
```json
{
    "adjustIndistinguishableColors": "never",
    "bellStyle": "none",
    "colorScheme": "One Half Dark",
    "cursorShape": "filledBox",
    "experimental.retroTerminalEffect": false,
    "font": 
    {
        "face": "FiraCode Nerd Font",
        "size": 11,
        "weight": "light"
    },
    "guid": "{963ff2f7-6aed-5ce3-9d91-90d99571f53a}",
    "hidden": false,
    "name": "Ubuntu-24.04",
    "opacity": 100,
    "padding": "14",
    "source": "Windows.Terminal.Wsl",
    "useAcrylic": false
}
```

