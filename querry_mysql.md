## 1 selezionare tutti gli studenti nati nel 1990 (160)

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

Result: 
<code>14:50:55	SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990 LIMIT 0, 1000	160 row(s) returned	0.0068 sec / 0.000081 sec</code>

## selezionare tutti i corsi che valcano più di 10 cfu 

SELECT *
FROM `courses`
WHERE `cfu` > 10;

Result: 
<code>14:59:53	SELECT * FROM `courses` WHERE `cfu` > 10 LIMIT 0, 1000	479 row(s) returned	0.0023 sec / 0.0028 sec</code>
