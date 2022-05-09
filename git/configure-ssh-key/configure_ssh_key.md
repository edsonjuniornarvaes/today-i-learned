# Configure SSH key.

#### With SSH installed on the machine follow the steps below.`

##### Generate your new key.

``` bash
ssh-keygen -t rsa
```

##### View your new public key.
``` bash
cat /home/renan/.ssh/id_rsa.pub
```

##### Having generated the SSH key, copy and paste it into the location for the configuration in your git.
