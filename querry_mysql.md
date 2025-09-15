# S E L E C T 
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

# G R O U P  B Y  

## 1. Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(`enrolment_date`) AS `anno_iscrizione`,
       COUNT(*) AS `numero_iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY `anno_iscrizione`;

Result: 
<code>
'2018','912'
'2019','1709'
'2020','1645'
'2021','734'
15:44:28	SELECT YEAR(`enrolment_date`) AS `anno_iscrizione`,        COUNT(*) AS `numero_iscritti` FROM `students` GROUP BY YEAR(`enrolment_date`) ORDER BY `anno_iscrizione` LIMIT 0, 1000	4 row(s) returned	0.0063 sec / 0.000012 sec

</code>

## 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT `office_address`, COUNT(*) AS `numero_insegnanti`
FROM `teachers`
GROUP BY `office_address`
ORDER BY `numero_insegnanti` DESC;
<code>

'Rotonda Martinelli 309','9'
'Borgo Elga 89','8'
'Via Eusebio 167 Appartamento 28','6'
'Rotonda Carmela 10 Piano 1','6'
'Strada Vitali 8 Piano 0','5'
'Contrada Amato 58 Piano 2','5'
'Strada Kociss 997 Piano 8','5'
'Via Mariano 48','4'
'Borgo Elio 234 Piano 4','4'
'Contrada Penelope 73','4'
'Strada Neri 577','3'
'Contrada Rita 5 Appartamento 71','3'
'Piazza Demian 856 Appartamento 63','3'
'Piazza Ferretti 619','3'
'Borgo Martino 82 Appartamento 07','3'
'Contrada Santoro 17 Appartamento 30','3'
'Incrocio Marini 9','3'
'Via Giacinto 11 Piano 8','3'
'Strada Concetta 6','3'
'Via Maika 491','3'
'Strada Lombardi 855','3'
'Piazza Pellegrino 613 Piano 8','2'
'Incrocio Testa 142 Piano 7','2'
'Rotonda Teseo 9','2'

</code>

## 3. Calcolare la media dei voti di ogni appello d'esame

SELECT `exam_id`,
       AVG(`vote`) AS `media_voti`
FROM `exam_student`
GROUP BY `exam_id`;

<code>

'1','16.8824'
'2','16.4615'
'3','20.3333'
'4','27.0000'
'6','17.5000'
'7','19.6000'
.......
.......
</code>
