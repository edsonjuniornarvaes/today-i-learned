Generate your new key.

``` bash
ssh-keygen -t rsa
```

View your new public key.
``` bash
cat /home/${you_user}/.ssh/id_rsa.pub
```

---

In this example I use github, after generating the key and copying it, go to settings > **SSH and GPG keys** > **New SSH key**, generate a title and insert your key, after clicking on **Add SSH key**.
 
If you generated the key correctly it will be accepted and from now on you can use your ssh key however you want.

---

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ol4ljxgoek3llb4xbqz4.png)
