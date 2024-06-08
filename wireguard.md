# WireGuard

## Uruchomienie WireGuard

Start

```
wg-quick up wg0
```

Stop

```
wg-quick down wg0

```
Status
```
wg
```

## Tworzenie plików konfiguracyjnych

Plik konfiguracyjny znajdue się:
```
/etc/wireguard/wg0.conf
``` 

## Generowanie kluczy 
#### Server
```
wg genkey | tee server_privatekey | wg pubkey > server_publickey

```
#### Client
```
wg genkey | tee client1_privatekey | wg pubkey > client1_publickey
```