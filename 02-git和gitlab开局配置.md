# git和gitlab开局配置

> Date: 2023-10-18

## 0. git配置

**查询：**

```bash
## 查看全局配置信息
git config --global --list

## 查看仓库级别的配置信息
git config --local --list
```

git全局配置文件在 `C:/Users/pp/.gitconfig` ，也就是 `${HOME}/.gitconfig`

参考的内容：

```
[user]
	name = yourname
	email = yourname@domain.com
[core]
	autocrlf = false
[credential "http://10.30.10.200:10088"]
	provider = generic
[alias]
	ad = add .
	cmm = commit -m
	rlog = reflog
	co = checkout
	cob = checkout -b
```



## 1. cases

### 1.1 git alias

git alias配置：

```bash
git config --global alias.ad "add ."
git config --global alias.cmm "commit -m"
git config --global alias.rlog "reflog"
git config --global alias.co "checkout"
git config --global alias.cob "checkout -b"
```

### 1.2 warning: LF will be replaced by CRLF

参考链接：

- [关于git提示“warning: LF will be replaced by CRLF”终极解答](https://www.jianshu.com/p/450cd21b36a4)
- [What's the difference between git reset --mixed, --soft, and --hard?](https://stackoverflow.com/questions/3528245/whats-the-difference-between-git-reset-mixed-soft-and-hard)

在win上使用git的时候会遇到这个情况。

**解决方案：**

增加配置如下：

```bash
git config --global core.autocrlf false
```

### 1.3 git push的认证

CredentialHelperSelector配置：选择默认的manager-core即可

![image-20231016133830015](_MARKDOWN_ASSETS/02-git和gitlab开局配置.assets/image-20231016133830015.png)

<img src="_MARKDOWN_ASSETS/02-git和gitlab开局配置.assets/image-20231016134003977.png" alt="image-20231016134003977" style="zoom:67%;" />