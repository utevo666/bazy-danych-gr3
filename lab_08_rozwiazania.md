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
Zadanie 2
***
```sql
1.
select wyprawa.nazwa, count(uczestnicy.id_uczestnika) as 'liczba uczestnikow', group_concat(kreatura.nazwa separator ', ') as 'imiona uczestnikow'
from wyprawa left join uczestnicy on wyprawa.id_wyprawy = uczestnicy.id_wyprawy left join kreatura on kreatura.idKreatury = uczestnicy.id_uczestnika group by wyprawa.nazwa;
2.
select etapy_wyprawy.kolejnosc, sektor.nazwa, kreatura.nazwa from wyprawa inner join etapy_wyprawy on wyprawa.id_wyprawy = etapy_wyprawy.idWyprawy
inner join sektor on sektor.id_sektora = etapy_wyprawy.sektor inner join kreatura on kreatura.idKreatury = wyprawa.kierownik order by etapy_wyprawy.kolejnosc asc, wyprawa.data_rozpoczecia asc;
```
***
Zadanie 3
***
```sql
1.
select ifnull(count(etapy_wyprawy.sektor), 0) as ilosc_odwiedzin, sektor.nazwa from sektor
left join etapy_wyprawy on etapy_wyprawy.sektor = sektor.id_sektora group by sektor.id_sektora;
2.
select kreatura.nazwa, if(count(uczestnicy.id_wyprawy) = 0, 'nie bral udzialu w wyprawie', 'bral udzial w wyprawie')
as czy_wyprawa from kreatura left join uczestnicy on uczestnicy.id_uczestnika = kreatura.idKreatury group by kreatura.nazwa;
```
***
