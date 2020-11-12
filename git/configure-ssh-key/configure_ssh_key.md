# Configure SSH key.

#### With SSH installed on the machine follow the steps below.

##### Check for the existence of the SSH key.

``` bash
$ cat ~ / .ssh / id_rsa.pub
```

##### Enter the following command with your git account if the SSH key does not exist.

``` bash
$ ssh-keygen -t rsa -b 2048 -C "your_git_account@example.com"
```

##### Having generated the SSH key, copy and paste it into the location for the configuration in your git.
