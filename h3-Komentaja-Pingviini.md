# h3 Komentaja Pingviini

## Komentorivin perusteet
Teksti on tiivistetty Tero Karvisen 2020 artikkelista Command Line Basics Revisited

Linuxissa käytetty komentorivi on kätevä, nopea, ilmaisuvoimainen ja helposti automatisoitava.


## Muutamia komentoja kategorioittain
### Liikkuminen ja katselu
Komentorivia käytettäessä ollaan aina jossain kansiossa. Tämänhetkistä kansiota kutsutaan työskentelykansioksi (working directory).
- `$ pwd` - Tulosta töskentelykansio.
- `$ ls` - Listaa kansion tiedostot.
- `$ cd` - Liiku kansiosta, esim. `$ cd ../esimerkki` liikkuakseen yhtä ylemmässä kansiossa sijaitsevaan esimerkki nimiseen kansioon.
- `$ less` - Näyttää tekstin ruudun kokoisina palasina "less-avaruudessa" omilla navigaatiotyökaluillaan. Minkä vain tulosteen voi putkittaa lessiin 
### Tiedostojen muokkaus
- `$ nano FOO.TXT` - Avaa FOO.TXT tiedoston nano tekstinkäsittelyohjelmalla, tai jos tiedostoa ei ole, avaa nano editorin uudelle tiedostolle ja tallentamisen yhteydessä FOO.TXT luodaan.
- `$ mkdir` - Luo kansio.
- `$ mv` - Liikuta tai uudelleen nimeä tiedosto.
- `$ cp` - Kopioi tiedosto tai `$ cp -r` kopioi kansio sisältöineen.
- `$ rmdir` - Tuhoa tyhjä kansio.
- `$ rm` - Tuhoa tiedosto tai `$ rm -r` tuhoa kansio sisältöineen.
### SSH Etäyhteys
Terminaalista voi ottaa Secure Shellillä etäyhteydän toiseen koneen terminaaliin.
- `$ ssh tero@example.com` - Avaa etäyhteyden ja terminaalin kohdekoneeseen.
- `remotemachine$ exit` - Poistuu terminaalista.
- `$ $ scp -r FOLDER tero@example.com:public_html/` - Turvallisesti kopioi kansion omalta koneelta etäkoneelle. SCP ajetaan omalta koneelta, eli etäyhteys on suljettava ensin.
### Apu
Ohjeita ohjelmien käytöstä voi lukea niiden manuaalisivulta tai moniin ohjelmiin sisältyväv, usein suppeamma, apusivun kautta.
- `$ man` - Avaa manuaalisivun, esim - `$ man ls` ls:n manuaalille.
- `$ ls --help` Avaa komentoon sisältyvän helpin.
### Historia ja Arvailu
Tabillä voi automaattisesti viimeistellä aloitetun komennon ja kahdesti painamalla saa listan saatavilla olevista komennoista (sekä vavhistusruudun jos tuplatabin painaminen ei välttämättä ollut kyseisessä tilanteessa mielekästä). 

![Are you sure?](h2_x1_TabTab.png)
### Tärkeät Kansiot
Kaikkien Linuxien kansirakenteet ovat Filesystem Hierarchy Standardard mukaisia, eli kansiorakenne on sama distrosta riippumatta.
- `/` - Juurihakemisto hakemistorakenteen huipulla. Kaikki muu on tämän alla.
- `/home/` - Sisältää kaikkien käyttäjien kotihakemistot.
- `/home/tero/` - Sisältää tero nimisen käyttäjän kotihakemiston ja on ainoa paikka, jonne tero voi pysyvästi tallentaa dataa.
- `/etc/` - Sisältää kaikki järjestelmän laaljuiset asetukset.
- `/media/` - Sisältää irrotettavan median kuten usb-tikut ja levy-mediat.
- `/var/log/` - Sisältää järjestelmän laajuiset logit.
### Hallinnolliset Komennot
Pienimmän käyttäjäoikeuden periaate (eng. minimum privilege principle) sanoo, että operaatiot suoritetaan alimman mahdollisen tason käyttäjäoikeuksilla. Täten ainoastaan operaatiot, jotka tarvitsevat laajoja käyttäjäoikeuksia tulee suorittaa 'sudo':na, jolloin ne saavat rajattomat oikeudet.
Tälläisiä ovat koko järjestelmään vaikuttavat operaatiot, kuten ohjelmien asennus ja poisto sekä käyttäjien luonto ja käyttäjäoikeuksien hallinnointi.
Siispä `$ sudo apt-get update`, joka päivittää listan saatavilla olevista pakeista tarvitsee sudo (super user do) oikeudet, mutta  `$ apt-cache search`, joka etsii paketteja ei tarvitse.

