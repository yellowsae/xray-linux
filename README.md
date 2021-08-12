

###  Xray Linux客户端使用



下载： [xray](https://github.com/XTLS/Xray-core/releases) 

根据linux的框架下载不同xray版本



创建一个文件夹，将下载的 xray.zip  移动到这个文件夹

```bash
# 解压 
unzip xray-linux-64.zip  

# 验证 
./xray  --version 

# 创建配置文件夹 
mkdir  /usr/local/share/xray
mkdir /var/log/xray
mkdir /usr/local/etc/xray


# 移动文件
# 服务文件
chmod 777 xray.service  xray@.service 
mv xray.service  xray@.service  /etc/systemd/system

mv geoip.dat geosite.dat /usr/local/share/xray

# 运行文件
mv xray   /usr/local/bin 

# 配置文件  config.json 
cp config.json  /usr/local/etc/xray 



# 运行 xray 
systemctl  restart xray 
systemctl enable xray 
```

---





#### proxychains

配置好 xray 后，再使用 `proxychains`一个Linux终端代理工具，配置端口代理既可以使用 

`echo  "alias pc='proxychains' " >> ~/.zshrc   ` 

`source ~/.zshrc `





