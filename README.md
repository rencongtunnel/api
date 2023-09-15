# Rencong Tunnel API

## Configuration

File konfigurasi

    /etc/rencongtunnel/.env
    
## Access

Melihat Port dan API Key

    cat /etc/rencongtunnel/.env

Output

    APIKEY=2b28e25a-4003-4326-bf92-c20e42d02d45
    LISTEN_PORT=3000

API Key : `2b28e25a-4003-4326-bf92-c20e42d02d45 `

API Port : `3000`

## Endpoint

Format

    http://[IP_SERVER]:[API_PORT]/[PATH]

Contoh :

    http://localhost:3000/api/sshvpn

## Create

Method : `POST`

|Protocol|Path|APIKey|username|password|limitip|quota|expired|
|--|--|--|--|--|--|--|--|
|SSH/OpenVPN|/api/sshvpn|✅|✅|✅|✅|⛔️|✅|
|VMess|/api/vmess|✅|✅|⛔️|✅|✅|✅|
|VLess|/api/vless|✅|✅|⛔️|✅|✅|✅|
|Trojan|/api/trojan|✅|✅|⛔️|✅|✅|✅|
|Shadowsocks|/api/shadowsocks|✅|✅|⛔️|✅|✅|✅|
|Shadowsocks22|/api/shadowsocks22|✅|✅|⛔️|✅|✅|✅|
|Socks5|/api/socks5|✅|✅|✅|✅|✅|✅|


Contoh penggunaan menggunakan cURL (Linux Command)
```
curl -X POST \
  -H "Content-type: application/json" \
  -H "Authorization: Bearer 2b28e25a-4003-4326-bf92-c20e42d02d45" \
  -d '{
    "username": "rencongtunnel",
    "password": "rencongtunnel",
    "limitip": 1,
    "expired": 30
  }' \
  http://localhost:3000/api/sshvpn
```

**Catatan**

✅ - Diperlukan

⛔️ - Tidak digunakan


## Trial

Method : `POST`

|Protocol|Path|expired|
|--|--|--|
|SSH/OpenVPN|/api/trialsshvpn|✅|
|VMess|/api/trialvmess|✅|
|VLess|/api/trialvless|✅|
|Trojan|/api/trialtrojan|✅|
|Shadowsocks|/api/trialshadowsocks|✅|
|Shadowsocks22|/api/trialshadowsocks22|✅|
|Socks5|/api/trialsocks5|✅|

**Catatan**
- Untuk trial menggunakan sistem menit ! tidak lebih 24 Jam Reset jam 00:00 !!!  


## Delete

Method : `DELETE`

|Protocol|Path|username|
|--|--|--|
|SSH/OpenVPN|/api/deletesshvpn|✅|
|VMess|/api/deletevmess|✅|
|VLess|/api/deletevless|✅|
|Trojan|/api/deletetrojan|✅|
|Shadowsocks|/api/deleteshadowsocks|✅|
|Shadowsocks22|/api/deleteshadowsocks22|✅|
|Socks5|/api/deletesocks5|✅|


## Response

Success

```
{
    "status": true,
    "message": "Create Account Success !",
    "hostname": "47.254.76.110",
    "isp": "Alibaba (US) Technology Co., Ltd.",
    "city": "San Jose",
    "username": "rencongtunnel",
    "servername": "mqq3gvs.ghosts.my.id",
    "pubkey": "4dda98891f5f753df06f4ed3929f936649ec2f7a06d65e7c884787f5badacc6d",
    "password": "rencongtunnel",
    "exp": "Sep 18, 2023",
    "ovpn": "https://uk.ghosts.my.id:81/all-ovpn.zip",
    "port": {
        "openssh": "443, 80, 22",
        "dropbear": "443, 109",
        "dropbearws": "443, 109",
        "sshws": 80,
        "sshwsssl": 443,
        "sshtls": 443,
        "ovpnwsssl": 443,
        "ovpnssl": 443,
        "ovpntcp": "443, 1194",
        "ovpnudp": 2200,
        "squid1": 3128,
        "squid2": 8000,
        "squid3": 8080,
        "badvpnudp": "7100, 7300, 7300"
    },
    "payload": {
        "cdn": "GET / HTTP/1.1[crlf]Host: uk.ghosts.my.id[crlf]Upgrade: websocket[crlf][crlf]",
        "wss": "GET wss://BUG.COM/ HTTP/1.1[crlf]Host: uk.ghosts.my.id[crlf]Upgrade: websocket[crlf][crlf]"
    }
}
```

Failed
```
{
    "status": "error"
}
```
