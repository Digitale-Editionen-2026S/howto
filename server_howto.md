# Das Internet – Eine kurze Einführung

## 1) Was ist das Internet?
- Ein weltweites Netzwerk von Netzwerken von Computern.
- Computer tauschen Daten in kleinen Einheiten (Pakete) aus.
- Zwei Säulen:
  - Hardware: Kabel, Funk (WLAN, Mobilfunk), Switches, Router, Rechenzentren.
  - Software/Protokolle: IP, TCP/UDP, DNS, HTTP(S), u. v. m.

---

## 2) Vom Kupferkabel zum Protokollstapel

- Physikalisch: Kupfer/Glasfaser/Funk übertragen Bits.
- Link-Layer: MAC-Adressen, Switches (innerhalb eines lokalen Netzes/LAN).
- Netzwerk-Layer: IP-Adressen, Routing zwischen Netzen.
- Transport-Layer: TCP (zuverlässig) oder UDP (schnell, ohne Garantie).
- Anwendung: HTTP(S), SMTP, FTP, DNS, …

Beispiel-Stack:
- Client: Anwendung → HTTP → TCP → IP → Ethernet/WLAN → Medium

---

## 3) Adressen, Ports und Pakete

- IP-Adressen
- Port: Dienst auf einem Gerät, z. B. HTTP 80, HTTPS 443
- Socket: Kombination aus IP + Port, z. B. `203.0.113.5:443`
- Paket: enthält Quell-/Ziel-IP (Netzwerkschicht) und ggf. TCP/UDP mit Quell-/Ziel-Port (Transportschicht)

---

## 4) Subnetze und Router

- Subnetz: Gruppe von IPs, die „direkt“ erreichbar sind.
- Subnetzmaske/Prefix: z. B. `192.168.1.0/24` (Maske 255.255.255.0)
- Router: verbindet verschiedene Netze; entscheidet, wohin Pakete weitergeleitet werden.

Kleines Diagramm (LAN mit Router ins Internet):

```
[PC A]  [PC B] – [PC C]    [Router]====[Internet]
  |        |               |
 [ S w i t c h ]-----------+
   LAN: 192.168.1.0/24
   Router-LAN-IP: 192.168.1.1 (Gateway)
```

- Standard-Gateway: Router-IP im eigenen Netz, an die „fremde“ Ziele gesendet werden.

---

## 5) URLs und DNS

- URL-Beispiel: `https://www.beispiel.de:443/pfad?x=1#anker`
  - Schema: `https`
  - Hostname: `www.beispiel.de`
    - Top-Level-Domain (TLD): `de`
    - Second-Level-Domain (SLD): `beispiel`
    - Subdomain: `www`
  - Port: `443` (optional, Standard für HTTPS)
  - Pfad/Query/Fragment: `/pfad?x=1#anker`
- DNS: „Telefonbuch“ des Internets. Übersetzt Namen in IPs.

DNS-Resolver-Ablauf:

```
[Client] -> fragt -> [DNS-Resolver des ISP]
    falls Cache-Miss:
        Resolver fragt rekursiv:
        Root -> TLD (.de) -> autoritativer DNS (beispiel.de)
<- IP-Antwort zurück an Client
```
---

## 6) HTTP/HTTPS und ein GET-Request

- HTTP: Protokoll für Webseiten (Anwendungsschicht) – gilt allgemein als suboptimal
- HTTPS: HTTP + TLS-Verschlüsselung (Transport gesichert) – schützt vor Abhören und Manipulation

Ablauf: URL → Seite


1) URL eintippen (https://www.google.com)
2) DNS: Hostname -> IP
3) [TCP-Verbindung](https://de.wikipedia.org/wiki/Transmission_Control_Protocol) / [TLS-Handshake](https://de.wikipedia.org/wiki/Transport_Layer_Security)
5) HTTP GET / senden
6) Server antwortet mit Status + Headers + Body (HTML/CSS/JS/Bilder)

Mini-Sequenzdiagramm:

```
Client                       Server
  |------ DNS (resolve) ------>|
  |<----- IP-Adresse ----------|
  |=== TCP Handshake =========>|
  |=== TLS Handshake =========>|
  |--- GET / HTTP/1.1 -------->|
  |<-- 200 OK + Inhalt --------|
```
---

# Einen Lokalen HTTP-Server starten

Um einen **lokalen** (also nur auf Ihrem Rechner erreichbaren) Development-Server zu starten, sollten Sie zunächst HTML-Dateien generieren.
Navigieren Sie dann in das HTML-Verzeichnis und starten Sie einen Server. Je nach Betriebssystem können Sie den folgenden Befehl verwenden:

```bash
python -m http.server
# bzw.
python -m http.server --bind 127.0.0.1
# bzw.
python3 -m http.server --bind 127.0.0.1
```
