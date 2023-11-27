Zadanie 1
***
```sql
1.
create table kreatura select * from wikingowie.kreatura;
create table zasob select * from wikingowie.zasob;
create table ekwipunek select * from wikingowie.ekwipunek;
2.
select * from zasob;
3.
select * from zasob where rodzaj = 'jedzenie';
4.
select idZasobu, ilosc from ekwipunek where idKreatury IN (1,3,5);
```
***
Zadanie 2
***
```sql
1.
select * from kreatura where rodzaj != 'wiedzma' and udzwig>50;
2.
select * from zasob where waga >= '2.00' and  waga <= '5.00';
3.
select * from kreatura where nazwa like '%or%' and udzwig >= 30 and udzwig <= 70;
```
***
Zadanie 3
***
```sql
1.
select * from zasob where month(dataPozyskania) between 7 and 8;
2.
select * from zasob where rodzaj is not null order by waga asc;
3.
select * from kreatura order by dataUr asc limit 5;
```
***
Zadanie 4
***
```sql
1.
select distinct rodzaj from kreatura;
2.
select concat(nazwa,' ', rodzaj) from kreatura where rodzaj like 'wi%';
3.
select concat(ilosc*waga) calkowita_waga from zasob where dataPozyskania >= '2000-01-01' and dataPozyskania <='2007-12-31';
```
***
Zadanie 5
***
```sql


```
