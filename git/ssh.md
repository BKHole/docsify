# SSH key

SSH Key 的目的是使得客户端和服务端之间建立信任，这种信任表现在两端通信的过程中不需要输入密码即可。

### 生成key

``` code 
ssh-keygen -t rsa -C "xxxxxxx@163.com"
```

### 查看公钥

``` code
// 查看本地生成默认名为id_rsa的公钥
cat ~/.ssh/id_rsa.pub
```
