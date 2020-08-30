---
description: Page with concepts and examples about encryption.
---

# Encryption

## What is Encryption?

My motivation to understand encryption was using the software for backups called borg. Since it uses GPG to encrypt the backups and i was having some issues regarding the encryption itself, i decided to start from scratch.

Encryption is a two-way function, meaning.. 

## How to use GPG on Ubuntu \(18.04\)

As talked in the beginning of the concepts of this section, GPG uses an assymetrical encryption, or PKI \(Public Key Interface\), meaning it has two different keys. This assumes you have already generated your key and we just want to encrypt/decrypt a file.

I followed this tutorial: [https://www.digitalocean.com/community/tutorials/how-to-use-gpg-to-encrypt-and-sign-messages](https://www.digitalocean.com/community/tutorials/how-to-use-gpg-to-encrypt-and-sign-messages)

But even though it didn't make clear for me how the GPG actually works in practice when you want to send someone a file, in this case i'm sending myself a file to test it out.

As said before, this assume we have already generated our GPG keys, but just to make sure it was generated:

![](.gitbook/assets/image%20%2812%29.png)

First we create a txt file:

![](.gitbook/assets/image%20%2811%29.png)

Then we encrypt it using gpg flag command --encrypt and we HAVE to specify the recipient, if this recipient is not valid then it will return an error. The name of the output file can be chosen as you wish and the format as well \(asc, gpg..\)

![When the email address is correct the encrypted file is generated](.gitbook/assets/image%20%283%29.png)

Note that somehow it checks on a database if the email is valid or not.

![](.gitbook/assets/image%20%286%29.png)

Just to make sure we don't make any confusion here i'm going to delete the original file `unencrypted-file.txt`:

![See that the only thing left is the encrypted file](.gitbook/assets/image%20%2810%29.png)

To decrypt our file, we just have to: `$ gpg encrypted-file.txt.asc` :

![](.gitbook/assets/image%20%284%29.png)

See that when using gpg without arguments/flags it doesn't know what to do, so it guesses, in this case he knows that we want to decrypt it, so what he does is create a decrypted file with the same name without the extension asc. It's important to note that i inserted my passphrase already, so it didn't prompt in the screen for me, but usually it would be prompted.

Another way to have more control when decrypting is:

![](.gitbook/assets/image%20%2813%29.png)

Some useful sources that i found to understand better GPG: [https://github.com/whatbirdisthat/gpg-hello-world](https://github.com/whatbirdisthat/gpg-hello-world)

## Using same GPG key in Windows 10 \(created originally in Ubuntu\)

{% embed url="https://unix.stackexchange.com/questions/184947/how-to-import-secret-gpg-key-copied-from-one-machine-to-another" %}



## Hashing vs Encryption

While hashing is based on one-way functions, i.e: functions that are easy to compute an input but hard to invert them given a random image.

