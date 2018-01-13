# Структура каталога course (Электронный курс)


***

Ознакомьтесь со [структурой каталога course (Электронный курс)](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=course) (версия 3.4.0.54 (2017.11.03)).

В дальнейшем мы будем работать с объектами данного типа и выполнять с ними некоторые практические занятия.

---

code – Тип поля: string – Код курса

name – Тип поля: string – Название курса

status – Тип поля: string – Статус – common.course_test_states

price – real – Стоимость курса

max_score – Тип поля: integer – Максимальный балл

yourself_start – Тип поля: bool – Может быть назначен самостоятельно

duration – Тип поля: integer – Продолжительность в днях

person_id – Тип поля: integer – Эксперт курса – Ссылка на другой каталог: [collaborators](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=collaborator)

cl_course_id – Тип поля: integer – Электронный курс – Ссылка на другой каталог: [cl_courses](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=cl_course)

education_org_id – Тип поля: integer – Обучающая организация – Ссылка на другой каталог: [education_orgs](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=education_org)

base_url – Тип поля: string – Базовый url

pwt_disp – Тип поля: bool – Отображать в списке Персонального WebTutora

user_access_role – Тип поля: string – Роль пользователя – Ссылка на другой каталог: [access_roles](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=access_role)

user_group_id – Тип поля: integer – Группа пользователя – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)

modification_date – Тип поля: date – Дата модификации

app_instance_id – Тип поля: string – Код сервера

knowledge_parts – Тип поля: string – Значения карты знаний

tags – Тип поля: string – Тэги

experts – Тип поля: string – Эксперты




***
<dd><li> <a href="3_object_model.md"> Возврат к части 3</a></dd>
<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
