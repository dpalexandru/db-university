## 1 selezionare tutti gli studenti nati nel 1990 (160)

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;

Result: <code>14:50:55	SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990 LIMIT 0, 1000	160 row(s) returned	0.0068 sec / 0.000081 sec</code>


