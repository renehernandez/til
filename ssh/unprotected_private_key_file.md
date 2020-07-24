# Unprotected private key file

I was configuring a ssh key pair to authenticate against a remote repository as part of script and I ran into the following error, while doing the initial `git clone`:

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for '~/.ssh/key_name' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "~/.ssh/key_naem": bad permissions
```

As it turns out, ssh key files need to have permission so that it is only readable by its owner. To fix this, as part of the script configuration section, I added the following line after having all the ssh files in place:

```bash
chmod -R go-wrx ~/.ssh
```

which recursively removes the **write**, **read** and **execute** permissions for the **group** and **others** bits.
