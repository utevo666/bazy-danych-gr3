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
select rodzaj, sum(waga) suma_wag from zasob group by rodzaj;
2.
select nazwa, avg(waga) as srednia_waga, sum(ilosc), sum(waga) from zasob group by nazwa having sum(ilosc) >= 4 and sum(waga) > 10;
3.
select rodzaj, count(distinct(nazwa)) from zasob group by rodzaj having min(ilosc) > 1;
```
***
Zadanie 3
***
```sql

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
