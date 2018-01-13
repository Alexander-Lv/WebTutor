# Структура каталога assessment (Тест)


***

Ознакомьтесь со [структурой каталога assessment (Тест)](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=assessment) (версия 3.4.0.54 (2017.11.03)):

В дальнейшем мы будем работать с объектами данного типа и выполнять с ними некоторые практические занятия.

---

id – Тип поля: integer – ID

code – Тип поля: string – Код

title – Тип поля: string – Название теста

status – Тип поля: string – Статус – common.course_test_states

duration – Тип поля: integer – Продолжительность в минутах

duration_days – Тип поля: integer – Продолжительность в днях

passing_score – Тип поля: integer – Проходной балл

not_display_unfinished_score – Тип поля: bool – Не показывать набранный балл для незавершенных тестов

is_open – Тип поля: bool – Открытый тест (возможно самостоятельно назначить тест)

external_type – Тип поля: string – Тип внешнего источника – common.assessment_external_types

modification_date – Тип поля: date – Дата модификации

app_instance_id – Тип поля: string – Код сервера

knowledge_parts – Тип поля: string – Значения карты знаний

tags – Тип поля: string – Тэги

experts – Тип поля: string – Эксперты

user_access_role – Тип поля: string – Роль пользователя – Ссылка на другой каталог: [access_roles](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=access_role)

user_group_id – Тип поля: integer – Группа пользователя – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)  



***
<dd><li> <a href="3_object_model.md"> Возврат к части 3</a></dd>
<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
