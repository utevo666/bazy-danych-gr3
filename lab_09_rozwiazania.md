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
create trigger wyprawa_after_delete
after delete on wyprawa
for each row
begin
insert into archiwum_wyprawy values(
select w.id_wyprawy, w.nazwa ,w.data_rozpoczecia, w.data_zakonczenia, k.nazwa from wyprawa w
inner join kreatura k on k.idKreatury = w.kierownik
where id_wyprawy = old.id_wyprawy;
end$
```
***
