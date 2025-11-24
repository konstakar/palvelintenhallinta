Tein kaikki tehtävät (x, a, b, c ja d) kotona, omalla tietokoneellani sunnuntaina 24.11.2025.

x) Tiivistelmät. 

Tiivistelmä 1) Pro Git, 2ed: 1.3 Getting Started - What is Git?
- git on erilainen kuin perinteiset VCS:t, git ei talleta muutoksia tiedostokohtaisina muutoksina vaan otoksina/snapshotteina
- kun committaat gitillä, git periaatteessa ottaa kuvan kaikista tiedostoistasi sillä hetkellä ja tallettaa viitteen snapshottiin.
- jos tiedosto ei ole muuttunut, git ei tallenna sitä uudestaan vaan linkittää sen aiempaan identtiseen tiedostoon joka sillä on jo tallessa.
- suurin osa git-toiminnoista toimii paikallisesti, esim historian selaaminen tai snapshottien erojen tarkastelu onnistuu ilman nettiä
- voit myös committaa silloin kun olet offline/et ole netissä.
- git varmistaa tietojen eheyden SHA-1 hashilla ennen tallennusta
- tällä git havaitsee tiedostojen/hakemistojen muutokset tai korruptiot
- git on suunniteltu niin että melkein kaikki toiminnot lisäävät dataa, eivät poista
- commitin jälkeen tekemäsi tiedon menettäminen on vaikeaa, varsinkin jos työstät etä repositorya.
- gitin kolme tilaa: modified, staged, committed
- kolme osa-aluetta: working tree, staging area ja git directory
- git työnkulku: muokkaat tiedostoja sinun työpuussasi -> stageet ne muutokset, jotka haluat seuraavaan committiisi -> committaat, joka tallentaa snapshotin staging-alueelta git-hakemistoosi pysyvästi.

Tiivistelmä 2) git add . && git commit; git pull && git push
- git add lisää muutettuja tiedostoja staging-alueelle
- "." (piste) tarkoittaa että se lisää muutokset nykyisestä hakemistosta ja siitä alaspäin, mukaan lukien tiedostot joidenka nimet alkavat pisteellä (.), mukaan tulevat uudet tiedostot, muokatut tiedostot ja myös poistetut tiedostot.
- && suorita seuraava vain jos edellinen onnistui
- git commit luo commitin eli uuden snapshotin muutoksista paikalliseen repoon
- ; suorita seuraava, vaikka edellinen epäonnistui
- git pull = git fetch + git merge, fetch hakee etäreposta uusimman historian ja tuoreet commitit ja merge yhdistää ne paikalliseen committiin.
- git push lähettää paikalliset commit etärepoon, päivitää etähaaran, jos et ole git pullia ja etäerpossa on uusia committeja push hylätään.

Lähteet: https://www.baeldung.com/linux/difference-ampersand-semicolon (koska ; ja && kai toimivat samoin tässä), https://github.com/git-guides/git-push, https://github.com/git-guides/git-pull, https://github.com/git-guides/git-commit, https://github.com/git-guides/git-add 

Tiivistelmä 3) Varaston terokarvinen/suolax/ historia
"Commits":ista
- initial commit, jossa lisätty LICENSE ja README sitten muokattu README.md:tä
- sitten "Add hello world module to create a temporary file", eli suolax/srv/salt/hello/init.sls tiedoston muokkaus sekä README:n muokkaus
- sitten "Add Makefile to apply hello state", eli luotu uusi commit nimellä Makefile
- "Add state to install my favourite apps, currently just 'tree'", eli muokattu srv/salt/favourites/init.sls-tiedostoa ja äskeistä Makefilea.
- "Add more favourite programs, and list installed modules in top file" eli Makefilen muokkaus, srv/salt/favourites/init.sls:n muokkaus sekä srv/salt/top.sls tiesdoston luonti.
- "Clean up README.md", siistitty README:tä sekä muokattu Makefilea
- "Improve usage instructions" muokattu README:tä, lisäsi sinne linkin Saltista tiedon etsintään.

--------------

Tehtävä a)
<img width="830" height="760" alt="image" src="https://github.com/user-attachments/assets/f3f802b3-1a43-4523-8c8d-6ca56fb66e79" />

----------------

Tehtävä b)
Kloonattu.
<img width="498" height="116" alt="image" src="https://github.com/user-attachments/assets/2d03ed86-2728-4979-a74b-02004ee2024f" />
<img width="227" height="34" alt="image" src="https://github.com/user-attachments/assets/920a8c6f-9595-49ff-aa6e-3e6e1a033cdd" />
<img width="429" height="76" alt="image" src="https://github.com/user-attachments/assets/156f8c3f-8d07-485f-8b8d-0eb46ae4170e" />


Sitten 
<img width="490" height="189" alt="image" src="https://github.com/user-attachments/assets/eb06917a-a78b-4cb6-a2fe-e60bf2f1593f" />
<img width="464" height="163" alt="image" src="https://github.com/user-attachments/assets/7c82378d-aab3-48d3-9031-60cb94b1b675" />
<img width="927" height="315" alt="image" src="https://github.com/user-attachments/assets/d2e1e6df-c760-4c73-bb53-89c8b3deab94" />
Tehty.

----------

Tehtävä c)
<img width="406" height="30" alt="image" src="https://github.com/user-attachments/assets/91462a10-361a-4dc4-a5aa-5effb9503a0e" />
<img width="516" height="160" alt="image" src="https://github.com/user-attachments/assets/92d13019-8c2a-4878-affa-a6c58cf2f6a7" />
<img width="399" height="143" alt="image" src="https://github.com/user-attachments/assets/4db35e83-7b18-4d9b-8d78-31f5adc945f7" />

-----------

Tehtävä d)
<img width="400" height="193" alt="image" src="https://github.com/user-attachments/assets/223b5a3d-7f1c-434a-9443-43fc376d08a6" />
Nimi ja sähköpostiosoite ovat oikealla tavalla, ei tarvitse korjata. Lokissa ei ole mitään väärin sillä nimeni ja sähköpostini näkyvät, niin näkyy myös commitin ID, päivämäärä ja commitin viesti, joka on vain tuo "Lisää esimerkki.txt", jolla lisäsin esimerkki.txt:n githubiini.

-------------------

Tehtävä e)

