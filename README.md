# NF5AA4.UFW (Firewall equip Linux)

## Presentació de l'activitat

Els tallafocs són una eina essencial per a la seguretat de les xarxes i malgrat el que es pugui pensar, no n'hi ha prou amb tenir un tallafocs que protegeixi la xarxa (firewall perimetral), sinó que també és necessari tenir un tallafocs en cada equip de la xarxa, en especial equips crítics com servidors.

En el món Linux, la feina de tallafocs l'exerceix `iptables`, però la seva sintaxi és complexa i difícil d'aprendre. Per això, s'ha creat una eina que simplifica la gestió del tallafocs: `ufw` (Uncomplicated Firewall).

### Durada de l'activitat

Durada prevista: 2 hores.

### Objectius de l'activitat

Configurar un tallafocs en un equip Linux amb l'eina `ufw` per a protegir-lo de possibles atacs externs i interns.

### Competències treballades

c) Instal·lar i configurar programari bàsic i d’aplicació, assegurant-ne el funcionament en condicions de qualitat i seguretat.

e) Instal·lar i configurar xarxes locals cablejades, sense fil o mixtes, i la seva connexió a xarxes públiques, assegurant-ne el funcionament en condicions de qualitat i seguretat.

p) Aplicar els protocols i normes de seguretat, qualitat i respecte al medi ambient en les intervencions realitzades.

### Resultats d'aprenentatge i criteris d'avaluació

RA4. Assegura la privadesa de la informació transmesa en xarxes informàtiques descrivint vulnerabilitats i instal·lant programari específic.

4.8 Instal·la i configura un tallafocs en un equip o servidor.

### Continguts

4.6 Tallafocs en equips i servidors.

### Capacitats clau

|             |                         |                    |
|------       |---------                |----------          |
|Autonomia    |Organització del treball |~~Treball en equip~~|
|~~Innovació~~|Resolució de problemes   |Responsabilitat     |
|             |~~Relació interpersonal~~|                    |

## Enunciat de l'activitat

### Entorn de treball

#### Servidor a protegir

Un equip Linux amb accés a Internet i privilegis d'administrador, pot ser un Ubuntu Server o un equip Desktop com Zorin, en aquest cas, es pot instal·lar l'eina gràfica `gufw` per a la gestió del firewall.

L'equip ha de tenir dues interfícies de xarxa:

- NAT per tenir accés a Internet.
- Host-Only per fer les proves de connexió des de l'equip físic.

A la màquina Linux cal instal·lar els següents serveis:

- Servidor SSH.
- Servidor nginx:
  - Editeu el codi html de la pàgina per defecteperquè aparegui el vostre nom i la data de l'activitat.
  - Comprovar que funciona la connexió via http (port 80).
  - Habilitar el lloc per defecte pel port 443 amb certificat autofirmat (comprovar que funciona la connexió via https).

#### Client per fer proves de connexió

Un segon equip, pot ser Windows o Linux, amb accés a Internet i a la xarxa Host-Only de la màquina Linux. Aquest equip s'utilitzarà per fer les proves de connexió amb el servidor Linux.

### Instruccions de l'activitat

1. Comprova l’estat del firewall i si cal habilita’l.
2. Mostra les regles que té definides. Quines són les regles per defecte?
3. Comprova la regla per defecte de `deny` pel trànsit d’entrada. Connectat des l’amfitrió a aquest equip via SSH i observa si et pots connectar.
4. Aplica regla per defecte `deny` al trànsit de sortida. Prova a fer un ping a Google.
5. Aplica regla per defecte `allow` al trànsit de sortida. Torna a provar a fer un ping a Google.
6. Crear una regla per prohibir qualsevol tipus de trànsit cap al domini "capgros.elnacional.cat. Comprova’l fent un ping o amb un navegador web.
7. Habilita el trànsit d’entrada pel servei SSH per la IP de l’amfitrió (192.168.56.1) comprova que connecta correctament, però que el segon equip virtual no es pot connectar.
8. Permet les connexions entrants al servidor nginx sense restricció. Comprova-ho tant des de l'equip físic, com des del segon equip virtual. Comprova que pots connectar tant pel port 80 com pel port 443.
9. Crea les regles necessàries per prohibir les connexions de sortida pel protocol FTP amb l'excepció del servidor de Rediris (ftp.rediris.es). Comprova que no pots connectar a cap altre servidor FTP però sí al servidor indicat.
10. Mostra el conjunt de regles definides.

### Documentació i Informe Final

Documenta les diferents activitats amb captures de pantalla i explicacions dels resultats obtinguts.

## Enllaços d'interès

- [Wili Ubuntu - UFW](https://wiki.ubuntu.com/UncomplicatedFirewall)

- [nixCraft - Ubuntu 22.04 Set Up UFW Firewall in 5 Minutes. nixCraft](https://www.cyberciti.biz/faq/ubuntu-22-04-lts-set-up-ufw-firewall-in-5-minutes/)

- [ServerSpace - UFW básico (sin complicaciones) Firewall) comandos](https://serverspace.io/es/support/help/osnovnye-komandy-ufw/)
