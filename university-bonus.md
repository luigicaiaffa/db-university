## BONUS

1. Contare quanti iscritti ci sono stati ogni anno

```sql

-- SELECT 
-- 	YEAR(`enrolment_date`)  AS `year`,
-- 	COUNT(`id`) AS `count`
-- FROM `university`.`students`
-- GROUP BY `enrolment_date` ;

```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql

SELECT 
	`office_address`,
	COUNT(`id`) AS `count`
FROM `university`.`teachers`
GROUP BY `office_address` ;

```

3. Calcolare la media dei voti di ogni appello d'esame

```sql

SELECT 
	`exam_id`,
	AVG(`vote`)
FROM `university`.`exam_student`
GROUP BY `exam_id` ;


```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql



```