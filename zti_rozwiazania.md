Klaudiusz Orłowski isi 3
Zadania czesc 1
***
Zadanie 1
***
```sql
select imie, nazwisko, data_urodzenia from pracownik
```
***
Zadanie 2
***
```sql
select imie, nazwisko, year(curdate())- year(data_urodzenia) as wiek from pracownik
```
***
Zadanie 3
***
```sql
select dzial.nazwa, count(pracownik.id_pracownika) from pracownik inner join dzial on pracownik.dzial = dzial.id_dzialu group by dzial.id_dzialu
```
***
Zadanie 4
***
```sql
select k.nazwa_kategori, count(t.id_towaru) from towar t inner join kategoria k on t.kategoria = k.id_kategori group by k.id_kategori;
```
***
Zadanie 5
***
```sql
select k.nazwa_kategori, group_concat(t.nazwa_towaru) from towar t
inner join kategoria k on t.kategoria = k.id_kategori
group by k.id_kategori;
```
***
Zadanie 6
***
```sql
select round(avg(pensja), 2) as srednie_zarobki from pracownik
```
***
Zadanie 7
***
```sql
select round(avg(pensja), 2) from pracownik
where year(curdate()) - year(data_zatrudnienia) >= 5;
```
***
Zadanie 8
***
```sql
select t.nazwa_towaru, sum(pz.ilosc) from towar t inner join pozycja_zamowienia pz on t.id_towaru = pz.towar group by t.nazwa_towaru order by 2 desc limit 10;
```
***
Zadanie 9
***
```sql
select z.numer_zamowienia, sum(pz.ilosc * pz.cena) as wartosc from zamowienie z inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie where year(z.data_zamowienia) = 2017 and quarter(z.data_zamowienia) = 1 group by z.id_zamowienia
```
***
Zadanie 10
***
```sql
select imie, nazwisko, sum(pz.ilosc * pz.cena) as wartosc from zamowienie z inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie 
inner join pracownik p on p.id_pracownika = z.pracownik_id_pracownika
group by p.id_pracownika order by wartosc desc;
```
***
Zadania czesc 2
***
Zadanie 1
***
```sql
select d.nazwa, min(p.pensja), max(p.pensja), avg(p.pensja) from pracownik p inner join dzial d on p.dzial = d.id_dzialu group by d.id_dzialu

```
***
Zadanie 2
***
```sql
select k.pelna_nazwa, z.numer_zamowienia, sum(pz.ilosc * pz.cena) as wartoscfrom zamowienie z
inner join pozycja_zamowienia pz on z.id_zamowienia = pz.zamowienie inner join klient k on k.id_klienta = z.klient group by z.id_zamowienia order by wartosc desc limit 10;
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
