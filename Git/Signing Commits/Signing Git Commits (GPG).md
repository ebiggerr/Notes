# Signing Git Commits (GPG)

## GPG

What is GPG? https://gnupg.org/ 

---
## Install GPG together with Kleopatra 

https://www.gpg4win.org/download.html (Contains GPG together with Kleopatra)

Gpg4win 3.1.15 ( at the time of writing 2nd May 2021 )

---

## Start (After installation of all required software)

Open up the Kleopatra software.

File...

New Key Pair

Create A Personal OpenGPG key pair

Name

Email ( same email address as GitHub Account)

Advanced Settings
- RSA (4096 bit)

Optional (Protect the generated key with passphrase)

p.s. 1) Remember the Key ID

## Setup the Git 

``` git config --global user.signingkey <KEY ID>``` 

Command above : Configuring the Git to tell Git about your signing key


```git config --global commit.gpgsign true```

Configuring Git so that it know you want to use GPG signing.


```gpg --armor --export <KEY ID>``` 


This command above will export the public key. (Replace the <>section with own key id as mentioned above)


## Upload the GPG public key to Github
 
Settings

SSH and GPG keys

New GPG key

Paste the result of export of GPG [result](#Setup-the-Git) inside the text area 

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
<key>
-----END PGP PUBLIC KEY BLOCK-----
```

Add GPG key

Then you should see the GPG key is successfully addded to your account.

## Signing Commits

```git commit -m "Test signing commit with GPG" -S```

Assumed that you already have a local repository and you are ready to commit some files.

## Extra

``` gpg --list-secret-keys --keyid-format LONG ```

List all the keys

``` git config --global gpg.program "C:/Program Files (x86)/GnuPG/bin/gpg.exe" ```

Configuring the Git so that Git know where is the location of GPG software you are using ( Default installation path of GPG )



