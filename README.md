# cf_ddns
cloudflare 动态 DNS（DDNS）！Cloudflare 的 DDNS 功能允许您通过 API 更新您的域名解析记录，使之适用于动态 IP 地址。

## 食用说明
### 第一步，安装curl，crontab
Debian <br>
```shell
apt install curl -y
```
```shell
apt install cron -y
```
### 第一步，下载脚本
```shell
wget https://raw.githubusercontent.com/jinqians/cd_ddns/main/cf_ddns.sh
```
### 第二步，获取API密钥
打开cloudflare，在My Profile--->API Tokens中获取Global API密钥，并更改脚本以下内容
用您的信息替换 <YOUR_EMAIL>、<YOUR_API_KEY>、<YOUR_DOMAIN> 和 <二级域名>
### 第三步，运行脚本
```shell
bash cf_ddns.sh
```
### 第四步，设置定时任务
```shell
crontab -e
```  
5分钟运行一次
```shell
*/5 * * * * /bin/bash/`**path** *更改为自己的路径*`/cf_ddns.sh
```
