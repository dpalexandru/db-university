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