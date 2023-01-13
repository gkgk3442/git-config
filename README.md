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

# git 소스 압축파일 생성
```
#!/bin/sh
name=`git remote -v | grep origin | head -n1 | awk '{print $2}' | sed -e 's,.*:\(.*/\)\?,,' -e 's/\.git$//'`
#branch=`git symbolic-ref -q --short HEAD`
branch=`git branch --show-current | sed -e 's/\//_/g'`
#commitId=`git rev-parse --verify HEAD`
commitId=`git show -s --format=%H`
datetime=`git show -s --date=format:'%Y%m%d_%H%M%S%z' --format=%cd`

git archive --format=tar.gz -o ${name}_${branch}_${datetime}_${commitId}.tar.gz HEAD
```
