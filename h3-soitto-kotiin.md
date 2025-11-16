Aloitin tekemään 6-8.11, mutta jäi kesken ja viimeistelin 16.11.

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

<img width="329" height="44" alt="image" src="https://github.com/user-attachments/assets/7134121e-b027-4258-9040-ba5fb482a7be" />

------

Tehtävä b). 

Pistin lähteessä annetun koodin Vagrantfileen ja käytin vinkeissa annettuja komentoja.

<img width="598" height="123" alt="image" src="https://github.com/user-attachments/assets/256ec63a-e46b-4d54-b500-3cafc2624153" />
<img width="906" height="100" alt="image" src="https://github.com/user-attachments/assets/fe061a00-9869-4b76-8f3b-dca6173ef985" />
<img width="814" height="192" alt="image" src="https://github.com/user-attachments/assets/3682d493-96e3-442b-909c-15a4bfef3377" />
<img width="662" height="141" alt="image" src="https://github.com/user-attachments/assets/e8bc02bb-7a33-4ca0-ae95-19e723ce0456" />

------
Tehtävä c).


Pistin lähteessä annetun koodin Vagrantfileen ja käytin komentoja

<img width="420" height="45" alt="image" src="https://github.com/user-attachments/assets/c2015e9c-d3c2-4666-b79d-cf5a8a09ff1f" />
<img width="519" height="122" alt="image" src="https://github.com/user-attachments/assets/7540b337-1554-4814-a0e5-f66da01e61b8" />
<img width="668" height="55" alt="image" src="https://github.com/user-attachments/assets/0cdbc95a-703f-4697-9c4a-36617ddbfa41" />
<img width="687" height="230" alt="image" src="https://github.com/user-attachments/assets/6b9b2ba6-46e9-4de1-9a31-7398eafd4826" />

-----
Voivat pingata toisiaan.
<img width="557" height="139" alt="image" src="https://github.com/user-attachments/assets/9c1abdca-f45c-4fc7-ae2c-a38ef00cc3b5" />

<img width="552" height="131" alt="image" src="https://github.com/user-attachments/assets/f7521473-d216-4c90-95b0-58bbe9979a3c" />

----


Tehtävä d).
<img width="462" height="611" alt="image" src="https://github.com/user-attachments/assets/e36a7b21-59e4-4d64-89d7-b6ad9fd073b0" />
<img width="410" height="21" alt="image" src="https://github.com/user-attachments/assets/f5b75f9d-1012-4e0e-9db4-530771513706" /> 
<img width="455" height="20" alt="image" src="https://github.com/user-attachments/assets/62c0f109-ddd5-44f8-ad60-ca5e1b4d7af2" />


<img width="571" height="135" alt="image" src="https://github.com/user-attachments/assets/42851385-3d3f-4f64-9412-45bd8d15fd80" /> ja sama toisin päin. <img width="565" height="133" alt="image" src="https://github.com/user-attachments/assets/4b8346a8-50eb-471a-867b-b85fa1069421" />


Yhdistämistä varten piti muuttaa nanolla t002:sen "/etc/salt/minion" tiedostosta "#master: salt" saltin tilalle t001:sen ip.<img width="738" height="373" alt="image" src="https://github.com/user-attachments/assets/4fd326e2-47f6-425c-ab13-008b7a81aff0" /> sitten restart. <img width="464" height="24" alt="image" src="https://github.com/user-attachments/assets/ea994aa2-4d31-4546-8ae6-196608223c28" />
takasin t001:sessä, minionin key näkyy. <img width="434" height="135" alt="image" src="https://github.com/user-attachments/assets/725c0510-fa68-4955-bf2b-8715a4b29bee" />
<img width="393" height="79" alt="image" src="https://github.com/user-attachments/assets/8a77a67e-fc3f-4055-a32d-c2fe77342e72" />

-----

Tehtävä e).

Eka luodaan salt state hakemisto masterille.<img width="372" height="58" alt="image" src="https://github.com/user-attachments/assets/241795b2-6a48-4e70-98d7-1e72a71de5df" />
Hakemistoon tiedosto (minulla testaus.sls), johon laitan kaksi tilaa (pkg ja service). <img width="218" height="189" alt="image" src="https://github.com/user-attachments/assets/ce35c4be-f81c-427b-a6e6-f354844d181b" />
<img width="571" height="75" alt="image" src="https://github.com/user-attachments/assets/7d380ecc-b650-4858-98e1-e474feb1b18d" /> <img width="491" height="303" alt="image" src="https://github.com/user-attachments/assets/128fdd0b-235b-4017-ab26-55549d51d37d" />

-----

Tehtävien tekemiseen meni yhteensä n. pari tuntia taas.

Lähteet: Karvinen, Tero 2021: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant. https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/ Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/?fromSearch=salt%20quickstart%20salt%20stack%20master%20and%20slave%20on%20ubuntu%20linux Karvinen 2023: Salt Vagrant - automatically provision one master and two slaves https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file ChatGPT: kysyin esimerkkejä mitä tiloja laittaa sls-tiedostoon.

