### Docker

* Lista wszystkich aktywnych (uruchomionych) kontenerów

```
docker ps
```
<br>


* Lista pełna również kontenerów zatrzymanych (nieaktywne)

```
docker ps -a
```
<br>

* Szczegółowe informacje w formie listy

```
docker ps --format "table {{.ID}}\t{{.Names}}\t{{.Status}}"
```