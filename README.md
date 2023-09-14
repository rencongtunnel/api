
# Rencong Tunnel API

API Key : `Bearer rencongtunnel`

API Port : `3000`

## Endpoint

Format

    http://[IP_SERVER]:[API_PORT]/[PATH]

Contoh :

    http://localhost:3000/api/sshvpn

## Create

Method : `POST`

|Protocol|Path|APIKey|username|password|limitip|bug|quota|expired|
|--|--|--|--|--|--|--|--|--|
|SSH/OpenVPN|/api/sshvpn|✅|✅|✅|✅|⛔️|⛔️|✅|
|VMess|/api/vmess|✅|✅|⛔️|✅|✅|✅|✅|

Contoh penggunaan menggunakan cURL (Linux Command)
```
curl -X POST \
  -H "Content-type: application/json" \
  -H "Authorization: Bearer rencongtunnel" \
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

## Response

Success

```
{
    "status": "success",
    "hostname": "127.0.0.1",
    "isp": "Rencong Tunnel Technology Co., Ltd.",
    "city": "Indonesia",
    "username": "rencongtunnel",
    "servername": "ns.rencongtunnel.com",
    "pubkey": "9c4aca7ea739d70140aeae19f6fb85244f619cc6be4dcc6362e5dcb4ddca3638",
    "password": "rencongtunnel",
    "exp": "Oct 14, 2023",
    "ovpn": "https://rencongtunnel.com:81/all-ovpn.zip",
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
        "cdn": "GET / HTTP/1.1[crlf]Host: rencongtunnel.com[crlf]Upgrade: websocket[crlf][crlf]",
        "wss": "GET wss://BUG.COM/ HTTP/1.1[crlf]Host: rencongtunnel.com[crlf]Upgrade: websocket[crlf][crlf]"
    }
}
```

Failed
```
{
    "ok": false,
    "description": "Error Message"
}
```
