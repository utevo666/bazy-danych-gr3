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
1.
select kreatura.nazwa, year(kreatura.dataUr) as rok_urodzenia, zasob.idZasobu, zasob.nazwa from kreatura cross join
ekwipunek on kreatura.idKreatury = ekwipunek.idKreatury join zasob on zasob.idZasobu = ekwipunek.idZasobu having rok_urodzenia > 1670 and rok_urodzenia < 1680;
2.
select k.nazwa, e.ilosc, z.nazwa from kreatura k inner join ekwipunek e on k.idKreatury = e.IdKreatury inner join
zasob z on z.idZasobu = e.idZasobu where z.rodzaj = 'jedzenie' order by k.dataUr desc limit 5;
3.
select concat(k1.nazwa, ' - ', k2.nazwa) as nazwa, k1.idKreatury, k2.idKreatury from kreatura k1, kreatura k2 where k1.idKreatury - k2.idKreatury = 5;
```
***
Zadanie 5
***
```sql
1.
select kreatura.rodzaj, avg(e.ilosc* z.waga) from kreatura inner join ekwipunek e on kreatura.idKreatury = e.idKreatury
inner join zasob z on z.idZasobu = e.idZasobu where kreatura.rodzaj not in ('malpa','waz') and e.ilosc < 30 group by kreatura.rodzaj;
2.
select 'najmlodsza', a.maxData, b.nazwa, a.rodzaj from (select max(dataUr) maxData, rodzaj from kreatura group by rodzaj) a,
(select nazwa, dataUr from kreatura) b where a.maxData = b.dataUr union select 'najstarsza', a.minData, b.nazwa, a.rodzaj from
(select min(dataUr) minData, rodzaj from kreatura group by rodzaj) a, (select nazwa, dataUr from kreatura) b where a.minData = b.dataUr 
```
***
