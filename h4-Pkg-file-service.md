Tehty sunnuntaina 16.11.
x) Tiivistelmä: Pkg-File-Service – Control Daemons with Salt – Change SSH Server Port
- saltilla voit hallita ison määrän palveluprosesseja herra-orja-arkkitehtuurissa 
- SSH-palvelun portin vaihtaminen voidaan tehdä muokkaamalla sshd_config-tiedostoa Saltin file.managed -tilalla. 
- Muutokset aktivoidaan service.running -tilalla, jolloin SSH-palvelu uudelleenkäynnistyy automaattisesti.
- aseta tila orjille / minioneille (state.apply)
- testaa että se toimii

------

Tehtävä a)
Aloitan käsin sillä, että uusi portti SSHd:een "sudoedit /etc/ssh/sshd_config" ja lisään port 1234 <img width="200" height="348" alt="image" src="https://github.com/user-attachments/assets/047f838d-2646-4d09-a173-42fffd0f62e6" />

Sitten uudelleenkäynnistys -> sudo systemctl restart ssh ja seuraavaksi uuden portin testaus <img width="389" height="58" alt="image" src="https://github.com/user-attachments/assets/97ec806c-6b96-4cdb-b21f-333670759074" />

<img width="735" height="116" alt="image" src="https://github.com/user-attachments/assets/86ad251d-8278-4613-b642-715e9d5ee6db" />


Sitten html-tiedosto <img width="568" height="39" alt="image" src="https://github.com/user-attachments/assets/05f71795-f3e3-4638-9f95-6f5996cb8128" />


------

Sen jälkeen poistin käsin tekemäni muutokset, esim. "sudo nano /etc/ssh/sshd_config" -> sieltä pois "Port 1234". <img width="469" height="44" alt="image" src="https://github.com/user-attachments/assets/7371ac81-51ec-4857-a8de-067c43aed241" />

<img width="497" height="43" alt="image" src="https://github.com/user-attachments/assets/ff975f79-42ee-424a-b4c7-48042254c7a7" />


------

Tässä tiedosto /srv/salt/ssh/init.sls. <img width="328" height="419" alt="image" src="https://github.com/user-attachments/assets/69cefaeb-1204-4a68-a842-d443428d5c1a" /> ja tiedosto /srv/salt/ssh/sshd_config <img width="158" height="356" alt="image" src="https://github.com/user-attachments/assets/c76329b6-f3a6-4e0e-a867-d4bbedad1573" />



<img width="524" height="58" alt="image" src="https://github.com/user-attachments/assets/26608d0e-2550-47d1-a1df-518caf9888c3" />
<img width="317" height="380" alt="image" src="https://github.com/user-attachments/assets/91d16865-24eb-416f-888f-c92ee997e680" /> 

Lisäsin vielä tuonne sshd_configiin. "PermitRootLogin" ja "PasswordAuthentication" <img width="278" height="379" alt="image" src="https://github.com/user-attachments/assets/88f1fe9c-ad58-449f-b4db-dbad657d565b" />


 Lopuksi: <img width="354" height="34" alt="image" src="https://github.com/user-attachments/assets/15920305-2c14-456d-8ff9-428853c954cd" /> 

 ------

Aikaa meni hieman yli 2 tuntia.

Lähteet: Karvinen, Tero 2018. Pkg-File-Service – Control Daemons with Salt – Change SSH Server Port https://terokarvinen.com/2018/04/03/pkg-file-service-control-daemons-with-salt-change-ssh-server-port/?fromSearch=karvinen%20salt%20ssh, Chatgpt:ltä mitä laittaa init.sls:ään
