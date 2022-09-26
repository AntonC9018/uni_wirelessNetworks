
# Lucrul individual la RFF

Tema: *Configurarea și testarea unei rețele fără fir în packet tracer.*

Student: *Curmanschii Anton, MIA2022.*


## Obiectivele

1. Să se conecteze la un router fără fir;
2. Să configureze routerul fără fir;
2. Să conectezee un dispozitiv la routerul fără fir folosind un fir;
2. Să convecteze un dipozitiv fără fir la routerul fără fir;
2. Să adauge un punct de acces la rețea pentru a extinde aria de acoperire a rețelei;
2. Să actualizeze setările routerului.


## Relizarea topologiei

Topologia cu care se va petrece activitatea, routerele nu au fost conectate între sine sau configurate.

![Topology](images/topology_no_wires.png)


## 1. Să se conecteze la un router fără fir

> Pasul 1: conectez adminul la routerul fără fir.

Folosesc cablu Eithernet straigh-through pentru a conecta Admin-ul la router.
Conectarea devine verde, înseamnă că am avut succes.

![Admin connection](images/admin_connection_to_router.png)


> Pasul 2: configurez admin să folosească DHCP.

Intru în **Admin -> Desktop -> IP Configuration** și bifez DHCP.

![](images/use_dhcp_admin.png)


> Pasul 3: mă conectez la interfața web de configurare a routerului de pe Admin.

Pentru aceasta, intru în **Admin -> Desktop -> Web Brower** și introduc adresa routerului: *192.168.0.1*.
Routerul cere login și parola, care sunt ambele "admin" implicit.
Introduc "admin" în ambele câmpuri, și se încarcă meniul configurării.

![](images/router_configuration.png)

Adresa care a primit-o Admin este *192.168.0.100*, ceea ce poate fi explicat dacă ne uităm mai jos până la Network Setup, care arată diapazonul adreselor DHCP, începând cu adresa lui Admin, prima adresă alocată pentru primul client, și conținând 49 adrese consecutive nealocate. 

![](images/router_dhcp_address_range.png)

> Pasul 4: modific configurarea routerulului.

Vom seta valori diferite pentru configurarea IP a routerului.
Vom folosi configurarea statică și un DNS, pe care îl vom configura mai târziu.

![](images/router_static_config.png)

Scrolez jos și apas *Save Settings*.

Rămâne să configurăm celelălt router și serverul DNS.

Am conectat routerele între sine, și am configurat adresa interfeței din partea routerului doi.

![](images/router_router_connection.png)

Am conectat serverul, am adăugat adresa la a doua interfață de la al doilea router, am configurat adresa ip al serverului.

![](images/interface_2_other_router.png)
![](images/dns_server_ip_config.png)

Am configurat serviciul DNS pe server, adaugând o înregistrare nouă: *www.stuff.com*, locată pe același server.

![](images/dns_server_dns_config.png)

> Pasul 5: verificarea conexiunei.

Am dat câte un ping de la consola adminului la toate alte ip adresele, cu succes:
- Routerul fără fir: 209.165.200.225;
- Routerul 2: 209.165.200.226;
- Serverul DNS: 209.165.201.1;
- Serverul, prin DNS: www.stuff.com.

Nu putem ajunge la Admin direct de pe Serverul DNS, deoarece, cred, routerul fără fir are un NAT configurat automat, datorită cui adresa locală nu este vizibilă pentru Routerul 2.
În plus, routerul 2 nu are configurat să trimită mesaje cu IP-uri necunoscute la Routerul fără fir.
De fapt, nici nu știe ce să facă cu ele și pur și simplu le pică.

Curios este faptul că routerul fără fir nu răspunde la pinguri de la server, cu toate că request-urile ajung la el.
Cred că pur și simplu este configurat implicit să nu răspundă la ele.

[source](https://itexamanswers.net/13-1-10-packet-tracer-configure-a-wireless-network-instructions-answer.html)


## 2. Să configureze routerul fără fir

Aici configurez setările WLAN al routerului fără fir.