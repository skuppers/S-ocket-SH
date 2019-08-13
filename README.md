# S(ocket)-SH

An SSH connection manager powered by ssh's controlmaster config file.

![socksh](https://user-images.githubusercontent.com/29956389/62934203-475c9400-bdc4-11e9-849c-d01bfa6ec387.png)

When started, it displays all known hosts listed in the ssh config file. Check if the destination is reachable, specifies the associated IP adress, aswell as the Socket Status.

## Configuration
If you don't know ssh's ControlMaster, I recommend you to RTFM.
To make short, it allows you to save the ssh's connection socket inside a directory, where it will stay for a specified time, before being deleted.
The default configuration file for this is at ~/.ssh/config.

An example file has been added to the repo, you better make your own one, but consider that the syntax for the ControlPath has to end with
> %r@%h:%p

![syntax](https://user-images.githubusercontent.com/29956389/62935022-4f1d3800-bdc6-11e9-904b-cd03d92a3dd4.png)

Be sure ton configure the script itself:
![conf](https://user-images.githubusercontent.com/29956389/62935494-948e3500-bdc7-11e9-93d7-c4ce52012bc7.png)

Be sure to check the permissions and the owner of the script aswell as the config file, as it could disclose important network information.

Now you just have to add your script to the PATH, and you ready to go!
