x) Tiivistelmät. 
**Tiivistelmä 1. Two Machine Virtual Network With Debian 11 Bullseye and Vagrant**
- installaa vagrant, luo uusi directory projektille ja tallenna vagrantfile sinne
- vagrantilla voi ssh loginaa hostiin ja poistua takaisin omaan host-käyttöjärjestelmään. molemmat hostit voivat yhdistyä toisiinsa ja internetiin.
- helposti voi tuhota virtuaalikoneet "vagrant destroy" ja aloittaa uudet "vagrant up"

**Tiivistelmä 2.  Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux**
- lataa master ja lataa slave
- vaihda asetukset (anna sille nimi eli id)
- hyväksy slave key masterilla
- kokeile sen toimivuus komennoilla.

**Tiivistelmä 3. Salt Vagrant - automatically provision one master and two slaves: Infra as Code - Your wishes as a text file + top.sls - What Slave Runs What States**
- kirjoitetaan tekstissä oleva sisältö init.sls:ään.
- sisennys on tärkeä, kaksi välilyöntiä, ei tabia.
- top.sls-tiedosto päättää mitä tiloja ajetaan milläkin slaveilla
- kun top.sls on määritelty, "sudo salt '*' state.apply" on riittävä komento, ilman erillistä state-nimeä.


Tehtävä a).


Tehtävä b).

Tehtävä c).

Tehtävä d).

Tehtävä e).

Lähteet:

