
# Referat

Tema: *Soluții moderne de rețele fără fir, (tehnologii, puncte de acces și rutere 802.11).*

Student: *Curmanschii Anton, MIA2022.*.

## Conținut

- [Referat](#referat)
  - [Conținut](#conținut)
  - [Introducere](#introducere)
  - [Capacitățile-cheie lui IEE 802.11ax](#capacitățile-cheie-lui-iee-80211ax)
    - [Problema de congestie](#problema-de-congestie)
    - [Beamforming](#beamforming)
    - [Alte beneficii](#alte-beneficii)
  - [Punctele de acces](#punctele-de-acces)
    - [Tabelul cu informații la hardware](#tabelul-cu-informații-la-hardware)
    - [Compararea rapidității](#compararea-rapidității)
  - [Tehnologii noi](#tehnologii-noi)
    - [802.11az: Positioning Using Super-Resolution Time of Arrival Estimation](#80211az-positioning-using-super-resolution-time-of-arrival-estimation)
    - [802.11bd: Următoarea generație de comunicații de la vehicul la vehicul](#80211bd-următoarea-generație-de-comunicații-de-la-vehicul-la-vehicul)
    - [802.11bf: WLAN Sensing](#80211bf-wlan-sensing)
    - [802.11bh: Randomized and Changing MAC Addresses (RCM)](#80211bh-randomized-and-changing-mac-addresses-rcm)
  - [Concluzii](#concluzii)
  - [Bibliografie](#bibliografie)

## Introducere

Cele mai raspândite tehnologii 802.11 folosite astăzi sunt:
- 802.11n (Wi-Fi 4, creat în 2008);
- 802.11ac (Wi-Fi 5, creat în 2014); 
- standardul nou 802.11ax (Wi-Fi 6 și Wi-Fi 6E, 2019 și 2020 respectiv).

> Tehnologia 802.11be (Wi-Fi 7) în timpul scrierii este încă în dezvoltare.

În acest referat va fi discutată tehnologia cea mai nouă, standardul **802.11ax**.

<!-- Cu aprobarea și răspândirea fiecărui standard crește performanța și calitatea conexiunii. -->

802.11ax, denumit și High-Efficiency Wireless (HEW), are obiectivul ambițios de a îmbunătăți debitul mediu per utilizator cu cel puțin 4 ori în medii dense, unde rețeaua este folosită de un număr mare de utilizatori simultan.
Acest nou standard se concentrează pe implementarea unor mecanisme care să ofere unui număr mai mare de utilizatori un flux de date (debit mediu) consistent și fiabil în prezența multor alți utilizatori.
Pentru a atinge scopul său de a deveni un RFF de eficiența ridicată, au fost elaborate mecanisme noi, discutate în continuare.

Se vor discuta și dispozitivele noi care realizează acest standard.


## Capacitățile-cheie lui IEE 802.11ax

802.11ax include următoarele caracteristici cheie:

- Backward-compatibility cu standardele trecute 802.11a, b, g, n, ac.
- Mărește de 4 ori debitul mediu în scenarii de mare densitate, cum ar fi gările, aeroporturile și stadioanele.
- Rate de date și lățimi de canal similare cu 802.11ac, introducând și noi seturi de modulație și codificare.
- Specificat pentru funcționarea multi-utilizator prin intermediul tehnologiei MU-MIMO și OFDMA (Orthogonal Frequency Division Multiple Access).
- Îmbunătățirea fluxului de trafic și a accesului la canal.
- O mai bună gestionare a energiei pentru o durată de viață mai lungă a bateriei.


Aplicațiile urmărite includ:

- Offloading de date celulare.
- Medii cu un număr sporit de device-uri heterogene.


### Problema de congestie

Deși 802.11 este o tehnologie rezistentă, nu este neapărat eficientă.
802.11 funcționează atât la nivelul fizic, cât și la nivelul de date, având momente neeficiente la ambele.

Istoric, modificările anterioare ale standardului 802.11 au definit tehnologii care au oferit viteze de transfer de date mai mari și canale mai largi, dar nu au abordat problema eficienței.
O analogie des folosită este că, cu toate că au fost construite mașini mai rapide și șosele mai mari, ambuteiajele nu au dispărut.
În ciuda ratelor de date mai mari și a canalelor de 40/80/160 MHz utilizate în 802.11n/ac, sunt mai mulți factori contribuie la congestionarea traficului, din cauza cărora ambuteiajele uneori persistă.

Ratele de date 802.11 nu reprezintă debitul TCP.
Să se aducă aminte că frecvența radio (RF) este un mediu half-duplex și că protocolul de contenție a mediului 802.11 CSMA/CA consumă o mare parte din lățimea de bandă disponibilă.
În condiții ideale, se poate obține un debit TCP de 60-70% din debitul de date operațional folosind comunicarea 802.11n/ac între un punct de acces (AP) și un client.
Cifrele privind debitul agregat sunt considerabil mai mici în mediile practice, cu participarea activă a mai multor clienți conectați simultan la rețea, care comunică prin intermediul unui punct de acces.
Cu un număr mai mare de clienți care încearcă a-și transmite datele cresc și cheltuielile de contenție pentru mediu, iar eficiența scade.
Prin urmare, debitul agregat este, de obicei, cel mult 50% din rata de date 802.11 anunțată.

Tehnologia 802.11ax se referă la o utilizare mai bună și mai eficientă a mediului de frecvență radio existent.
Vitezele de transfer de date mai mari și canalele mai largi nu sunt obiectivele Wi-Fi 6.
Obiectivul este o gestionare mai bună și mai eficientă a traficului 802.11.
Cele mai multe îmbunătățiri aduse de Wi-Fi 6 se află la nivelul fizic și implică o nouă versiune multiutilizator a tehnologiei OFDM, care era destinată doar unui singur utilizator în tehnologii precedente.
OFDMA permite unui singur radio să comunice simultan cu mai mulți clienți, ceea ce înseamnă că comunicarea devine paralelă, nu succesivă.
Aceasta înseamnă, de asemenea, că dispozitivele care sunt adresate pot răspunde în același timp și la punctul de acces.

### Beamforming

802.11ax introduce îmbunătățiri în tehnică de beamforming care a fost introdusă încă în 802.11n și îmbunătățită în 802.11ac.
Beamforming este o tehnică care focalizează un semnal fără fir către un anumit dispozitiv de recepție, în loc ca semnalul să se răspândească în toate direcțiile, ca la o antenă de emisie.
Conexiunea directă rezultată este mai rapidă și mai fiabilă.
Prin natura undelor electromagnetice, semnalele radiază în toate direcțiile de la o singură antenă, cu excepția cazului în care sunt blocate de un obiect fizic. Pentru a concentra semnalul într-o anumită direcție, formând fasciculul de energie electromagnetică, mai multe antene aflate în imediata apropiere emit același semnal aproape în același timp.
Undele care se suprapun vor produce interferențe, care în unele zone sunt constructive (făcând semnalul mai puternic), iar în alte zone sunt distructive (făcând semnalul mai slab sau nedetectabil).
Atunci când este executat corect, acest proces concentrează un semnal într-o anumită direcție.

Beamforming în 802.11ax suportă MU-MIMO, care permite mai multor utilizatori să comunice simultan cu mai multe antene de pe router.
MU-MIMO utilizează beamforming pentru a se asigura că comunicațiile de la router sunt direcționate eficient către fiecare client conectat.
802.11ax a crescut, de asemenea, numărul de antene acceptate de la 4 la 8, ceea ce îmbunătățește ratele de transfer de date și extinde raza de acțiune a semnalelor către anumiți clienți.


### Alte beneficii

Wi-Fi 6 oferă algoritme de codificare a datelor mai bune, ceea ce duce la un debit mai mare.
Mai multe date sunt împachetate în aceleași unde radio, deoarece chipseturile care codifică și decodifică semnalele RF sunt mai robuste și pot face față unor sarcini de lucru mai mari.

În plus, Wi-Fi 6 suportă atât benzile de 2.4GHz, cât și cele de 5GHz, ceea ce nu era posibil anterior.
În timp ce majoritatea dispozitivelor mobile trec la 5GHz, datorită vitezelor mai rapide de transfer de date, dispozitivele de 2.4GHz încă există în prezent în industrie.
De exemplu, telefoane vechi, scanere și alte dispozitive suportează doar benzile 2.4GHz.
Backwards compatibility deci este o chestie importantă pentru aceste tehnologii.

Datorită razei de acțiune și eficienței sporite a Wi-Fi 6, conectarea la Wi-Fi va fi mai puțin solicitantă de energie pentru dispozitive.
De asemenea, Wi-Fi 6 introduce funcția "target wake time" (TWT), care îmbunătățește durata de viață a bateriei clienților.
TWT permite punctului de acces la rețea să comunice cu clienții și să pună conexiunea Wi-Fi în stare de repaus atunci când nu este utilizată și să se trezească automat atunci când este nevoie de Wi-Fi.
Atunci când frecvența radio Wi-Fi petrece mai mult timp în somn, această optimizare contribuie la utilizarea scăzută a bateriei.


## Punctele de acces

> Informațiile sunt băzate pe review-ul autorului Mark B de pe site [mbreviews.com](mbreviews.com), deoarece autorul referatului nu are timp, experiență sau resurse pentru a realiza o comparație hardware-ului singur.

Punctele de acces are rolul de a converti datele primite de la o conectare Ethernet cu fir într-un semnal fără fir (2.4GHz sau 5GHz), dar un router wireless poate face cam același lucru, așa că se poate întreba de ce să se aibă nevoie de un punct de acces separat?
Cu toate că routerele pot deservi toți clienții din apropiere, totodată des există puncte moarte unde semnalul pur și simplu nu ajunge, sau zona de acoperire dorită este prea mare, de aceea posibil ar trebui să se folosească cel puțin un punct de acces suplimentar pentru a extinde rețeaua sau pentru a atinge acele colțuri.

În timp ce scopul principal al unui AP este de a extinde rețeaua, unii producători au decis să adopte tehnologia de rețea mesh, ceea ce înseamnă că două sau mai multe noduri radio mici și ușoare de instalat pot forma o singură rețea fără fir care să permită roaming pe întreaga aria clădirii prin conectarea automată a clientului la nodul cel mai apropiat, astfel asigurând un semnal stabil și puternic.

### Tabelul cu informații la hardware

<table>
    <tbody>
        <tr>
            <td class="topside"></td>
            <td class="topside">Zyxel WAX650</td>
            <td class="topside">TP-Link EAP660 HD</td>
            <td class="topside">EnGenius ECW230</td>
            <td class="topside">Ubiquiti U6-LR</td>
            <td class="topside">EnGenius EAP1250</td>
            <td class="topside">Linksys LAPAC1750C</td>
        </tr>
        <tr>
            <td class="leftside">CPU</td>
            <td class="">quad-core 2.0GHz Qualcomm Atheros IPQ8072A</td>
            <td class="">quad-core 2.0GHz Qualcomm Atheros IPQ8072A</td>
            <td class="">quad-core 2.0GHz Qualcomm Atheros IPQ8072A</td>
            <td class="">dual-core 1.35GHz Mediatek ARM MT7622AV</td>
            <td class="">quad-core 717MHz Qualcomm IPQ4018 (ARM Cortex-A7)</td>
            <td class="">single-core 700MHz Qualcomm Atheros QCA9558</td>
        </tr>
        <tr>
            <td class="leftside">RAM</td>
            <td class="">512MB Nanya NT5CC256M16ER-EK</td>
            <td class="">512MB ESMT (2x M15T4G16256A)</td>
            <td class="">512MB Micron MT41K256M16TW</td>
            <td class="">512MB (2X Winbond W632GU8NB-11)</td>
            <td class="">128MB NANYA NT5CC128M16JR-EK</td>
            <td class="">128MB (2X ETRONTECH EM68B16CWQH-25H)</td>
        </tr>
        <tr>
            <td class="leftside">Storage</td>
            <td class="">512MB Winbond W29N02GZSIBA)</td>
            <td class="">128MB ESMT F59D1G81MB-AZM1P0H9N</td>
            <td class="">256MB MXIC MX30LF2G18AC-XKI</td>
            <td class="">64MB (Winbond) + 16MB &amp; 512KB (MXIC)</td>
            <td class="">32MB</td>
            <td class="">16MB Macronix MXIC MX25L12835FMI-10G</td>
        </tr>
        <tr>
            <td class="leftside">Switch</td>
            <td class="">Atheros AR8033-AL1A</td>
            <td class="">Qualcomm QCA8081</td>
            <td class="">Qualcomm QCA8081</td>
            <td class="">Marvell AQrate AQR112G</td>
            <td class="">Qualcomm Atheros QCA8072</td>
            <td class="">Qualcomm Atheros AR8035-A + Qualcomm Atheros QCA9558</td>
        </tr>
        <tr>
            <td class="leftside">5GHz Radio</td>
            <td class="">IPQ8072A (QCN5054) 802.11a/n/ac/ax 4×4:4</td>
            <td class="">IPQ8072A (QCN5054) 802.11a/n/ac/ax 4×4:4</td>
            <td class="">IPQ8072A (QCN5054) 802.11a/n/ac/ax 4×4:4</td>
            <td class="">Mediatek MT7975AN &amp; MT7915AN 802.11a/b/g/n/ac/ax 4×4:4</td>
            <td class="">Qualcomm Atheros IPQ4018 802.11a/n/ac 2×2:2</td>
            <td class="">Qualcomm Atheros QCA9880 802.11a/n/ac 3×3</td>
        </tr>
        <tr>
            <td class="leftside">2.4GHz Radio</td>
            <td class="">Qualcomm IPQ8072A (QCN5024) 802.11b/g/n/ax 4×4:4</td>
            <td class="">Qualcomm IPQ8072A (QCN5024) 802.11b/g/n/ax 4×4:4</td>
            <td class="">IPQ8072A (QCN5074) 802.11b/g/n/ax 4×4:4</td>
            <td class="">Mediatek MT7622 802.11a/b/g/n 4×4:4</td>
            <td class="">Qualcomm Atheros IPQ4018 802.11b/g/n 2×2:2</td>
            <td class="">Qualcomm Atheros QCA9558 802.11b/g/n 3×3</td>
        </tr>
        <tr>
            <td class="leftside">PoE Support</td>
            <td class="">802.3at (48V)</td>
            <td class="">802.3at (21.5W)</td>
            <td class="">802.3bt (31W)</td>
            <td class="">802.3af/at (48V)</td>
            <td class="">802.3af (12V)</td>
            <td class="">802.3af/at (12V)</td>
        </tr>
        <tr>
            <td class="leftside">LAN Ports</td>
            <td class="">1x 5GbE + 1x 1GbE</td>
            <td class="">1x 2.5GbE</td>
            <td class="">1x 2.5GbE</td>
            <td class="">1x 1GbE</td>
            <td class="">1x 1GbE</td>
            <td class="">1x 1GbE</td>
        </tr>
        <tr>
            <td class="leftside">Approximate price</td>
            <td class="">670$</td>
            <td class="">200$</td>
            <td class="">600$</td>
            <td class="">200$</td>
            <td class="">?</td>
            <td class="">200$</td>
        </tr>
    </tbody>
</table>


### Compararea rapidității

Zyxel WAX650S deține primul loc, deoarece suportă o lățime de bandă de 160MHz și oferă un debit excelent, dar TP-Link EAP660 HD îi poate lua locul în orice moment, depășind WAX650S pe banda 80MHz, și este absolut excepțional în ceea ce privește prețul (în momentul redactării).
Nu este surprinzător faptul că punctele de acces Wi-Fi 6 ies învigător, având în vedere faptul că acestea realizează tehcile utile menționate anterior.

> Toate dispozitivele au fost testate în aceleași condiții.

![5ghz](https://www.mbreviews.com/wp-content/uploads/2022/01/best-wireless-access-points-1-re-new.jpg)

![2.4ghz](https://www.mbreviews.com/wp-content/uploads/2022/01/best-wireless-access-points-2-re-new.jpg)


Însă faptul că un anumit punct de acces s-a demonstrat mai rapid nu înseamnă că este alegerea cea mai bună pentru o rețea concretă. Sunt mai mulți factori, precum scopurile de folosire, prețul, etc. care tot trebuie fi luate în considerarea când se alege un dispozitiv.

<!-- 
### Zyxel WAX650S

Zyxel WAX650S este în prezent unul dintre cele mai bune puncte de acces Wi-Fi 6 de pe piață.
Cu toate că nu este atât de ieftin în comparație cu alte dispozitive din această listă, acesta concurează cu puncte de acces de nivel enterprise, deci performanța sa este excelentă.
Desigur, utilizează tehnologia OFDMA, are suport pentru MU-MIMO, beamforming și lățime de bandă a canalului de 160 MHz, dar ce-i interesant suportează și PoE++ (Power over Ethernet).
Se pare că este necesar un switch Ethernet PoE puternic (cum ar fi XS1930-12HP) pentru a-l putea utiliza la maxim.
WAX650S vine cu un port 5GbE pentru a vă permite să depășiți vechea limitare Gigabit. -->


## Tehnologii noi

Sunt mai multe tehnologii noi care încă nu sunt răspândite sau încă sunt în starea de dezvoltare.
Aceștia vor fi incluse în standarde noi în viitor.

### 802.11az: Positioning Using Super-Resolution Time of Arrival Estimation

Un grup de studiu a fost format în ianuarie 2015 pentru a răspunde nevoilor unei "stații de a identifica poziția sa absolută și relativă față de o altă stație sau stații cu care este sau nu este asociată".
Obiectivele grupului ar fi de a defini modificări la niveluri MAC și fizic care să permită "determinarea poziției absolute și relative cu o precizie mai bună în raport cu protocolul Fine Timing Measurement (FTM) care se execută pe același tip fizic, reducând în același timp utilizarea mediului wireless existent și consumul de energie, și este scalabil pentru implementări dense."
Aprobarea finală este așteptată până în decembrie 2022.

> Prin tip fizic cred că se are în vedere implementarea nivelului fizic al substandardului 802.11 în funcție.

### 802.11bd: Următoarea generație de comunicații de la vehicul la vehicul

Unul dintre conceptele asociate cu lumea vehiculelor inteligente este că mașinile aflate în imediata apropiere pot crea rețele ad-hoc pentru a face schimb de informații legate de siguranța și gestionarea traficului.
802.11bd este definit ca un amendament pentru 802.11p pentru a îmbunătăți fiabilitatea, latența și debitul.
Aprobarea finală este așteptată până în decembrie 2022.

### 802.11bf: WLAN Sensing

Odată cu progresele recente, WLAN sau Wi-Fi a a fost utilizată cu succes pentru a realiza funcționalități de sensing, cum ar fi detectarea, localizarea și recunoașterea.
Cu toate acestea, rețelele WLAN sunt dezvoltate în principal pentru comunicație și, prin urmare, este posibil să nu poată satisface cerințele stricte de detecție în aplicații emergente.
Pentru a rezolva această problemă, un nou grup operativ 802.11bf, a fost înființat de către grupul de lucru IEEE 802.11, cu obiectivul de a crea un nou amendament la standardul WLAN pentru a oferi cerințele avansate de detecție, reducând în același timp la minimum efectul asupra comunicațiilor.

În conformitate cu definiția formală a IEEE 802.11bf, WLAN sensing se referă la utilizarea semnalelor fără fir primite de la stații capabile să detecteze WLAN pentru a determina caracteristicile (de exemplu, distanța, viteza, unghiul, mișcarea, prezența sau proximitatea, gestul) țintelor vizate (de exemplu, obiect, om, animal) într-un anumit mediu (de exemplu, cameră, casă, vehicule, întreprindere).

### 802.11bh: Randomized and Changing MAC Addresses (RCM)

Ideea este să se îmbunătățească confidențialitatea utilizatorilor în rețea.
Se poate imagina o situație unde o persoană facând o încercare de a conecta la un LAN, răspândește informația despre prezența ei în acest LAN: dacă o persoană se conectează la Wi-Fi din același device, este ușor să asocieze adresa MAC al persoanei la singura persoană.
Astfel, dacă adresa MAC este asociată dispozitivului, persoana poate fi urmărită, și nu doar în cadrul unui singur LAN, ci și în LAN-uri diferite. 

Soluția este să se genereze adresa MAC în mod aleator.

Deși acest lucru sporește confidențialitatea utilizatorului, conduce, de asemenea, la potențiale probleme de conectivitate și la o posibilă întrerupere a experienței utilizatorului.
Un exemplu este atunci când utilizatorii doresc să utilizeze o rețea Wi-Fi publică într-o cafenea, hotel, cabinet medical sau în altă parte.
Deoarece multe portaluri captive utilizează adrese MAC statice ca identificatori, este posibil ca utilizatorul să fie nevoit să se conecteze în mod repetat și să retrimită informații pe măsură ce adresa MAC se schimbă.
În alte cazuri, este posibil ca utilizatorul să fie nevoit să se autentifice și să se conecteze din nou atunci când dispozitivul se oprește, se deconectează și se reconectează prin intermediul unei adrese MAC diferite.

Un alt exemplu este atunci când familiile stabilesc controale parentale pe dispozitivele copiilor în ceea ce privește timpul petrecut în fața ecranului și conținutul.
Aceste limite sunt deseori impuse de adresa MAC a unui dispozitiv, iar dacă adresa se schimbă, controalele pot împiedica accesul la conținutul permis sau nu se mai aplică.

Operatorii de rețea tot pot întâmpina dificultăți, deoarece schimbarea continuă a identificatorilor dispozitivelor face dificilă înțelegerea de către operatori a legitimității unui utilizator sau a numărului de dispozitive conectate la o rețea la un moment dat, a aplicării de analize avansate ale rețelei și a depanării acesteia sau a menținerii controlului asupra rețelelor și utilizatorilor în scopuri comerciale.


## Concluzii

În referatul acesta s-a discutat standardul 802.11ax, tehnicile și ideile noi introduse de acest standard.
S-au prezentat superficial tehnologiile noi care urmează a fi răspândite, ori fiind în dezvoltare, ori fiind tânări.
Tehnologiile date rezolvă probleme specifice, realizând o soluție standartă.
Au fost prezentate și niște cele mai bune AP-uri (puncte de acces) care acum există pe piață.


## Bibliografie

- [Standardele IEEE 802.11](https://www.ieee802.org/11/Reports/802.11_Timelines.htm)
- [IEEE 802.11ac info](https://scdn.rohde-schwarz.com/ur/pws/dl_downloads/dl_application/application_notes/1ma192/1MA192_7e_80211ac_technology.pdf)
- [IEEE 802.11ax info](https://www.ni.com/ro-ro/innovations/white-papers/16/introduction-to-802-11ax-high-efficiency-wireless.html)
- [Standarde 802.11 overview](https://www.networkworld.com/article/3238664/80211x-wi-fi-standards-and-speeds-explained.html)
- [OFMDA](https://www.cisco.com/c/en/us/products/wireless/what-is-ofdma.html)
- [MU-MIMO](https://www.linksys.com/what-is-mu-mimo.html)
- [Data Offloading](https://www.wikiwand.com/en/Mobile_data_offloading)
- [802.11ax informații 1](https://www.extremenetworks.com/wifi6/what-is-80211ax/)
- [802.11ax informații 2](https://www.extremenetworks.com/extreme-networks-blog/wi-fi-6-for-sports-venues-4-things-you-should-know/)
- [802.11ax informații 3](https://www.actiontec.com/three-reasons-why-802-11ax-will-change-wi-fi-forever/)
- [Punctele de acces comparison](https://www.mbreviews.com/best-wireless-access-points/)
- [Wireless mesh networks](https://www.wikiwand.com/en/Wireless_mesh_network)
- [Beamforming](https://www.networkworld.com/article/3445039/beamforming-explained-how-it-makes-wireless-communication-faster.html)
- [PoE](https://www.servethehome.com/key-differences-of-poe-vs-poe-vs-poe-switches/)
- [5GbE](https://youtu.be/JjliZScYG7Y)
- [802.11az Positioning Using Super-Resolution Time of Arrival Estimation](https://www.mathworks.com/help/wlan/ug/802-11az-indoor-positioning-using-super-resolution-time-of-arrival-estimation.html)
- [Fine Timing Measurement](https://core.ac.uk/download/pdf/233003516.pdf)
- [802.11bd](https://ieeexplore.ieee.org/document/8723326)
- [802.11bf](https://arxiv.org/abs/2207.04859)
- [802.11bh](https://youtu.be/3ec7KfHPOf0)
- [802.11bh privacy and ease of use](https://beyondstandards.ieee.org/data-privacy-and-ease-of-use-in-wireless-networks/)