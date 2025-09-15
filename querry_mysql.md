## 2 Selezionare tutti gli studenti nati nel 1990 (160)

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

Result: 
<code>14:50:55	SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990 LIMIT 0, 1000	160 row(s) returned	0.0068 sec / 0.000081 sec</code>

## 2 Selezionare tutti i corsi che valcano più di 10 cfu 

SELECT *
FROM `courses`
WHERE `cfu` > 10;

Result: 
<code>14:59:53	SELECT * FROM `courses` WHERE `cfu` > 10 LIMIT 0, 1000	479 row(s) returned	0.0023 sec / 0.0028 sec</code>

## Selezionare tutti gli studenti che abbiano più di 30 anni

SELECT *
FROM `students`
WHERE `date_of_birth` < "1995-09-15"

Result: 
<code>15:09:49	SELECT * FROM `students` WHERE `date_of_birth` < "1995-09-15" LIMIT 0, 1000	1000 row(s) returned	0.0032 sec / 0.0033 sec</code>
