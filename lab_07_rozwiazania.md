Klaudiusz Orłowski isi3
***
Zadanie 1
***
```sql
1.
select avg(waga) from kreatura where rodzaj = 'wiking';
2.
select rodzaj, avg(waga) from kreatura group by rodzaj;
3.
select avg(2023 - year(dataUr)) as sredni_wiek from kreatura;
```
***
Zadanie 2
***
```sql
1.
select rodzaj, sum(waga*ilosc) suma_wag from zasob group by rodzaj;
2.
select nazwa, avg(waga) as srednia_waga, sum(ilosc), sum(waga) from zasob group by nazwa having sum(ilosc) >= 4 and sum(waga) > 10;
3.
select rodzaj, count(distinct(nazwa)) from zasob group by rodzaj having min(ilosc) > 1;
```
***
Zadanie 3
***
```sql
1.
select k.nazwa, sum(e.ilosc) as ilosc from kreatura k inner join ekwipunek e on e.idKreatury = k.idKreatury group by k.nazwa;
2.
select k.nazwa, z.nazwa from kreatura k inner join ekwipunek e on e.idKreatury = k.idKreatury left join zasob z on z.idZasobu=e.idZasobu;
3.
select k.nazwa, e.idZasobu from kreatura k left join ekwipunek e on k.idKreatury = e.idKreatury having e.idZasobu is null;
```
***
Zadanie 4
***
```sql

```
***
Zadanie 5
***
```sql

```
