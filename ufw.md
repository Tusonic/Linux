## Uncomplicated Firewall
### Instalacja UFW

* Instalacja
```
apt install ufw
```

* Sprawdzenie statusu
```
ufw status
```
<br>

* Włączenie (pamiętaj aby dodać SSH)
```
ufw enable
```
<br>

* Wyłączenie
```
ufw disable
```
<br>

* Wyświetlenie listy (wyłączonej)
```
ufw show added
```

### ALLOW (umożliwić)

* Odblokowanie portu dla IP
```
ufw allow from [IP] to any port [port]
```
<br>

* Odblokowanie portu 

```
ufw allow [port]
```
<br>

### EDIT (edycja)

* Wyświetlenie listy
```
ufw status numbered
```

### DELETE (usuwanie)

* Wyświetlenie listy
```
ufw status numbered
```
```
ufw delete 2
```
```
sudo ufw delete allow 22
```





