# DOCUMENTACIÓ MAT PROJECT

## 1. API SHODAN

Per començar, ens vam registrar a la plataforma *https://developer.shodan.io/* que la qual ens proporciona un TOKEN. Aquest TOKEN ens ha sigut útil a l'hora de fer les consultes a les BBDD de SHODAN (ens ha permès l'accés).

Hem filtrat els paràmetres que hem cregut adients, com per exemple: domini, port i IP (associada al domini)

## 2. HARVESTER

Aquest eina és capaç de recopilar correus electrònics, noms, subdominis, IP i URL de múltiples fonts de dades públiques que inclouen, com per exemple:

**Shodan**: cercarà ports i bàners dels amfitrions descoberts
**pentesttools**:potents eines de prova de penetració.
**Twitter**:comptes de Twitter relacionats amb un domini concret.
**Rapiddns**: eina de consulta de DNS que facilita la consulta de subdominis o llocs d'una mateixa IP.
**Censys**:utilitzarà cerques de certificats per enumerar subdominis i recopilar correus electrònics


## 3. OSINT
**Que és**
És intel·ligència recopilada a partir de fonts disponibles públicament com Internet, mitjans de comunicació massius, xarxes socials, revistes de recerca i eines d’investigació del govern estatal o nacional

### 3.1 Holehe

Eina per buscar emails registrats en pàgines web, aquestes pàgines web estan en una base de dades que incorpora l'eina.
Es passa per paràmetre un email demanat per teclat y la crida es fa per **subprocés**.

### 3.2 Ghunt

Eina amb moltes tècniques per investigar comptes de Google, o objectes, dispossa el següents mòduls de correu electrònic, documents, tutube i gaia.
Utilitzarem cookies de la sessió actual del compte de Google. És passarà per paràmetres un mòdul amb el tipus de paràmetre empleat prèviament ja sigui document, email, etc.
En aquest cas pasem per **input** un correu.

### 3.3 Udork 

Pareguda al Ghunt utilitza cookies per poder utilitzar-la en aquest cas utilitza les de Messenger (Facebook). És passa per paràmetre un domini i a continuació les opcions que necessites, abans demanar aquesta opció es llisten aquestes. Aquestes entrades es demanen per **input** i finalitza amb un **subprocés**.

### 3.4 Wafwoof

Eina per detectar WAF, aquesta eina envia una sol·licitud HTTP al firewall de l'aplicació web per a identificar-ho. Quan falla l'enviament de sol·licituds HTTP, wafw00f realitza una sol·licitud HTTP maliciosa. Si falla una sol·licitud HTTP maliciosa, wafw00f examina les sol·licituds HTTP anteriors i empra un algorisme simple per a determinar si l'aplicació web tallafocs reacciona als nostres atacs.

Utilitza'm una ruta URL que la demanem per un **input** i un **subprocés** que crida a aquesta eina mes els paràmetres introduïts per el input. 

### 3.5 Mosint

Conjunt d'eines osint, aquesta eina a part dels requeriments que instal·lem també necessitem utilitzar l'eina golang. Utilitza'm un **subprocés** amb un email demanat per **input**.
Sols hem implementat l'opció de buscar tot.

## 4. ESCANEGI NAMP

Importació d'eines necessàries com el mòdul nmap i pyfiglet.

### 4.1 DESCOBRIR ELS HOSTS DE LA XARXA
En aquesta funció, hem implementat la cerca dels hosts de la xarxa amb les funcions **nmap.PortScanner()**, passant com a paràmetres el **host**. Això ens permet que el nmap faci una cerca exhaustiva dels hosts que es troben a al xarxa i el seus **status**(gràcies als mòdul **nmap** de **python**).

### 4.2 LLISTAR PROTOCOL I PORTS

El resultat de la cerca anterior, ens permet que **nmap** ens proporcioni un llistat de ports oberts segons el hosts que li passi com a paràmetre. Com ja sabem, tenim ports directament relacionats al servei que escolten, per tant, el mòdul de l'nmap s'encarregarà de la cerca d'aquests ports, proporcionant-nos aquest juntament amb l'estat del port i els protocols que utilitza (**nm[host].all_protocols():**).

### 4.3 LLISTAR VULNERABILITATS D'UN RANG

* Acabar d'implementar

## 5. Auditoria SSH
**Que és**
SSH-Audit és una eina CLI de codi obert escrita en Python que us permet verificar fàcilment a 
través de diferents pautes, vulnerabilitats en el seu protocol SSH del servidor de destinació

**Que fa ssh-audit**
1. Mostra la versió del protocol i del programari que estem usant.
2. Busca els algorismes dintercanvi de claus.
3. Busca els algorismes del host.
4. Busca els algorismes de xifratge.
5. Busca els algorismes d'autenticació de missatges (hash).
6. Busca recomanacions sobre la manera de procedir amb certs algorismes.

## 6. Enumeració
**Dependències necessàries**
S'ha de tenir el paquet Samba instal·lat, ja que aquest script és bàsicament només un embolcall al voltant de rpcclient, net, nmblookup i smbclient.
**Funcionament**
És una eina per a enumeració d'informació del sistema operatiu Windows i el Protocol Samba. Està escrit en llenguatge Perl i és bàsicament un contenidor de les eines, 
Samba smbclient, rpclient, net i nmbloookup


## 7. Enviar informe

Utilitza'm un bot de Telegram, aquest script compta amb una funció que ens permet enviar fitxers gràcies a l'api del Telegram. Es necessita tant **bot_token** com **bot_chatID** aquesta la proporciona el bot.
Per últim es posa la ruta de l'arxiu a enviar. Per poder guardar aquest informe el que femes utilitzar tant el paràmetre open per poder obrir un fitxer i escriure **variable=open('nomdelfitxert','w')** i la cridem al subprocés on volem que guardi el fitxer amb **stdout=f**. Sol se ha aplicat a uns scritps.


 

