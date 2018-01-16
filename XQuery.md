# Запросы XQuery. Примеры запросов


***

В системе WebTutor широко используются запросы в формате XQuery. Эти запросы менее известны, чем аналогичные запросы на языке SQL, но после некоторой практики запросы XQuery становятся вполне понятными.

Для понимания того, как устроены запросы XQuery, на наш взгляд, может быть полезна следующая прекрасная иллюстрация взята из книги Максима Юркова ["Progressive WebTutor"](https://maksimyurkov.gitbooks.io/progressive-webtutor/content/).

![](XQuery01.jpg)

---

Отбор сотрудников по одному критерию:

for $elem in collaborators where contains($elem/fullname, 'Test') return $elem

SELECT * FROM collaborators WHERE CONTAINS(fullname, 'Test')

_query_str = "for $elem in collaborators where contains($elem/fullname, 'Test') return $elem";

**Примечание**: Обратите внимание на то, что значение критерия поиска (ФИО) заключено в одинарные кавычки, а весь текст кода запроса – в двойные кавычки.

CONTAINS — предикат, используемый для выполнения полнотекстового поиска подстроки в полях, содержащих символьные данные.

---

Отбор сотрудников по двум критериям:

for $elem in collaborators where (contains($elem/fullname, 'Test') and $elem/login = 'TestTestTest') return $elem

SELECT * FROM collaborators WHERE CONTAINS(fullname, 'Test') AND login = 'TestTestTest'

_query_str = "for $elem in collaborators where (contains($elem/fullname, 'Test') and $elem/login = 'TestTestTest') return $elem";

---

Отбор теста по одному критерию (коду):

for $elem in assessments where $elem/code = '00000017' return $elem

    SELECT * FROM assessments WHERE code = '00000017'

    _query_str = " for $elem in assessments where $elem/code = '00000017' return $elem ";

---

Отбор курса по одному критерию (коду):

for $elem in courses where $elem/code = 'OTM8' return $elem

SELECT * FROM courses WHERE code = 'OTM8'

 _query_str = "for $elem in courses where $elem/code = 'OTM8' return $elem";

---

Отбор сотрудников с упорядочиванием (по возрастанию):

for $elem in collaborators where contains($elem/fullname, 'Иванов') order by $elem/id return $elem

или 

for $elem in collaborators where contains($elem/fullname, 'Иванов') order by $elem/id ascending return $elem

SELECT * FROM collaborators WHERE CONTAINS(fullname, 'Иванов') ORDER BY id 

_query_str = "for $elem in collaborators where contains($elem/fullname, 'Иванов') order by $elem/id return $elem";


----

Отбор сотрудников с упорядочиванием (по убыванию):

for $elem in collaborators where contains($elem/fullname, 'Иванов') order by $elem/id descending return $elem

SELECT * FROM collaborators WHERE CONTAINS(fullname, 'Иванов') ORDER BY id DESC

_query_str = "for $elem in collaborators where contains($elem/fullname, 'Иванов') order by $elem/id descending return $elem";

---

Отбор законченных тестов для определенного сотрудника:

for $emp in test_learnings where contains($emp/person_fullname, 'Иванов Иван Иванович') return $emp

---

Отбор незаконченных тестов для определенного сотрудника:

_query_str = "for $emp in active_test_learnings where contains($emp/person_fullname, 'Иванов Иван Иванович') return $emp";

---

Отбор пройденных тестов (state_id=4) среди завершенных по данному сотруднику:

for $elem in collaborators where contains($elem/fullname, 'Иванов') and $elem/state_id=4 return $elem

_query_str = "for $elem in collaborators where contains($elem/fullname, 'Иванов') and $elem/state_id=4 return $elem";

---

Отбор пройденных тестов (state_id=4) среди незавершенных по данному сотруднику:

for $elem in collaborators where contains($elem/fullname, 'Иванов') and $elem/state_id=4 return $elem

_query_str = "for $elem in collaborators where contains($elem/fullname, 'Иванов') and $elem/state_id=4 return $elem";

---





просмотра каталога
Нажимаем ctrl + shift + f8. Получаем интерфейс позволяющий получить данные из каталога.



---


Что понадобится для выполнения этих упражнений?


- Учебная система WebTutor в минимальной комплектации (в частности, должны присутствовать модули "Персонал и организационная структура", "Дистанционное обучение", "Тестирование", "Системное администрирование", "Дизайнер".

- Доступ к WebTutor Administrator (на январь 2018 г. - версия WebTutor Administrator 3.4). 

- Административные права в WebTutor Administrator.

- Доступ к корпоративному сайту news.websoft.ru компании WebSoft, где размещены, в том числе, различные материалыф по программированию в среде WebTutor (такой доступ имеют практически все пользователи WebTutor Administrator).

---

Большинство упражнений предполагает их выполнение без изменения предлагаемого кода. Однако в отдельных случаях нужно будет внести в код некоторые изменения, связанные с особенностями используемой системы WebTutor. Сообщение о необходимости внесения изменений в код будет начинаться со слов **Внести изменения!**, выделенных жирным шрифтом.

 


***



<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
