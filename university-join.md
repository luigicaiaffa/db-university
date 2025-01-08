1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql

SELECT *
FROM `students`
JOIN `degrees`
ON `degree_id` = `degrees`.`id`
WHERE `degree_id` = 53 ;

```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

```sql

SELECT * 
FROM `degrees`
JOIN `departments`
ON `department_id` = `departments`.`id`
WHERE `department_id` = 7 AND `degrees`.`level` = 'magistrale' ;

```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql

SELECT * 
FROM `course_teacher`
JOIN `courses`
ON `course_id` = `courses`.`id` 
WHERE `teacher_id` = 44 ;

```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome

```sql

SELECT * 
FROM `students`
JOIN `degrees`
ON `degree_id` = `degrees`.`id` 
JOIN `departments`
ON `department_id` = `departments`.`id` 
ORDER BY `students`.`name`, `students`.`surname` ;

```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql

SELECT * 
FROM `course_teacher`
JOIN `courses`
ON `course_id` = `courses`.`id`
JOIN `degrees`
ON `degree_id` = `degrees`.`id` 
JOIN `teachers`
ON `teacher_id` = `teachers`.`id` ;

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)

```sql

SELECT * 
FROM `course_teacher`
JOIN `teachers`
ON `teacher_id` = `teachers`.`id` 
JOIN `courses`
ON `course_id` = `courses`.`id`
JOIN `degrees`
ON `degree_id` = `degrees`.`id` 
WHERE `department_id` = 5 ;

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.

```sql

SELECT 
	`course_id`,
	`student_id`,
    COUNT(`course_id`) AS `number_of_try`,
	MAX(`vote`) AS `max_vote`
FROM `exam_student`
JOIN `students`
ON `student_id` = `students`.`id`
JOIN `exams`
ON `exam_id` = `exams`.`id`
GROUP BY `student_id`, `course_id` 
HAVING `max_vote` >= 18 ;

```