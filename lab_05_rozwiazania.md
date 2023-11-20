Klaudiusz Orłowski isi3

Zadanie 1
***
```sql
a)
select * from postac where rodzaj = 'wiking'
and nazwa != 'Bjorn'
order by wiek desc;
delete from postac where id_postaci in (12,4)
b)
alter table walizka drop foreign key walizbka_ibfk_1
alter table przetwory drop foreign key przetwory_ibfk_1
alter table przetwory drop foreign key przetwory_ibfk_2
alter table postac change id_postaci id_postaci int;
alter table postac drop primary key;
```
***
Zadanie 2
***
```sql
a)
alter table postac add pesel char(11) first;
update postac set pesel = '17763874635' where id_postaci = 1;
alter table postac add primary key(pesel);
b)
alter table postac modify rodzaj enum('wiking','ptak','kobieta','syrena');
c)
insert into postac (id_postaci,nazwa,rodzaj,wiek,pesel) values ('9','Gertruda Nieszczera','syrena','28','12345678917');
```
***
Zadanie 3
***
```sql
a)
update postac set statek='Odyn'
where nazwa like '%a%';
b)
update statek set max_ladownosc = 0.7 * max_ladownosc where data_wodowania >= '1901-01-01' and data_wodowania <= '2000-01-01';
c)
alter table postac modify wiek int unsigned check(wiek <=1000);
```
