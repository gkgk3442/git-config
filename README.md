# git install

```
sudo apt install git
git --version
```

# git client config

```
git config --global credential.helper 'store --file ~/.git-credentials'
git config --global user.name shinssy
git config --global user.email test@test.com
git config --global http.sslVerify false
```

# git server config

```
git config --global pack.windowMemory 1g
git config --global pack.SizeLimit 1g
git config --global pack.threads 2
git config --global pack.window 0
```
