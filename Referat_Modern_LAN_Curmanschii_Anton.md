
# Referat

Tema: *Soluții moderne de rețele fără fir, (tehnologii, puncte de acces și rutere 802.11).*

Student: *Curmanschii Anton, MIA2022.*.

## Conținut

- [Referat](#referat)
  - [Conținut](#conținut)
  - [Introducere](#introducere)
  - [Capacitățile-cheie lui IEE 802.11ax](#capacitățile-cheie-lui-iee-80211ax)
  - [Problema de congestie](#problema-de-congestie)
  - [Alte beneficii](#alte-beneficii)

## Introducere

Cele mai raspândite tehnologii 802.11 folosite astăzi sunt:
- 802.11n (Wi-Fi 4, creat în 2008);
- 802.11ac (Wi-Fi 5, creat în 2014); 
- standardul nou 802.11ax (Wi-Fi 6 și Wi-Fi 6E, 2019 și 2020 respectiv).

> Tehnologia 802.11be (Wi-Fi 7) în timpul scrierii este încă în dezvoltare.

În acest referat va fi discutată tehnologia cea mai nouă, standardul **802.11ax**.

<!-- Cu aprobarea și răspândirea fiecărui standard crește performanța și calitatea conexiunii. -->

802.11ax, denumit și High-Efficiency Wireless (HEW), are obiectivul ambițios de a îmbunătăți debitul mediu per utilizator cu cel puțin 4 ori în medii dense, unde rețeaua este supraîncărcată.
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


## Problema de congestie

Deși 802.11 este o tehnologie rezistentă, nu este neapărat eficientă.
802.11 funcționează atât la nivelul fizic, cât și la nivelul de date, având momente neeficiente la ambele.

Din punct de vedere istoric, modificările anterioare ale standardului 802.11 au definit tehnologii care ne-au oferit viteze de transfer de date mai mari și canale mai largi, dar nu au abordat problema eficienței.
O analogie des folosită este că, cu toate că au fost construite mașini mai rapide și șoseauri mai mari, ambuteiajele nu au dispărut.
În ciuda ratelor de date mai mari și a canalelor de 40/80/160 MHz utilizate în 802.11n/ac, sunt mai mulți factori contribuie la congestionarea traficului, din cauza cărora ambuteiajele uneori persistă.

Ratele de date 802.11 nu reprezintă debitul TCP.
Să se aducă aminte că frecvența radio (RF) este un mediu half-duplex și că protocolul de contenție a mediului 802.11 CSMA/CA consumă o mare parte din lățimea de bandă disponibilă.
În condiții de ideale, se poate obține un debit TCP de 60-70% din debitul de date operațional folosind comunicarea 802.11n/ac între un punct de acces (AP) și un client.
Cifrele privind debitul agregat sunt considerabil mai mici în mediile practice, cu participarea activă a mai multor clienți conectat simultan la rețea, care comunică prin intermediul unui punct de acces.
Cât mai mulți clienți încearcă a-și transmite datele, atât cresc și cheltuielile de contenție pentru mediu, iar eficiența scade.
Prin urmare, debitul agregat este, de obicei, cel mult 50% din rata de date 802.11 anunțată.

Tehnologia 802.11ax se referă la o utilizare mai bună și mai eficientă a mediului de frecvență radio existent.
Vitezele de transfer de date mai mari și canalele mai largi nu sunt obiectivele Wi-Fi 6.
Obiectivul este o gestionare mai bună și mai eficientă a traficului 802.11.
Cele mai multe îmbunătățiri aduse de Wi-Fi 6 se află la nivelul fizic și implică o nouă versiune multiutilizator a tehnologiei OFDM, care era destinată doar unui singur utilizator în tehnologii precedente.
OFDMA permite unui singur radio să comunice simultan cu mai mulți clienți, ceea ce înseamnă că comunicarea devine paralelă, nu succesivă.
Aceasta înseamnă, de asemenea, că dispozitivele care sunt adresate pot răspunde în același timp și la punctul de acces.


## Alte beneficii

Wi-Fi 6 oferă algoritme de codificare a datelor mai bune, ceea ce duce la un debit mai mare.
Mai multe date sunt împachetate în aceleași unde radio, deoarece chipseturile care codifică și decodifică semnalele RF sunt mai robuste și pot face față unor sarcini de lucru mai mari.

În plus, Wi-Fi 6 suportă atât benzile de 2.4GHz, cât și cele de 5GHz, ceea ce nu era posibil anterior.
În timp ce majoritatea dispozitivelor noastre mobile trec la 5GHz, datorită vitezelor mai rapide de transfer de date, dispozitivele de 2.4GHz încă există în prezent în industrie.
De exemplu, unele telefoane vechi, scanere și alte dispozitive suportează doar benzile 2.4GHz.
Backwards compatibility deci este o chestie importantă pentru aceste tehnologii.

Datorită razei de acțiune și eficienței sporite a Wi-Fi 6, conectarea la Wi-Fi va fi mai puțin solicitantă de energie pentru dispozitive, dar la fel și "obiectivele de timp de trezire". Țintele de timp de trezire permit unui punct de acces wireless să comunice cu dispozitivele conectate, pentru a notifica cât timp pot dormi sau intra în repaus dispozitivele între momentul în care vorbesc cu (primesc semnale) AP-ul, precum și când trebuie să fie activ pentru a comunica din nou cu acel AP.  Această perioadă de inactivitate va contribui în mare măsură la conservarea duratei de viață a bateriei dispozitivelor personale (cum ar fi smartphone-urile, tabletele etc.) și a dispozitivelor IoT. 


- [Standardele IEEE 802.11](https://www.ieee802.org/11/Reports/802.11_Timelines.htm)
- [IEEE 802.11ac info](https://scdn.rohde-schwarz.com/ur/pws/dl_downloads/dl_application/application_notes/1ma192/1MA192_7e_80211ac_technology.pdf)
- [IEEE 802.11ax info](https://www.ni.com/ro-ro/innovations/white-papers/16/introduction-to-802-11ax-high-efficiency-wireless.html)
- [Overview](https://www.networkworld.com/article/3238664/80211x-wi-fi-standards-and-speeds-explained.html)
- [OFMDA](https://www.cisco.com/c/en/us/products/wireless/what-is-ofdma.html)
- [MU-MIMO](https://www.linksys.com/what-is-mu-mimo.html)
- [Data Offloading](https://www.wikiwand.com/en/Mobile_data_offloading)
- [802.11ax practical](https://www.extremenetworks.com/wifi6/what-is-80211ax/)
- [802.11ax more stuff](https://www.extremenetworks.com/extreme-networks-blog/wi-fi-6-for-sports-venues-4-things-you-should-know/)