steps:

1. Generate a new SSH Key pair on local machine
2. copy public key to remote machine
3. Login to remote sever without password

Commands:

    ssh-keygen
    ssh-copy-id

 ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/soubha/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/soubha/.ssh/id_rsa
Your public key has been saved in /home/soubha/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:JWlLglVs12HlsiiE1VIDIhwXCIQDQEFS5vQvgEYmLXg soubha@BCP-PG02EKB2
The key's randomart image is:
+---[RSA 3072]----+
|@@Booo=+++o.oo.  |
|X=E.o= ++.oo..   |
|.=o o o.*o. . .  |
|.  . . = + . o   |
|    . . S . .    |
|     .   .       |
|                 |
|                 |
|                 |
+----[SHA256]-----+