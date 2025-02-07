# V2ray 搭建

```bash
sudo apt install wget unzip -y
# 安装
wget https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh
sudo bash install-release.sh
# 移除
sudo bash install-release.sh --remove
# 修改配置信息
sudo mkdir /usr/local/etc/v2ray
sudo vim /usr/local/etc/v2ray/config.json
# 重启服务
systemctl enable v2ray
systemctl restart v2ray
```

config.json:
```json
{
  "inbounds": [
    {
      "port": 12345, 
      "protocol": "vmess",
      "settings": {
        "clients": [
          {
            "id": "[UUID]",
            "alterId": 0
          }
        ]
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",  
      "settings": {}
    }
  ]
}
```