Klaudiusz Orłowski isi3

Zadanie 1
***
```sql
1. 
create table postac ( 
  id_postaci int primary key auto_increment,
  nazwa varchar(40),
  rodzaj enum("wiking","ptak","kobieta"),
  data_ur date,
  wiek int unsigned);
2.
insert into postac values(default,"Bjorn","wiking","1700-10-23",323);
insert into postac values(default,"Drozd","ptak","1700-10-23",323);
insert into postac values(default,"Tesciowa","kobieta","1700-10-23",323);
update postac set wiek=88 where id_postaci=3;
```
***
Zadanie 2
***
```sql
1.
create table walizka (
  id_walizki int primary key auto_increment,
  pojemnosc int unsigned,
  kolor enum("rozowy","czerwony","teczowy","zolty"),
  id_wlasciciela int,
  foreign key(id_wlasciciela) references postac(id_postaci) on delete cascade);
2.
alter table walizka alter kolor set default "rozowy";
insert into walizka values(default,30,"rozowy",1);
insert into walizka values(default,20,"zolty",3);
```
***
Zadanie 3
```sql
1.
create table izba ( 
  adres_budynku varchar(50),
  nazwa_izby varchar(50),
  metraz int unsigned,
  wlasciciel varchar(40),
  primary key (adres_budynku, nazwa_izby),
  foreign key(wlasciciel) references postac(nazwa) on delete set null);

2.
alter table izba add kolor_izby varchar(20) default 'czarny' after metraz;
3.
insert into izba values('sloneczna 54','spizarnia','10','czerwony','Bjorn');
```
***
Zadanie 4
```sql
1.
create table przetwory(
  id_przetworu int primary key auto_increment,
  rok_produkcji varchar(4) default '1654',
  id_wykonawcy int,
  zawartosc varchar(40),
  dodatek varchar(40) default 'papryczka chilli',
  id_konsumenta int,
  foreign key(id_wykonawcy) references postac(id_postaci),
  foreign key(id_konsumenta) references postac(id_postaci));

2
insert into przetwory values(default,default,'1','bigos',default,'3')

```
***
Zadanie 5
```sql
1.
insert into postac values
(default, 'Asgard', 'wiking', '1678-08-12',340),
(default, 'Khorad', 'wiking', '1864-03-22',170),
(default, 'Edgard', 'wiking', '1723-06-13',300),
(default, 'Floki', 'wiking', '1623-07-15',430),
(default, 'Ragnar', 'wiking', '1738-01-30',300);

2.

create table statek (
nazwa_statku varchar(30) primary key,
rodzaj_statku enum('byrding','drakkar','sneka','knara'),
data_wodowania date,
max_ladownosc int,
check(max_ladownosc>0)
);
```
