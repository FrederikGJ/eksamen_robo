# Eksmaen Robotics - forår 2024 - valgfag 

Noter til robotics eksamen. 

## Komponenter brugt til at bygge vores robotbil

- NodeMCU SP8266 
- L298N Motor Driver Module
- Motor Type TT Double-Shaft 1:48 Gear motor 3V-6V DC
- MG996R High Torque
Metal Gear Dual Ball Bearing Servo 
- Komponenter fra byggesystemet som man finder i abstractica repository

**Jeg skal beskrive komponenterne og hvad vi har brugt dem til**

## Vores proces 

Vi har som studiegruppe haft en proces der bærer præg af en empirisk tilgang, hvor vi prøvede
os frem og fejlede, hvorefter vi lærte af vores fejl. Vi har løbende opdelt gruppen i mindre
grupper, der arbejder enten p˚a at bygge den fysiske bil, eller p˚a at programmere Node MCU
eller samle de elektroniske dele.

## Læring 

- 3D print
- Lower Level Programming
- Asynkron programmering 
- Elektronik og hardware

## Serial Peripheral Interface
Serial Peripheral Interface (SPI) er en seriel kommunikationsprotokol, der anvendes til kortdistancekommunikation, primært i indlejrede systemer. SPI bruges ofte til at overføre data mellem en mikrocontroller og perifere enheder som sensorer, hukommelseschips, skærme og andre enheder.

Grundlæggende Funktioner

SPI er en synkron seriel kommunikationsprotokol, hvilket betyder, at den overfører data synkroniseret med et kloksignal (SCLK), hvilket giver en højere datahastighed sammenlignet med asynkrone protokoller som UART.
Komponenter i SPI

- Master: Den enhed, der styrer kommunikationsprocessen. Masteren genererer kloksignalet (SCLK) og vælger hvilke slaveenheder, der skal kommunikere med ved hjælp af Chip Select (CS) signaler.
- Slave: En eller flere enheder, der kommunikerer med masteren. Hver slave har sin egen Chip Select linje.
- SCLK (Serial Clock): Kloksignalet genereret af masteren, som synkroniserer dataoverførslen.
- MOSI (Master Out, Slave In): Linjen, hvor data overføres fra master til slave.
- MISO (Master In, Slave Out): Linjen, hvor data overføres fra slave til master.
- CS (Chip Select): Et aktivt-lavt signal, der aktiverer den ønskede slaveenhed.

### Dataoverførsel

SPI bruger fuld-dupleks kommunikation, hvilket betyder, at data kan sendes og modtages samtidig. Data overføres bit for bit i takt med kloksignalets overgange (enten stigende eller faldende kant, afhængigt af konfigurationen).
Fordele ved SPI

- Høj hastighed: SPI kan operere ved meget høje klokfrekvenser, hvilket muliggør hurtig dataoverførsel.
- Simpel og effektiv: Med få ledninger og en simpel protokol er SPI let at implementere og fejlsøge.
- Fuld-dupleks kommunikation: Mulighed for samtidig tovejs dataoverførsel øger effektiviteten.

Ulemper ved SPI

- Flere ledninger: SPI kræver flere ledninger sammenlignet med andre serielle protokoller som I2C. For hver slaveenhed kræves en ekstra CS-linje.
- Ingen standardiseret håndtering af flere mastere: SPI er designet til en enkelt master og flere slaver. At have flere mastere kræver ekstra hardware og kompleksitet.
- Ingen indbygget flowkontrol: SPI har ikke indbygget flowkontrol, hvilket kan kræve ekstra logik for at håndtere dataflowet korrekt.

Typiske Anvendelser

- Sensorinterfacing: Tilslutning af sensorer som temperaturmåler, tryksensorer osv.
- Hukommelse: Interfacing med flashhukommelse og EEPROM.
- Skærme: Kommunikation med LCD- og OLED-skærme.
    AD/DA-konvertere: Anvendelse i analoge til digitale og digitale til analoge konvertere.

SPI er populært i applikationer, hvor hastighed og enkelhed er vigtig, og hvor de ekstra ledninger ikke er en ulempe. Protokollen anvendes bredt i indlejrede systemer og elektronik.