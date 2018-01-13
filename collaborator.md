# Структура каталога collaborator (Сотрудник)


***

Ознакомьтесь со [структурой каталога collaborator (Сотрудник)](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=collaborator) (версия 3.4.0.54 (2017.11.03)):

Также мы будем далее называть сотрудников **пользователями** или **обучающимися**.

В дальнейшем мы будем работать с объектами данного типа и выполнять с ними некоторые практические занятия.

---

id – Тип поля: integer – ID

code – Тип поля: string – Код

fullname – Тип поля: string – ФИО

login – Тип поля: string – Логин

short_login – Тип поля: string – Логин без домена

lowercase_login – Тип поля: string – Логин в нижнем регистре

email – Тип поля: string – Email

phone – Тип поля: string – Телефон

mobile_phone – Тип поля: string – Мобильный телефон

birth_date – Тип поля: date – Дата рождения

sex – Тип поля: string – Пол

pict_url – Тип поля: string – URL к файлу фотографии

position_id – Тип поля: integer – Должность – Ссылка на другой каталог: [positions](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=position)

position_name – Тип поля: string – Название должности

position_parent_id – Тип поля: integer – Подразделение – Ссылка на другой каталог: [subdivisions](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=subdivision)

position_parent_name – Тип поля: string – Название подразделения

org_id – Тип поля: integer – Организация – Ссылка на другой каталог: [orgs](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=org)

org_name – Тип поля: string – Название организации

web_banned – Тип поля: bool – Запрещен доступ на портал

is_arm_admin – Тип поля: bool – Является пользователем интерфейса администратора

is_content_admin – Тип поля: bool – Является редактором контента

role_id – Тип поля: string – Роль – Ссылка на другой каталог: [access_roles](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=access_role)

is_candidate – Тип поля: bool – Является кандидатом

candidate_status_type_id – Тип поля: integer – Статус кандидата – Ссылка на другой каталог: [candidate_status_types](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=candidate_status_type)

is_outstaff – Тип поля: bool – Является временным

is_dismiss – Тип поля: bool – Является уволенным

position_date – Тип поля: date – Дата вступления в должность

hire_date – Тип поля: date – Дата приема

dismiss_date – Тип поля: date – Дата увольнения

in_request_black_list – Тип поля: bool – В "черном списке" на подачу заявок

level_id – Тип поля: integer – Уровень – Ссылка на другой каталог: [levels](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=level)

knowledge_parts – Тип поля: string – Значения карты знаний

tags – Тип поля: string – Тэги

experts – Тип поля: string – Эксперты

current_state – Тип поля: string – Текущее состояние

development_potential_id – Тип поля: integer – Потенциал развития – Ссылка на другой каталог: [development_potentials](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=development_potential)

efficiency_estimation_id – Тип поля: integer – Оценка эффективности – Ссылка на другой каталог: [efficiency_estimations](http://news.websoft.ru/view_doc.html?mode=catalogs&catalog=efficiency_estimation)

modification_date – Тип поля: date – Дата модификации

app_instance_id – Тип поля: string – Код сервера 




***
<dd><li> <a href="3_object_model.md"> Возврат к части 3</a></dd>
<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
