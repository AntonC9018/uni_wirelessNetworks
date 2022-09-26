
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

Am conectat routerele între sine, și am configurat 
![](images/router_router_connection.png)


[source](https://itexamanswers.net/13-1-10-packet-tracer-configure-a-wireless-network-instructions-answer.html)
