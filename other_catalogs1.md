# Структуры каталогов active_test_learning (Незаконченный (незавершенный) тест) и test_learning (Законченный (завершенный) тест)


***

Ознакомьтесь со структурами каталогов [active_test_learning (Незаконченный (незавершенный) тест)](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=active_test_learning) и [test_learning (Законченный (завершенный) тест)](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=test_learning).

В дальнейшем мы будем работать с объектами данного типа и выполнять с ними некоторые практические занятия.

---

## Данные каталога active_test_learning (Незаконченный (незавершенный) тест) (версия 3.4.0.54 (2017.11.03))

code – Тип поля: string – Код

assessment_id – Тип поля: integer – Тест – Ссылка на другой каталог: [assessments](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=assessment)

assessment_name – Тип поля: string – Название теста

person_id – Тип поля: integer – Сотрудник – Ссылка на другой каталог: [collaborators](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=collaborator)

person_fullname – Тип поля: string – ФИО сотрудника

person_position_name – Тип поля: string – Должность

person_org_name – Тип поля: string – Организация

person_subdivision_name – Тип поля: string – Подразделение

person_instance_id – Тип поля: string – Код сервера сотрудника

person_current_state – Тип поля: string – Текущее состояние сотрудника

event_id – Тип поля: integer – Мероприятие – Ссылка на другой каталог: [events](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=event)

group_id – Тип поля: integer – Группа – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)

start_usage_date – Тип поля: date – Дата активации

start_learning_date – Тип поля: date – Дата начала обучения

last_usage_date – Тип поля: date – Дата последнего посещения

max_end_date – Тип поля: date – Дата планируемого завершения

score – real – Баллы

state_id – Тип поля: integer – Состояние – common.learning_states

time – Тип поля: integer – Время модуля

max_score – real – Максимальный балл

assessment_appraise_id – Тип поля: integer – Процедура оценки – Ссылка на другой каталог: [assessment_appraises](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=assessment_appraise)

question_num – Тип поля: integer 

question_answered_num – Тип поля: integer 

question_passed_num – Тип поля: integer 

user_access_role – Тип поля: string – Роль пользователя – Ссылка на другой каталог: [access_roles](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=access_role)

user_group_id – Тип поля: integer – Группа пользователя – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)

creation_date – Тип поля: date – Дата создания

creation_user_id – Тип поля: integer – Пользователь

modification_date – Тип поля: date – Дата модификации

modification_user_id – Тип поля: integer – Пользователь

app_instance_id – Тип поля: string – Код сервера

***

## Данные каталога test_learning (Законченный (завершенный) тест) (версия 3.4.0.54 (2017.11.03))

assessment_id – Тип поля: integer – Тест – Ссылка на другой каталог: [assessments](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=assessment)

assessment_name – Тип поля: string – Название теста

person_id – Тип поля: integer – Сотрудник – Ссылка на другой каталог: [collaborators](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=collaborator)

person_fullname – Тип поля: string – ФИО сотрудника

person_position_name – Тип поля: string – Должность

person_org_name – Тип поля: string – Организация

person_subdivision_name – Тип поля: string – Подразделение

person_instance_id – Тип поля: string – Код сервера сотрудника

person_current_state – Тип поля: string – Текущее состояние сотрудника

event_id – Тип поля: integer – Мероприятие – Ссылка на другой каталог: [events](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=event)

group_id – Тип поля: integer – Группа – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)

start_usage_date – Тип поля: date – Дата активации

start_learning_date – Тип поля: date – 

last_usage_date – Тип поля: date – Дата последнего посещения

max_end_date – Тип поля: date – Дата планируемого завершения

score – real – Баллы

text_result – Тип поля: string – Описание итога

state_id – Тип поля: integer – Состояние – Ссылка на другой каталог: common.learning_states

time – Тип поля: integer – Время модуля

max_score – real – Максимальный балл

assessment_appraise_id – Тип поля: integer – Активный тест – Ссылка на другой каталог: [assessment_appraises](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=assessment_appraise)

active_test_learning_id – Тип поля: integer – Незаконченный тест

question_num – Тип поля: integer 

question_answered_num – Тип поля: integer 

question_passed_num – Тип поля: integer 

user_access_role – Тип поля: string – Роль пользователя – Ссылка на другой каталог: [access_roles](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=access_role)

user_group_id – Тип поля: integer – Группа пользователя – Ссылка на другой каталог: [groups](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=group)

creation_date – Тип поля: date – Дата создания

creation_user_id – Тип поля: integer – Пользователь

modification_date – Тип поля: date – Дата модификации

modification_user_id – Тип поля: integer – Пользователь

app_instance_id – Тип поля: string – Код сервера 




***
<dd><li> <a href="3_object_model.md"> Возврат к части 3</a></dd>
<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
