
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

|Tunnel|Path|APIKey|username|password|limitip|expired|
|--|--|--|--|--|--|--|
|SSH/OpenVPN|/api/sshvpn|✅|✅|✅|✅|✅|


Contoh penggunaan menggunakan cURL (Linux Command)

curl -X POST \
  -H "Content-type: application/json" \
  -H "Authorization: Bearer rencongtunnel" \
  -d '{
    "username": "rencongtunnel",
    "password": "rencongtunnel",
    "limitip": 1,
    "expired": "30"
  }' \
  http://localhost:3000/api/sshvpn


**Catatan**

✅ - Diperlukan

