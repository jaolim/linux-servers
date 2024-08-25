# h1 Oma Linux

### x) FSF Free Software Definition

FSF määrittää vapaan ohjelmiston ohjelmistoksi, jota voi ajaa, muokata, tutkia, kopioida, ja julkaista haluamallaan tavalla.
Edellytys tälle on pääsy lähtekoodiin.


### a) Asenna Linux virtuaalikoneeseen

Ympäristö: Windows 11 Education käyttöjärjestelmä, AMD Ryzen 3900XT prosessori, 32GB muistia

Latasin VirtualBox 7.0.20 exen ja Debian live 12.6.0 imagen koneelle.
Lähdin asentamaan VirtualBoxia kaikilla ominaisuuksilla. Keskeytin ensimmäisen asennuksen asentaakseni puuttuvat riippuvuudet Python tukeen.

![VirtualBox Install](1_virtualbox_install.png)

![Python Install](2_python_install.png)

Asensin puuttuvat riippuvuudet ja asensin VirtualBoxin kaikilla ominaisuuksilla.

Tein uuden Virtuaalikoneen VirtualBoxiin seuraavilla asetuksilla:

![Virtual Machine](3_virtual_machine.png)

Boottasin Debianin live version ja testasin hiiren, näppäimistön ja internet yhteyden toimimisen, sekä ajoin yksinkertaisen komennon shellissä.

![Shell](5_hello_debian.png)

Asensin Debianin seuraavilla asetuksilla:

![Settings](6_install_settings.png)

Boottasin virtuaalikoneen ja varmistin koneen speksien olevan oikein.

![Debian Running](8_debian_running.png)

Prosessissa meni kokonaisuudessaan 1h 10min ja ainoa vastaan tullut ongelma oli puuttuva riippuvuus virtualboxin hallinnointiin Python scripteillä (todennäköisesti turha ominaisuus, mutta asensimpa kuitenkin), jonka selvittäminen tapahtui parissa minuutissa.

## x)Vapaaehtoinen bonus: suosikkiohjelmani Linuxilla. Tee ja raportoi jokin yksinkertainen toimenpide haluamallasi Linux-ohjelmalla.

Hain Googlesta tietoa Linux CPU testeistä ja päädyin Sysbench ohjelmaan.

Sysbench install:

![Sysbench Install](h1_x1_sysbench_install.png)

Sysbench manuaali (man sysbench komento):

![Sysbench Manual](h1_x2_sysbench_manual.png)

Testin asetukset (neljän loogisen ytimen testi):

![Benchmark Parameters](h1_x3_benchmark_parameters.png)

Testitulokset:

![Benchmark Results](h1_x4_benchmark_results.png)

Yhteenvetona voin todeta, etten osaa tarkemmin tulkita testituloksia, mutta koska virtuaalikone tai pyörittänyt pöytäkone eivät kaatuneet, joten pidän sitä onnistuneena.


## Lähteet
Tehtävä: https://terokarvinen.com/linux-palvelimet/#h1-oma-linux

Ohjeet: https://terokarvinen.com/2021/install-debian-on-virtualbox/

Debian image: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/debian-live-12.6.0-amd64-xfce.iso

VirtualBox lataussivu: https://www.virtualbox.org/wiki/Downloads

Sysbench benchmark ohjelma: https://github.com/akopytov/sysbench
