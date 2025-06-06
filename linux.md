# Linux cheat sheet  
## Find .git repos  
```
$ find / -name ".git"
```

## Browse git history
```
$ cd /path/to/dir

$ git log -p
$ git log --reflog
```
## SSH to remote  
```
$ ssh -p 1337 username@host
```  

## Remote files copy
```
$ scp [from] [to]
$ scp -r /path/to/local/dir user@remotehost:/path/to/remote/dir
$ scp -r username@from_host:/remote/directory/  /local/directory/
```
## Default ssh keys
```
~/.ssh/id_rsa.pub and ~/.ssh/id_rsa
```