## Raportti
## Ympäristö
### Rauta: 
- Käyttöjärjelmä: Windows 11 Education x86-64 23H2
- Prosessori: AMD Ryzen 3900XT 3.9GHz 12-core
- RAM: 32GB
- Näytönohjain: Nvidia Geforce 3080 RTX
- Kiintolevy: Samsung 2 TB M.2 SSD
### Virtuaali:
- Virtualisointi: VirtuaBox 7.0.20
- Käyttöjärjestelmä: Debian 12 x86-64
- CPU: 4 core
- RAM: 8GB
- Kiintolevy: 200 GB

Tehtäviä suoritteassani minulla oli ajastin pyörimässä, mutta tähtävän sisällä eri osioihin käytetty aika on ainoastaan rehellinen arvioni, koska tarkempaa mittausta en tehnyt.

## a) Micro. Asenna micro-editori.
Käytetty aika: 12 minuuttia. ~5 minuuttia tehtävään ja ~7 minuuttia raporttiin sekä kuvakaappauksiin.

Ajoin `sudo apt-get update` ja `sudo apt-get install micro` komennot. Hyväksyin xclipin asennuksen, josta promptattiin ennen asennuksen alkua.
Katsoin micron kuvauksen `man micro` komennolla ja loin kokeeksi tekstitiedoston. Tämän jälkeen selvitin micron näppäinyhdistelmät painamalla `Alt-g`, jonka jälkeen tallensin tiedoston ja poistun microsta.

![micro manual](h2_a1_micro.png)
![Testing](h2_a2_testing.png)

## b) Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. Kokeile kutakin ohjelmaa sen pääasiallisessa käyttötarkoituksessa. Ota ruutukaappaus. Kaikki terminaaliohjelmat kelpaavat, TUI (text user interface) ja CLI (command line interface). Osaatko tehdä apt-get komennon, joka asentaa nämä kolme ohjelmaa kerralla?
Käytetty aika: 34 minuuttia. ~10 minuuttia tiedonhakuun Linux CLI ohjelmista, ~15 minuuttia tehtävään, ~9 minuuttia kuvakaappauksiin ja raporttiin.

Päädyin ohjelmiin Wget, lshw ja tldr. Wget ja lshw tulivat vastaan viikon materiaalissa ja tldr:en löysin googlettamalla Linuxiin suositeltuja CLI ohjelmia.

