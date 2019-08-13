# S(ocket)-SH

An SSH connection manager powered by ssh's controlmaster config file.

![socksh](https://user-images.githubusercontent.com/29956389/62934203-475c9400-bdc4-11e9-849c-d01bfa6ec387.png)

When started, it displays all known hosts listed in the ssh config file. Checks if the destination is reachable, specifies the associated IP address, as well as the Socket Status.

## Configuration
![dgr](https://user-images.githubusercontent.com/29956389/62971405-1014d400-be12-11e9-81fd-f243fe5cf34a.png)
Be sure to configure the permissions and the owner of the script as well as the config file properly, as it could disclose important network information.

If you don't know ssh's ControlMaster, I recommend you to read the fancy manual.
In short, it allows you to save the ssh's connection socket inside a directory, where it will stay for a specified amount of time, before being deleted.
The default configuration file for this is at ~/.ssh/config.

An example file has been added to the repo, but you better create your own one. If you don't want to modify the script to work consider that the syntax for the ControlPath has to end with
> %r@%h:%p

![syntax](https://user-images.githubusercontent.com/29956389/62935022-4f1d3800-bdc6-11e9-904b-cd03d92a3dd4.png)

Be sure to configure the script itself:
![conf](https://user-images.githubusercontent.com/29956389/62935494-948e3500-bdc7-11e9-93d7-c4ce52012bc7.png)


Now you just have to add your script to the PATH, and you ready to go!

## Troubleshoot
If you find yourself not beeing able to connect to a server, and the script just loops over the selection screen, you can delete the `while [ 1 ] ; do` and the `done` at the bottom end of the file to further investigate why the ssh connection can not established.
