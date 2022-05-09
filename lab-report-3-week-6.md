# Week 6 Lab 4

## Streamlining `ssh` Configuration

My `.ssh/config` file:

![mySSHFile](mySSHFile.PNG)

Using the command `ssh ieng6` to login using just my alias:

![sshLogin](sshIeng6Login.PNG)

Copying over with just the alias:

![scpAlias](scpAlias.PNG)

## Setup Github Access from ieng6

Public key on Github:

![github](SSHKeyGithub.PNG)

Public and private key on the ieng6 server in .ssh:

![privateAndPublic](privateAndPublic.PNG)

[Committing](https://github.com/a1yao/markdown-parser/commit/08fd183c242087a083fc3b5ad0d3075e6ae5bcad) and pushing on ieng6:

![pushAndCommit](commitAndPush.PNG)

## Copy whole directories with `scp -r`

Copying over the entire markdown-parser directory:

![scpDir](scpDirectory.PNG)

Compiling and running in the copied directory on ieng6:

![compCopy](compCopy.PNG)

Using `scp`, `;`, and `ssh` to copy the whole directory and run the code in one line:

![oneLine](oneLine.PNG)