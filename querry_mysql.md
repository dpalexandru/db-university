## 1 Selezionare tutti gli studenti nati nel 1990 (160).

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

Result: 
<code>14:50:55	SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990 LIMIT 0, 1000	160 row(s) returned	0.0068 sec / 0.000081 sec</code>

## 2 Selezionare tutti i corsi che valcano più di 10 cfu. 

SELECT *
FROM `courses`
WHERE `cfu` > 10;

Result: 
<code>14:59:53	SELECT * FROM `courses` WHERE `cfu` > 10 LIMIT 0, 1000	479 row(s) returned	0.0023 sec / 0.0028 sec</code>

## 3 Selezionare tutti gli studenti che abbiano più di 30 anni.

SELECT *
FROM `students`
WHERE `date_of_birth` < "1995-09-15"

Result: 
<code>15:09:49	SELECT * FROM `students` WHERE `date_of_birth` < "1995-09-15" LIMIT 0, 1000	1000 row(s) returned	0.0032 sec / 0.0033 sec</code>

## 4 Selezionare tutti corsi del primo semeste del primo anno di un qualsiasi corso di laurea. 

SELECT *
FROM `courses`
WHERE `year` = 1
  AND `period` = "I semestre";

Result: 
<code>15:15:33	SELECT * FROM `courses` WHERE `year` = 1   AND `period` = "I semestre" LIMIT 0, 1000	286 row(s) returned	0.0025 sec / 0.0021 sec
</code>

## 5 Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio dopo le 14 del 20/06/2020

SELECT *
FROM `exams`
WHERE DATE(`date`) = '2020-06-20'
  AND TIME(`hour`) > '14:00:00';

Result: 
<code>15:27:46	SELECT * FROM `exams` WHERE DATE(`date`) = '2020-06-20'   AND TIME(`hour`) > '14:00:00' LIMIT 0, 1000	21 row(s) returned	0.010 sec / 0.000026 sec
</code>

## 6 Selezionare tutti i corsi di laurea magistrale

SELECT *
FROM `degrees`
WHERE `level` = "magistrale"

Result: 
<code>15:33:49	SELECT * FROM `degrees` WHERE `level` = "magistrale" LIMIT 0, 1000	38 row(s) returned	0.0014 sec / 0.000029 sec
</code>

## 7 Da quanti dipartimenti è composta l'università? 
SELECT COUNT(*) AS `numero_dipartimenti`
FROM `departments`;

Result: 
<code>15:36:51	SELECT COUNT(*) AS `numero_dipartimenti` FROM `departments` LIMIT 0, 1000	1 row(s) returned	0.00031 sec / 0.0000060 sec
</code>

## 8 Quanti sono gli insegnanti che non hanno un numero di telefono? 

SELECT COUNT(*) AS `insegnanti_senza_telefono`
FROM `teachers`
WHERE `phone` IS NULL 

Result: 
<code>15:39:16	SELECT COUNT(*) AS `insegnanti_senza_telefono` FROM `teachers` WHERE `phone` IS NULL LIMIT 0, 1000	1 row(s) returned	0.0051 sec / 0.000012 sec
</code>

