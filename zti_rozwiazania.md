Klaudiusz Orłowski isi 3
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
select imie, nazwisko, datediff(CURDATE(),data_urodzenia) as wiek from pracownik
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
select kategoria, group_concat(nazwa_towaru) as lista_produktow from towar group by kategoria 
```
***
