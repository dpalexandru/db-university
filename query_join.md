# J O I N 

# 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT `students`.`id` AS `id_studente`,
       `students`.`name` AS `nome`,
       `students`.`surname` AS `cognome`,
		`degrees`.`name` AS `corso_di_laurea`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

Result: 
<code>14:27:28	SELECT `students`.`id` AS `id_studente`,        `students`.`name` AS `nome`,        `students`.`surname` AS `cognome`,   `degrees`.`name` AS `corso_di_laurea` FROM `students` JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia' LIMIT 0, 2000	68 row(s) returned	0.0012 sec / 0.000026 sec
</code>

## 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT `degrees`.`id` AS `id_corso`,
       `degrees`.`name` AS `corso_di_laurea`,
       `departments`.`name` AS `dipartimento`
FROM `degrees`
JOIN `departments` 
  ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`level` = "magistrale"
  AND `departments`.`name` = 'Dipartimento di Neuroscienze';

  Result: 
<code>14:39:44	SELECT `degrees`.`id` AS `id_corso`,        `degrees`.`name` AS `corso_di_laurea`,        `departments`.`name` AS `dipartimento` FROM `degrees` JOIN `departments`    ON `degrees`.`department_id` = `departments`.`id` WHERE `degrees`.`level` = "magistrale"   AND `departments`.`name` = 'Dipartimento di Neuroscienze' LIMIT 0, 2000	1 row(s) returned	0.00051 sec / 0.0000081 sec
</code>