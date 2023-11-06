Klaudiusz Orłowski isi3

Zadanie 1

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

Zadanie 2

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

Zadanie 3

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

Zadanie 4

1.

