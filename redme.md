Dopo aver creato un nuovo database nel vostro MySQL Workbench e aver importato lo schema allegato, eseguite le query del file allegato.
Cosa consegnare?
Dopo aver testato le vostre query con MySQL Workbench, riportatele in un file txt e caricatelo nella vostra repo.

SELECT * FROM db_university.students
WHERE  YEAR(`date_of_birth`) = 1990;

SELECT * FROM db_university.courses
WHERE `cfu` > 10;

SELECT * FROM db_university.students
WHERE TIMESTAMPDIFF( YEAR,date_of_birth, CURDATE())>=30;

SELECT * FROM db_university.courses
WHERE period = 'I semestre' AND year = 1;

SELECT * FROM db_university.exams
WHERE date = '2020-06-20'
AND hour >'14:00:00';

SELECT * FROM db_university.degrees
WHERE level = 'magistrale'

SELECT DISTINCT name 
FROM db_university.departments;


ESERCIZIO 27/05/2025
ESERCIZIO DEL GIORNO  GROUP BY

1 SELECT YEAR(`enrolment_date`) AS `anno`,        
COUNT(*) AS `numero_iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY `anno`;



SELECT COUNT(*)AS `numero_insegnanti,`office_address`
FROM `teachers`
GROUP BY `OFFICE ADDRESS`



SELECT AVG(`vote`) AS `media_voto`,`exam_id`
FROM `exam_student`
GROUP BY `exam_id


COUNT (*) AS `corsi_di_laurea`,`departement_id`
FROM `degrees`
GROUP BY `departement_id`


UTILIZZO DEL JOIN



SELECT *
FROM `students`
JOIN `degrees` ON students.degree_id = degrees.id
WHERE degrees.name ='Corso di Laurea in Economia'


SELECT *
from `degrees`
join departments on degrees.department_id = departments.id
where departments.name = 'Dipartimento di Neuroscienze' and degrees.level = 'Magistrale' 




SELECT  `courses`.`*`,
FROM `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.course_id`
JOIN  teachers ON `teacher `. `id` = course_tacher .teacher_id
WHERE`teacher`.`id` = 44;





SELECT 
  students.name, 
  students.surname, 
  degrees.name AS degree_name, 
  departments.name AS department_name
FROM students
JOIN degrees  ON students.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
ORDER BY students.surname , students.name ;


SELECT  degrees.name AS nome_laurea, departments.name AS nome_dipartimento, courses.name AS nome_corso, teachers.name, teachers.surname
FROM degrees
JOIN courses ON courses.degree_id = degrees.id
JOIN course_teacher ON course_teacher.course_id = courses.id
JOIN teachers ON teachers.id = course_teacher.teacher_id
JOIN departments ON departments.id = degrees.department_id


SELECT DISTINCT teachers.*
FROM teachers
JOIN course_teacher ON teachers.id = course_teacher.teacher_id
JOIN courses ON courses.id = course_teacher.course_id
JOIN degrees ON degrees.id = courses.degree_id
JOIN departments ON departments.id = degrees.department_id
WHERE departments.name = "Dipartimento di matematica";