Wget on ei-interaktiivinen ohjelma tiedostojen lataamiseen netistä, lshw on työkalu koneen rauta-informaation selvittämiseen ja tldr (too long; didn't read) on yhteysövoimin ylläpidetty ohjelma, joka tarjoaa lyhennetyt ja `man` komentoa helpommin luettavat manuaalisivut eri ohjelmille.

Varmistin kaikkien löytymisen `apt-cache search` komennoilla. Ajoin `sudo apt-get install wget lshw tldr` ja hyväksyin tarvittavien riippuvuuksien asennuksen promptatessa.

Ensiksi ajoin `tldr tldr` komennon, joka ensin haki tldr manuaalitiedostot (`tldr --update` olisi tehnyt saman) ja sen jälkeen näytti tldr:n tldr sivun.
Seuraavaksi hain Wgetin tldr sivun ohjeeksi ohjelman käytöstä.

![Wget TLDR](h2_b1_tldr.png)

Wgetin tldr ohjeita noudattaen latasin erään ensimmäisen viikon läksyjen kuvista, joka toisella yrityksellä onnistui kun sain kirjoitettua komennon oikein.

![Wget download](h2_b2_wget.png)

Katsoin lshw:n tldr sivun `tldr lshw` komennolla ja nappasin sieltä komennon `sudo lshw -short` koneen raudan listaukseen.

![lshw](h2_b3_lshw.png)

## c) c) FHS. Esittele kansiot, jotka on listattu "Command Line Basics Revisited" kappaleessa "Important directories". Näytä kuvaava esimerkki kunkin tärkeän kansion sisältämästä tiedostosta tai kansiosta. Jos kyseessä on tiedosto, näytä siitä kuvaava esimerkkirivi. Työskentele komentokehotteessa ja näytä komennot, joilla etsit esimerkit.
Käytetty aika: 23 minuuttia. ~10 minuuttia tehtävään, ~13 minuuttia kuvakaappauksiin ja raporttiin.
Juurikansio (/) on järjestelmän ylin kansio, jonka alta kaikki muut löytyvät.

![Root](h2_c1_root.png)

Home (/home/) kansio sisältää kaikkien käyttäjien kotikansiot.

![Home](h2_c2_home.png)

Janne (/home/janne/) kansi on janne nimisen käyttäjän kotikansio.

![Janne](h2_c3_janne.png)

Etc (/etc/) sisältää järjestelmänlaajuiset asetukset.

![Etc](h2_c4_etc.png)

Media (/media/) sisältää irtomedian. Tällä hetkellä virtuaaliseen cd asemaan mountattu asennuslevy virtual box Guest Additionsille.

![Media](h2_c5_media.png)

Log (/vafr/log/) sisältää järjestelmänlaajuiset logitiedostot.

![Log](h2_c6_log.png)
![Logs explained](h2_c6.1_log_explained.png)


## d) The Friendly M. Näytä 2-3 kuvaavaa esimerkkiä grep-komennon käytöstä. Ohjeita löytyy 'man grep' ja tietysti verkosta.
Käytetty aika: 31 minuuttia. ~15 minuuttia tiedon hakuun ja manuaalisivujen tutkimiseen, ~10 tehtävän suorittamiseen, ~6 raporttiin ja kuvakaappauksiin.

Ajoin ensiksi `tldr grep`(olisi todennäköisesti suositeltavaa opetella `man` käyttö kohtuullisesti ennen oikoteiden käyttöä, mutta tämä on tulevan itseni ongelma).

![tldr Grep](h2_d1_grep_tldr.png)

Navigoin /etc/ kansioon ja katsoin os-release tiedoston sisältöä `cat os-release`, jonka jälkeen kirjoitin komennon, joka hakee rivit, jotka sisältävät hakutermin "NAME". Pelkästään hakutermin sisältävien rivien tulostus vaati kaksi yritystä syntaksin saamiseksi oikein.

![Grep os-release](h2_d2_grep_os_version.png)

Putkitin grepin manuaalisivun grepin komentoon tietyn rivin etsimiseksi löytääkseni edellisen komennon kuvauksen paikan grepin manuaalista komennolla `man grep | grep -n "before-context"`.

![Grep line number](h2_d3_man_grep_line.png)

Tämän jälkeen ajoin `grep man` ja navigoin kyseiselle sivulle.

![Grep Conxtext Line Control](h2_d4_man_grep.png)

Tulostin tiedoston testing.txt sisällön komennolla `cat testing.txt`, jonka jälkeen tulostin rivejä muutamalla grepin -E (extended-regexp) komennon parametrilla.

![Grep Regex](h2_d5_grep_regex.png)

## e) Pipe. Näytä esimerkki putkista (pipes, "|").
Käytetty aika: 10 minuuttia. ~5 minuuttia tiedonhakuun putkituksen ja uudelleenohjauksen syntakstiksta, ~1 minuutti tehtävään, ~4 minuuttia kuvankaappauksiin ja raporttiin.

Loin uuden tyhjän tekstitiedoston komennolla `touch result.txt`, jonka jälkeen käytin `echo qwerty12345 you12 me they` komentoa tulostamaan parametraina annetut sanat ja putkitin tämän grepin only matching hakuun parametrille y `grep -o "y"` ja ohjasin lopputuloksen aikasemmin luotuun tekstitiedostoon `>> result.txt`.
Lopuksi vielä varmistin vain y kirjainten kopioituneen komennolla `cat result.txt`.

![Piping And Redirecting](h2_e1_piping_and_redirecting.png)

## f) Rauta. Listaa testaamasi koneen rauta (‘sudo lshw -short -sanitize’). Asenna lshw tarvittaessa. Selitä ja analysoi listaus.
Ajankäyttö: 16 minuuttia. ~11 minuuttia hakuja lshw tulosten tulkitsemista (ei lopulta vaikutusta vastaukseen, mutta totesin, että tulosten syvempi tulktiseminen ei ole triviaalia, erityisesti jos ei tiedä täsmälleen mitä hakea), ~2 minuuttia tehtävään, ~3 minuuttia kuvakaappauksiin ja raporttiin.

Uudelleenohjasin annetun komennon tulosteen tiedostoon hardware.txt ja tulostin sen terminaalin catillä.

![Hardware](h2_f1_hardware.png)

Osasta laitteista, kuten prosessori, näki virtuaalinen Linux alle pyörivän raudan mallin, mutta valtaosa näkyi virtualboxin tarjoamina virtualisointeina. Muistissa ja kovalevytilassa näkyivät vain virutaalikoneelle allokoidut määrät. Ajaessa `lscpu` komennon näkyi myös prosessorin osalta ytimien määrän myös oikein. Tarkemmin en osannut tulkita tuloksia.

## g) Vapaaehtoinen: Valitse muutama rivi lokeista. Tulkitse ja analysoi.
Ajankäyttö: 10 minuuttia. ~5 minuuttia tehtävään ja ~5 minuuttia kuvankaappauksiin ja raporttiin.

Navigoin oikeaan hakemistoon.

![Journal Direcotry](h2_g1_journal_directory.png)

Tämän jälkeen yritin lukea yhtä .journal tiedostoa catillä ja totesin, ettei binääritiedoston lukeminen teksinä ole mielekästä ja noudatin c) tehtävän log readmessä vastaan tullutta ohjetta ajaa `journalctl`. Journalctl:ssa scrollasin loppupäähän ja kaivoin login koskien aikaisemman tehtävän sudona ajettua `lshw` komentoa. Login perusteella sudona ajettu komento tekee juurikäyttäjälle session, jossa komento ajetaan ja jonka jälkeen sessio suljetaan.

