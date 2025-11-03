x) **Tiivistelmät.**
  Tein kaikki tehtävät (x, a, b, c ja d) kotona, omalla tietokoneellani sunnuntaina 3.11.2025.


  **Tiivistelmä 1. Hello Salt Infra-as-Code **
- lataa salt ja micro editori
- luo kansio "hello" moduulille
- kirjoita infraa koodina, aja koodi ja tarkista, että salt teki mitä sen piti


  **Tiivistelmä 2. Salt contributors: Salt overview
  Rules of YAML**
- YAML esittää datan "key: value"-pareina
- kuvauksessa on kaksoispiste ja väli (": ") merkkaamassa "key: value" pareja
- kaikki keyt ja ominaisuudet ovat merkkikokoriippuvaisia = eli isoilla kirjaimilla on väliä
- tabulattorin käyttö ei ole sallittu, vain tavalliset välilyönnit


  **YAML simple structure**
- kolme peruselementtityyppiä.
- Scalars = key: value kuvaukset, joissa arvo voi olla numero, numeroarvo tai totuusarvo.
- Lists = key: value, jota seuraa arvolista (jokaista arvo on omalla rivillään ja niitä edeltää kaksi välilyöntiä ja viiva (-))
- Dictionaries = kokoelma key: value kuvauksia ja listoja.


  **Lists and dictionaries - YAML block structures**
- YAML on järkestetty lohkorakenteisiin
- sisennys määrittää kontekstin ja rakenteen, listat/ominaisuudet täytyy sisentää vähintään yhdellä väliyönnillä, kaksi välilyöntiä on standardi
- kokoelmat ilmaistaan "- " (viiva, välilyönti)


  **Salt contributors: The top file**
  **Introduction**
- useimmat infrastruktuurit koostuvat ryhmistä koneita. kaikilla koneilla on samankaltaisia rooleja (toistensa kanssa)
- nämä koneista kokoontuvat ryhmät työskentelevät yhdessä luodakseen application stackin (sovelluspinon)
- järjestelmänvalvoja määrittelee roolit koneiden ryhmille
- saltin tiedosto, joka määrittää koneiden ryhmien ja roolien yhteyden on top file
- top file = top.sls, sijaitsee "state tree":n yläosassa


  **A Basic Example**
- Top file sisältää kolme komponenttia
- environment = state tree-hakemisto, jossa on tilatiedostoja (state files)
- target = koneiden ryhmä, joihin tilat sovelletaan
- state files = ne määrittelevät mitä valvotaan ja konfiguroidaan.
- environmentit sisältää targetteja, targetit sisältää state fileja.

  
Tehtävä a) 
Kokeilin koodia "Hello Salt Infra-as-Code" ohjeiden mukaan. sudo mkdir -p /srv/salt/hello/ -> cd /srv/salt/hello/ -> sudoedit init.sls
-> /tmp/hello_infrakoodi   file.managed ->  sudo salt-call --local state.apply hello =

<img width="555" height="366" alt="image" src="https://github.com/user-attachments/assets/bdc5d524-e625-4d9a-8c3d-754801f2d9c3" />

Tehtävä b) 
Yritin tehdä, mutta mulla ei edes ollut muita .sls tilatiedostoja joita ajaa? <img width="570" height="97" alt="image" src="https://github.com/user-attachments/assets/4bd07b13-608b-47d8-bd1d-84b4c91c64ff" />
Joten en oikein hahmota mitä tässä pitäisi ajaa.


Tehtävä c) 
Tein erilliset esimerkit viidestä mainitusta tilafunktiosta. (package, file, service, user, cmd) <img width="672" height="172" alt="image" src="https://github.com/user-attachments/assets/0631ef47-b50c-481c-98c8-ca7324934a2b" />
Tein niihin kaikkiin init.sls, esim. pkg = install_htop -> pkg.installed -> - name: htop eli se asentaa paketin htop ja service = ensure_sshd_running: -> service.running: -> - name: ssh -> - enable: True. Testitulokset:
<img width="985" height="277" alt="image" src="https://github.com/user-attachments/assets/524709b0-62e2-46ff-8fd9-3ad6c8c171b8" />
<img width="412" height="141" alt="image" src="https://github.com/user-attachments/assets/779dde5f-7159-492a-bb5c-93515c63edea" />


Oikeat tulokset: <img width="277" height="83" alt="image" src="https://github.com/user-attachments/assets/2b694c25-b4aa-4149-920a-481c9fbb4b08" />
Fail oli se, ettei minulla ollut SSH ladattuna (vaikka mielestäni latasin sen kyllä jo aiemmin, mutta kuitenkin) Latasin sen, ja ajoin uudestaan ja se toimi. <img width="272" height="47" alt="image" src="https://github.com/user-attachments/assets/55bfa43f-e346-4192-8e16-f95bae78ef78" />

  
Tehtävä d) 
Loin sls:än, joka asensi paketin (package) ja loi tiedoston. sudo mkdir -p /srv/salt/testitiedosto -> sudo nano /srv/salt/testitiedosto/init.sls -> <img width="271" height="139" alt="image" src="https://github.com/user-attachments/assets/6ce3f2c5-a1cb-4454-842f-d6ba0ab27444" /> 
-> tämän jälkeen sudo salt-call --local state.apply -> <img width="825" height="439" alt="image" src="https://github.com/user-attachments/assets/ad2622cf-f645-43cd-872d-aeaafd0b5cc2" /> 
Ajoin saman komennon uudestaan ja tulos oli sama, eli mitään ei muuttunut = 
<img width="286" height="102" alt="image" src="https://github.com/user-attachments/assets/6866ad5a-d5d7-4783-a024-0d12edbbedf2" /> (changed=1 taitaa olla minun tekemäni echo-komento hellocmd-tiedoston sisällä. 
<img width="690" height="304" alt="image" src="https://github.com/user-attachments/assets/aa36b5a2-87e1-4f13-8950-ba8c73d1f59f" /> Tarkistin tiedoston tavallisella tiedostokomennolla myös. <img width="509" height="21" alt="image" src="https://github.com/user-attachments/assets/3edb7569-c609-4f44-88c4-36a268f72b64" />

Tehtävien tekemiseen meni n. 2 tuntia.

Lähteet:
Karvinen, Tero 2024: Hello Salt Infra-as-Code. https://terokarvinen.com/2024/hello-salt-infra-as-code/ 
Salt contributors: Salt overview https://docs.saltproject.io/salt/user-guide/en/latest/topics/overview.html#rules-of-yaml
Salt contributors: The Top File https://docs.saltproject.io/en/latest/ref/states/top.html
ChatGPT: prompt millä eri ohjelmalla tarkistan että lopputulos on oikea (en tajunnut että tarkoitettiin built-in komentoja, ei salt komentoja), kysyin minkä packagen lataan kun htop oli jo käytetty. 
