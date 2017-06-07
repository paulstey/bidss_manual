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
    3. (If you don’t already have it), Install Chocolately: https://chocolatey.org/install
        - `iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`
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


## SFTP Client
 
The SSH File Transfer Protocol (also Secure File Transfer Protocol, Secure FTP, or SFTP) is a network protocol that provides file access, file transfer, and file management functionalities over any reliable data stream<sup>[5](#footnote5)</sup>.
 
SFTP clients either provide a command-line interface such as the Terminal program on Mac or a graphical user interface (GUI) such as FileZilla that works with both Windows and Mac<sup>[6](#footnote6)</sup>.
 
1. Check if you already have a GUI-based SFTP client installed. If not, follow the instructions below for installing FileZilla, an open-source SFTP client
2. Download and install FileZilla Client
https://filezilla-project.org/
3. Open FileZilla and specify the following at the top:
    1. Host = `pbcbiedcit.services.brown.edu`
    2. Username = `<your Brown netid>`
    3. Password = `<your Brown password>`
    4. Port = `22`
4. Click “Quickconnect”
5. Once logged in, you should see a list of folders that are in your `pbcbiedcit` account – more about this later, for now click the “x” icon at the top to disconnect from the server.

_Note: Make sure you are on the VPN before trying to SFTP to the server._


## Text Editor
 
A text editor is a type of program used for editing plain text files<sup>[7](#footnote7)</sup>. Text editors are often provided with operating systems or software development packages, and can be used to change configuration files and programming language source code.
 
You likely already have a text editor installed on your machine (e.g., Notepad on Windows or TextEdit on Mac). Due to the variation in text editors, we will use __vim__<sup>[8](#footnote8)</sup> on `pbcbiedcit` and __Atom__<sup>[9](#footnote9)</sup> on your local machine (more about Atom later).


## Web Browser 

Given the variation in Web browsers, Google Chrome should be used for this course. If you do not have Google Chrome installed, please [download and install it from here](https://www.google.com/chrome/).


## IMPORTANT NOTES

1. Protect your files and directories on `pbcbiedcit.services.brown.edu`
    1. Multi-user environment
    2. Set permissions to restrict read, write, and execute access as necessary
2. __NO__ Protected Health information (PHI) or other sensitive information on `pbcbiedcit.services.brown.edu`
    1. Not HIPAA-compliant (Health Insurance Portability and Accountability Act)
    2. __Do not__ put clinical or other data that include PHI
    3. _For this class, we will use publicly accessible data or simulate data as needed_

___

<a name="footnote1">1</a>: https://en.wikipedia.org/wiki/Secure_Shell

<a name="footnote2">2</a>: https://en.wikipedia.org/wiki/Comparison_of_SSH_clients

<a name="footnote3">3</a>: https://en.wikipedia.org/wiki/Terminal_(macOS)

<a name="footnote4">4</a>: https://en.wikipedia.org/wiki/PuTTY

<a name="footnote5">5</a>: https://en.wikipedia.org/wiki/SSH_File_Transfer_Protocol

<a name="footnote6">6</a>: https://en.wikipedia.org/wiki/FileZilla

<a name="footnote7">7</a>: https://en.wikipedia.org/wiki/Text_editor

<a name="footnote8">8</a>: https://en.wikipedia.org/wiki/Vi

<a name="footnote9">9</a>: https://en.wikipedia.org/wiki/Atom_(text_editor)