![Sudo Log](h2_g2_sudo_command.png)

## h) Vapaaehtoinen: Asenna jokin plugin micro-editorille ja kokeile sitä. Vaikkapa palettero, cheat tai runit.
Ajankäyttö: 56 minuuttia. ~20 minuuttia tiedonhakuun plugineista, ~5 minuuttia pluginin testeihin toimivilla asetuksilla, ~25 minuuttia vianselvitykseen MarkDowniin liittyvässä ongelmatilanteessa, ~6 kuvankaappauksiin ja raporttiin.

Asensin ensin jump pluginin tarvitsemat riippuvuudet, jonka jälkeen tein jumptest.md tiedoston MarkDown navigoinnin testaamiseksi.

![MarkDown](h2_h1_markdown.png)

F4 painamalla jump navigointiruutu kuitenkaan ei tunnistanut tiedoston otsikoita.

![MarkDown Jump](h2_h2_markdown_jump.png)

Seuraavaksi tein .js tiedoston navigointikoilua varten.

![JavaScript](h2_h3_js.png)

Tässä tiedostossa navigointi toimi.

![JavaScript jump](h2_h4_js_jump.png)

Seuraavaksi lähdin selvittämään ongelmaa MarkDownin kanssa. 

Projektin githubissa annettu komento `$ cp -nv $HOME/.config/micro/plug/micro-jump/examples/ctags $HOME/.ctags` aiheutti valitusta puuttuvasta tiedostosta, joten navigoin läpi kansiorakennetta selvittämään virhettä, ja virheen löydettyäni korjasin sen muotoon `$ cp -nv $HOME/.config/micro/plug/jump/examples/ctags $HOME/.ctags`.

![Troubleshooting 1](h2_h5_markdown_troubleshooting1.png)
![Troubleshooting 2](h2_h6_markdown_troubleshooting2.png)

Kopioituani tiedoston onnistuneesti katselin sisältöä `cat` komentoa käyttäen.

![Troubleshooting 3](h2_h6_markdown_troubleshooting3.png)

Tämän jälkeen loin uuden testitiedoston tismalleen github sivun ohjeiden mukaisesti ja navigointi toimi.

![Troubleshooting 4](h2_h7_markdown_troubleshooting4.png)
![Troubleshooting 5](h2_h8_markdown_troubleshooting5.png)
![Troubleshooting 6](h2_h9_markdown_troubleshooting6.png)

Navigointi toimi nyt myös vanhassa jumptest.md tiedostassa, eli ongelma oli käyttäjän kotihakemistosta puuttunut .ctags tiedosto.

![Troubleshooting 7](h2_h10_markdown_troubleshooting7.png)

## Lähteet

Karvinen, Tero. 2020. Command Line Basics Revisited. https://terokarvinen.com/2020/command-line-basics-revisited/

Karvinen, Tero. 2024. h2 Komentaja Pingviini. https://terokarvinen.com/linux-palvelimet/#h2-komentaja-pingviini

tldr projektin github sivu: https://github.com/tldr-pages/tldr

Karvinen, Tero. 2022. Micro-jump. https://github.com/terokarvinen/micro-jump

## Lisenssi
Sivun sisältöä saa levittää GPL-3.0 lisenssin sallimin ehdoin: https://github.com/jaolim/linux-servers?tab=GPL-3.0-1-ov-file#readme
