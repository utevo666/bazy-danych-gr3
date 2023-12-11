Klaudiusz Orłowski isi3
***
Zadanie 1
***
```sql
1.
create table spisek.kreatura2 as select * from wikingowie.kreatura;
create table spisek.uczestnicy as select * from wikingowie.uczestnicy;
create table spisek.etapy_wyprawy as select * from wikingowie.etapy_wyprawy;
create table spisek.sektor as select * from wikingowie.sektor;
create table spisek.wyprawa as select * from wikingowie.wyprawa;
2.
select nazwa from kreatura left join uczestnicy on kreatura.idKreatury = uczestnicy.id_uczestnika where uczestnicy.id_uczestnika is null group by nazwa;
3.
select wyprawa.nazwa, SUM(ekwipunek.ilosc) as 'suma ilosci ekwipunku' from wyprawa inner join uczestnicy on wyprawa.id_wyprawy = uczestnicy.id_wyprawy
inner join ekwipunek ON ekwipunek.idKreatury = uczestnicy.id_uczestnika group by wyprawa.nazwa;
```
***
