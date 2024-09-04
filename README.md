# Setting up the Xray with XTLS and reality

## Requirements

1. VM with 1 Gbytes RAM and 1 CPU (core)
   1. 1 Gbytes and 2-4 cores won't hurt
2. Xray binaries that you can download [here](https://github.com/XTLS/Xray-core).
3. Terminal application
4. VSCode or something like it.

## Plan

1. Get the VM.
2. Setup SSH, RSA keys, paswordless login to the remote server
3. Download the binaries.
4. Configure service.
   1. Make it run
5. Configure proxy.
6. Select client application.
7. Configure client application.

## Get the VM

This will be out of scope.

You need to find, select, the cloud provider you like.

Find an offering for a VM (droplet, ec2, or whatever they call the compute) with 1 Gbytes RAM and 2 CPU cores.

VM can be with shared CPU, it's okay.

Disks can be any.

Network, huh. The faster the better. At least 1 Tb traffic to be allowed. Unlimited will be better, but for personal use 1 Tb is enough.

Don't use it for torrenting, the clous provider usually cooperate with the holders of the rights for movies and other stuff, so they discover your endpoint soon enough and grab your arse.

## Setup SSH, RSA keys, paswordless login to the remote server

### Where: local machine

### Setting up ssh

Do we have RSA keys for SSH at all?

```shell
ls -l ~/.ssh | grep id_rsa
```

If you see summat like this

```shell
username@my-expensive-macbook-look % ls -l ~/.ssh | grep id_rsa
-rw-------@ 1 username  staff   3434 Jul 25  2023 id_rsa
-rw-------@ 1 username  staff    743 Jul 25  2023 id_rsa.pub
```

Then is it really your MacBook or you stole it?

If you want to understand what are those keys, you can use the following command to check.

```shell
ssh-keygen -lf ~/.ssh/id_rsa
```

you'll get something like

```shell
username@mum-look-no-hands .ssh % ssh-keygen -lf ~/.ssh/id_rsa
4096 SHA256:uEKV9Byz...3z...EhcRX...EzACM ole.luckoye@mail.server (RSA)
```

If the output of the command is empty, then we'll create a new RSA keys pair.

```shell
ssh-keygen -t rsa -b 4096 -C name.surname@mail.server
```

The `-C` switch stands for Comment, basically you can write a poem there for you to understand, what is it for.







