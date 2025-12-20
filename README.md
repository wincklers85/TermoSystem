🟢 TermoSystem – v1.0.1 RC
Sistema di monitoraggio e controllo termico per puffer, pompe e hopper pellet
Firmware per ESP8266 con display 128×64, mini OLED, WebApp animata e OTA
📘 Indice
Descrizione generale
Caratteristiche principali
Hardware richiesto
Schema dei collegamenti
Installazione firmware
Aggiornamenti OTA
Utilizzo del sistema
WebApp integrata
Temi grafici
Limitazioni e placeholder
Versione firmware
🔥 Descrizione generale
TermoSystem è un controller avanzato per impianti termici basati su puffer, pompe di circolazione e sistemi a pellet.
Progettato per ESP8266, include:
interfaccia grafica animata su display 128×64
OLED di diagnostica con pagine automatiche
WebApp moderna e dinamica con animazioni di flusso acqua
controlli da menu stile embedded
supporto WiFi, AP Mode e configurazione da browser
aggiornamento OTA
gestione pompa intelligente con isteresi anti-rimbalzo
gestione relè principali + AUX
lettura 4 sonde NTC (2 puffer, max/min)
Molte funzioni sono già operative, altre sono placeholder pronti per essere attivati nelle versioni successive.
⭐ Caratteristiche principali
✔ Display principale 128×64
Dashboard con 5 temi grafici
Animazione TermoSystem allo startup
Icona WiFi e orologio sincronizzato NTP
Indicatori puffer con colori caldo/freddo
Hopper pellet (placeholder sensore ultrasuoni)
✔ Mini OLED diagnostico
Mostra ciclicamente:
temperature
stato pompe
voltaggio alimentazione
info di rete
Animazione TermoSystem periodica
✔ Logica pompa avanzata
Attivazione alla temperatura impostata
Spegnimento con isteresi di 1.5 °C (anti ON/OFF rapido)
Modalità:
AUTO
FORZATO ON
FORZATO OFF
Secondo relè AUX configurabile dal menu
✔ 4 Sonde NTC
P1 MAX
P1 MIN
P2 MAX
P2 MIN
Sostituibili con sensore reale o placeholder
✔ WebApp completa
Dashboard animata
Animazione flusso acqua tra caldaia, puffer 1 e puffer 2
Indicazione stato pompa e AUX
Storico temperature (placeholder grafico)
Temi come sul display, incluso tema natalizio automatico
Pagina impostazioni con:
setpoint pompa
WiFi
orario e fuso
reset
abilitazione/disabilitazione sonde (placeholder)
✔ Avvio “stile Linux”
Boot log con controlli periferiche
Diagnostica completa
Animazione logo incrociato Termo / System
🔧 Hardware richiesto
Componente	Note
ESP8266 (NodeMCU, Wemos D1 Mini, ecc.)	MCU principale
Display 128×64 ST7567 o simile	Interfaccia grafica principale
OLED mini 128×64 (SSD1306)	Diagnostica
Relè pompa (GPIO12)	Controllo pompa impianto
Relè AUX (GPIO16 / D0)	Funzione aggiuntiva configurabile
4 Sonde NTC 10k	Temperatura puffer
ADS1115 (consigliato)	Espansione analogica futura
Sensore ultrasuoni (HC-SR04)	Hopper pellet (placeholder)
Alimentazione 5V stabile	Preferibilmente 2A
🛠 Schema dei collegamenti
ESP8266 → Display principale
SCL → GPIO14
SDA → GPIO13
VCC 5V
GND
ESP8266 → OLED diagnostico
SCL → GPIO15
SDA → GPIO4
Relè
Pompa → GPIO12
AUX → GPIO16 (D0)
Sonde NTC
(placeholder – dipende da futura implementazione ADS1115)
P1 MAX
P1 MIN
P2 MAX
P2 MIN
Hopper pellet
(placeholder – sensore ultrasuoni)
📦 Installazione firmware
Metodo 1 — Compilazione da Arduino IDE
Installa core ESP8266
Carica il file Build1.0.1RC/sketch_dec20a.ino
Imposta:
CPU 160 MHz
Flash 4M (3M SPIFFS o LittleFS)
Carica via USB
Metodo 2 — OTA via file .bin
Carica una prima volta via USB
Entra nella WebApp → Impostazioni → Aggiornamento
Seleziona il file .bin nella cartella:
OTA/TermoSystem_v1.0.1RC.bin
🌐 Aggiornamenti OTA
Il firmware supporta aggiornamento Over-The-Air tramite:
WebApp
Endpoint dedicato (POST)
Upload manuale
Se l’OTA fallisce:
controllare WiFi
controllare alimentazione stabile
non superare 1MB di file
🖥 Utilizzo del sistema
Navigazione display
Pulsanti:
SU / GIÙ → navigazione menu
OK → selezione
OK 2s → azione extra
Menu principale
Dashboard
Stato sistema
Impostazioni pompa
Impostazioni display
Temi grafici
Impostazioni orario
Impostazioni sistema
Diagnostica
Info firmware
🌐 WebApp integrata
Accesso tramite:
http://IP_DEL_DISPOSITIVO/app
Se non connesso al WiFi, il dispositivo crea una rete AP:
SSID: TermoSystemWifi
IP: 192.168.4.1
Funzionalità WebApp
Dashboard animata
Grafico storico (placeholder)
Stato pompa e AUX
Impostazione setpoint
Impostazione fuso e orologio
Tema selezionabile
Tema Natalizio attivo automaticamente il 25 dicembre
Controllo hopper (placeholder)
Controllo sonde (placeholder)
🎨 Temi grafici disponibili
Classic
Techno
Dark Lines
WaveFlow
Christmas (attivo automaticamente il 25 dicembre)
Dashboard e WebApp condividono la stessa estetica del tema selezionato.
⚠ Limitazioni attuali & Placeholder
Queste parti sono predisposte ma non completamente funzionanti nella RC:
Funzione	Stato
Sensore hopper pellet	Placeholder
Storico grafico WebApp	Placeholder
Attivazione/disattivazione sonde dal menu	Placeholder
Comunicazione con Arduino Nano come espansione I/O	Placeholder
ADS1115	Placeholder
Modelli dashboard aggiuntivi	In sviluppo
Animazioni avanzate pompa e flusso acqua WebApp	Versione base completata
🧬 Versione Firmware
v1.0.1 RC
Questa è una Release Candidate, include:
rifattorizzazione grafica
fix isteresi pompa
supporto AUX
temi multipli
animazioni migliorate
startup professionale
preparazione per future espansioni
✨ Credits
Sviluppo firmware & WebApp: Stephan Winckler
Design grafico e architettura del sistema: TermoSystem Project
