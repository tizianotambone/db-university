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
