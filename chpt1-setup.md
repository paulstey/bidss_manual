# Getting Set Up

For this course, computing will initially be done on an education server (`pbcbiedcit.services.brown.edu`) provided by the Brown Center for Biomedical Informatics (BCBI). You will interact with pbcbiedcit from your computer (laptop or desktop) using your Brown network identifier (netid) and password. Your computer is the “client” or “local” machine while pbcbiedcit is the “server” or “remote” machine.

## VPN Client

Brown's Virtual Private Network (VPN) connects you to Brown's network when you are off campus. You might use VPN to access campus-only resources like library resources or keyed software, or you might just want to secure your internet traffic when you are on public or untrusted WiFi.

1. [Enable Two-Step Verification for your Brown Account](https://ithelp.brown.edu/kb/articles/445-enable-two-step-verification-for-your-brown-account)
2. Install the [VPN F5 Desktop Client](https://www.brown.edu/information-technology/software/catalog/vpn-f5-desktop-client)
3. Open F5 and connect to the Brown VPN (see screen shots below).

    1. Open F5

        ![f5a](/images/f5a.png)

    2. Enter your Brown credentials

        ![f5b](/images/f5b.png)

    3. Select two-factor authentication method

        ![f5c](/images/f5c.png)

    4. After completing two-factor authentication, you will be connected to the VPN

        ![f5d](/images/f5d.png)


## SSH Client
Secure Shell (SSH) is a cryptographic network protocol for secure data communication, remote shell services or command execution and other secure network services between two networked computers that connects, via a secure channel over an insecure network, a server and a client (running SSH server and SSH client programs, respectively)<sup>[1](#footnote1)</sup>. An SSH client is a software program that uses the secure shell protocol to connect to a remote computer<sup>[2](#footnote2)</sup>.

_Note: Make sure you are on the VPN before trying to SSH to the server._


### SSH using macOS
1. Launch the Terminal application (under Applications → Utilities → Terminal) <sup>[3](#footnote3)</sup>
2. Type `ssh username@hostname` at the prompt and substitute your Brown netid for `username` and `pbcbiedcit.services.brown.edu` for `hostname`.
3. Enter your password when prompted (nothing will be appear as you type)
4. You are now logged on to `pbcbiedcit`! Type `ls` to see what happens.
5. We will be learning more about `pbcbiedcit`, but for now type `logout` or `exit`


### SSH using Windows (with PowerShell)
1. If you don’t have openssh installed: 
    1. Start PowerShell as an administrator (after finding PowerShell from Cortana, right click and select “Run as Administrator”
    2. (If you haven’t set execution policy), Type: `Set-ExecutionPolicy Unrestricted`
    3. (If you don’t already have it), Install Chocolately: https://chocolatey.org/install)
    `iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`
    4. Type: `choco install openssh`
    5. Type: `notepad $profile` (if prompted to create new file, select yes)
        1. Add following line to $profile file: `$env:TERM = ‘xterm’`
    6. Exit PowerShell and restart PowerShell (in regular mode)
2. Type `ssh username@hostname` at the prompt and substitute your Brown netid for `username` and `pbcbiedcit.services.brown.edu` for `hostname`.
3. Enter your password when prompted (nothing will be appear as you type)
4. You are now logged on to `pbcbiedcit`! Type `ls` to see what happens.
5. We will be learning more about pbcbiedcit, but for now type `logout` or `exit`


### SSH using Windows (_without_ PowerShell)
1. For Windows (without PowerShell)
2. Check if you already have an SSH client installed. If not, follow the instructions below for installing PuTTY<sup>[4](#footnote4)</sup>, a free and open source terminal emulator application
3. Download and install [PuTTY](https://www.brown.edu/information-technology/software/catalog/putty-ssh-client)
4. A shortcut to “PuTTY” should appear in the Start Menu (or go to the PuTTY menu and choose “PuTTY” to open the application)
5. In the PuTTY Configuration window, under Session, specify the following:
    1. Host Name (or IP address) = `pbcbiedcit.services.brown.edu`
    2. Port = `22`
    3. Connection type = `SSH`
    4. Saved Sessions = `pbcbiedcit`
6. Click “Save” to save this configuration for future use
7. Click “Open” to open the connection to pbcbiedcit
8. When prompted, provide your Brown netid and password
9. You are now logged on to pbcbiedcit! Type ls to see what happens.
10. We will be learning more about pbcbiedcit, but for now type logout or exit

<a name="footnote1">1</a>: https://en.wikipedia.org/wiki/Secure_Shell
<a name="footnote2">2</a>: https://en.wikipedia.org/wiki/Comparison_of_SSH_clients
<a name="footnote3">3</a>: https://en.wikipedia.org/wiki/Terminal_(macOS)
<a name="footnote4">4</a>: https://en.wikipedia.org/wiki/PuTTY
