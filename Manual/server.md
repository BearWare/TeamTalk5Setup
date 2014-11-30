# TeamTalk Server Setup {#teamtalkserver}

This section explains how to set up a TeamTalk server. This is a quite
complicated procedure so users who are not so skilled with network
setup are advised to use the public TeamTalk servers which are
available in the Connect to Server dialog (press F2). To be able to
set up a TeamTalk server you first you need to ensure that the
TeamTalk server was installed when you ran the TeamTalk
installation. If it is installed there will be a folder called
"TeamTalk NT Service" in the "TeamTalk 5" program group of Windows'
start-menu.

Here's an overview of this section:

- [Configuring and Installing the TeamTalk Server as an NT service](@ref ntservice)
- [Installing multiple NT Services](@ref multintservice)
- [TeamTalk Server on Linux and Mac OS X](@ref tt5srv)

# Configuring and Installing the TeamTalk Server as an NT service {#ntservice}

To install the TeamTalk server click "Install TeamTalk NT Service" in
the TeamTalk 5 program group. On Windows this will bring up User
Access Control (UAC) since the TeamTalk server requires Administrator
access. The TeamTalk server will now run it's configuration wizard
(its "-wizard" option). If you want to change the server's default
settings or set up user accounts you need to run the configuration
wizard and answer 'y' to the first question.

Here is an example of how to set up a server with an administrator
user account. The user account has the username 'admin' and password
'admin'.

![Configure TeamTalk Server](serverconfig.png "Configure TeamTalk Server")

Once the server is up and running you can connect to the server using
the administrator user account that you just created. Use the
[user account dialog](@ref useraccountsdlg) to create more user accounts
for the server.


# Installing multiple NT Services {#multintservice}

To install multiple TeamTalk 5 NT Services the **sc.exe** command can
be used. Here is an example:\verbatim
sc.exe create "TeamTalk Server 2" binPath= "C:\MyServer\tt5svc.exe -wd c:\MyServer" start= auto
\endverbatim

The service in the above example will be called "TeamTalk Server 2" in
the NT service list. Notice the spaces after binPath and start. For
some strange reason these are required.

To start the above service run:\verbatim
sc.exe start "TeamTalk Server 2"
\endverbatim

To stop it type:\verbatim
sc.exe stop "TeamTalk Server 2"
\endverbatim

To uninstall it type:\verbatim
sc.exe delete "TeamTalk Server 2"
\endverbatim

# TeamTalk Server on Linux and Mac OS X {#tt5srv}

The Linux and Mac OS X distributions of TeamTalk also include a
TeamTalk server which can run both in daemon mode and as a regular
console application. On Linux the TeamTalk server binary is called
**tt5srv** and is located in the **server**-subfolder after untar'ing
the archive.

On Mac OS X the server binary is also called teamtalkd and is located
in **Applications/TeamTalk5.app/Contents/Server** subfolder after
installing the TeamTalk .dmg file.

For instructions on how to configure and run the TeamTalk server
(tt5srv) simply type:\verbatim
./tt5srv
\endverbatim
To start the TeamTalk server setup-wizard type:\verbatim
./tt5srv -wizard
\endverbatim

When running the setup-wizard then make sure the executable is run at
a writable location so it's possible for the setup-wizard to save its
changes to disk.

