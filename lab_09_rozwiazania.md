Klaudiusz Orłowski isi3
***
Zadanie 1
***
```sql
delimiter $
create trigger kreatura_edycja before insert, update on kreatura for each row 
begin 
if waga <= 0 
then signal sqlstate '45000' set message_txt = 'waga kreatury jest wieksza od zera'; 
end if; 
end$
```
***
Zadanie 2
***
```sql
create trigger t4 after delete on wyprawa 
for each row 
begin 
insert into archiwum_wypraw 
values(old.id_wyprawy, old.nazwa, old.data_rozpoczecia, old.data_zakonczenia, 
(select nazwa from kreatura where kreatura.idKreatury = old.kierownik)); 
end$
```
***
