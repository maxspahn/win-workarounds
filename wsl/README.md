# WSL2

There is a introductary documentation on the [Windows Learn
Page](https://learn.microsoft.com/en-us/windows/wsl/install), but it does not cover all required
steps to run MrDevelopment in WSL2.

## Prerequisites

- Windows 10 version 2004 or higher or Windows 11
- Admininstrator Rights for activation. Once it is activated, admin rights are no longer required.

## Enable WSL2

1. Enable WSL2 on Windows, there are plenty of tutorials.
    [Tutorial Sitepoint](https://www.sitepoint.com/wsl2/)

    ```bash
    wsl --install
    ```

2. Reboot your machine to enable the feature.
3. Make sure to update WSL2 to the latest version using the powershell and the command below.

    ```bash
    wsl --update
    ```

4. Install a Linux distribution. We use Ubuntu 22.04 LTS, but you can use any other distribution as well.

   ```bash
   wsl --install -d Ubuntu-22.04
   ```

5. The rendering should be enabled automatically, so these steps may
   not required because it is already setuped.
   This step is to ensure that WSL2 has access to systemd Inside WSL2,
   edit or create the file `/etc/wsl.conf` and add the following lines

    ```bash
    [boot]
    systemd=true
    ```

6. Shutdown WSL2 (`wsl --shutdown` from powershell) and start it again.

## Debugging with GLX

If you want to try out rendering then you
should setup the mesa utils and some related things:

1. Activate your WSL2 and log into it
2. Install the following libraries to enable glx support (this might be not a full list) inside WSL2

    ```bash
    sudo apt install libgl1-mesa-dev mesa-utils libgl1-mesa-dri libglx-mesa0 libglx-dev
    ```

3. Add the following to your .bashrc (or .zshrc) file `export GALLIUM_DRIVER=llvmpipe`
4. Try out the installation with `glxgears`. It should render some gears turning.

Now you should be good to go to perform rendering in WSL2. That includes tools like matplotlib and
opengl. Moreover, it is actually more reactive than any git-bash on windows itself.
