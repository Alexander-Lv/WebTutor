# Выполняемый код агента для пакетного назначения сотруднику набора курсов и тестов
***

Предварительно скачайте [файл Excel](Excel-TestFile01.xlsx) для загрузки.

Скопируйте приведенный код в созданный нами агент **Тестовый агент** на вкладку **"Выполняемый код"** (предыдущий код, введенный ранее на эту вкладку, можно удалить) и запустите агент, нажав на кнопку **Выполнить агент на стороне клиента**.

    // ******************ОПРЕДЕЛЕНИЕ СОТРУДНИКА*************************
    // Пример запроса: for $elem in collaborators  where (contains($elem/fullname, 'Test') 
    //		and $elem/login = 'TestTestTest')  return $elem
    
    try
    {
      // если агент выполняется на клиенте, то запросим файл ttt1.xls
      excelFileUrl = Screen.AskFileOpen( '', 'Выберите файл ttt1.xls' );
    }
    catch(err)
    {
      // агент должен выполняться на клиенте
      alert("Агент должен выполняться на клиенте. Нажмите кнопку Выполнить агент на стороне клиента.");
    }
    
    try
    {
    	sourceList = OpenDoc( excelFileUrl, 'format=excel' );
    
    	// Работаем с первым листом книги Excel 
    	// (нумерация загруженных в WebTutor листов начинается с 0; 
    	// первый лист имеет индекс 0 или задается с помощью функции ArrayOptFirstElem)
    	lineArray = ArrayFirstElem( sourceList.TopElem );
    }
    catch(err)
    {
    	alert("ОШИБКА: невозможно получить доступ к файлу " + excelFileUrl + ".");
    	alert("Агент для активации курсов и тестов завершен аварийно.");
    	return;
    }
    
    PersonID = 0;

    // Определение сотрудника, которому назначаются курсы и тесты
    // Производится отбор по ФИО и логину сотрудника
    // Пример запроса: for $elem in collaborators where (contains($elem/fullname, 'Test') and $elem/login = 'TestTestTest') return $elem
    _query_str = "for $elem in collaborators where $elem/fullname = " + XQueryLiteral(lineArray[1][0]) + 
    		" and $elem/login = " + XQueryLiteral(lineArray[1][1]) + " return $elem";
    alert(XQueryLiteral(lineArray[1][0]) + " " + XQueryLiteral(lineArray[1][1]));
    personArray = XQuery(_query_str);

    // Результатом отбора по запросу является массив
    // Работаем с первым (и единственным) элементом массива
    _elem = ArrayOptFirstElem(personArray);
     if (_elem == undefined)
     {
    	alert("ОШИБКА: сотрудник " + lineArray[1][0] + " не найден.");
    	continue;
    }
    PersonID = _elem.id;

    alert("Сотрудник: " + _elem.fullname);


     // ******************АКТИВАЦИЯ КУРСОВ*************************

    alert("Активация курсов");

    // Количество назначаемых курсов
    _counter_activate = 0;
    
    for (i = 1; i < ArrayCount(lineArray); i++)
    {
    	// Коды курсов находятся в ячейках C2, C3, C4 и т.д.
    	// Нумерация загруженных в WebTutor ячеек начинается с 0 
    	// (первый индекс – строка, второй – столбец)
    	// Ячейке C2 соответствует индекс [1][2], ячейке C3 – индекс [2][2], C4 – индекс [3][2] и т.д.
    	// Производится отбор по коду курса
    	courseArray = XQuery("for $elem in courses where $elem/code = " + 
    					XQueryLiteral(lineArray[i][2]) + " return $elem");

    	// Результатом отбора по запросу является массив
    	// Работаем с первым (и единственным) элементом массива
    	_object = ArrayOptFirstElem(courseArray);
    	
    	if (_object == undefined)
    	{
		alert("ОШИБКА: объект с первичным ключом code = " + XQueryLiteral( lineArray[i][2] ) + " не найден.");
    		continue;
	}
    	try
    	{
    		// Курс _object.id  назначается сотруднику PersonID
    		tools.activate_course_to_person( PersonID, _object.id );
    		alert( "Обработан курс " + i + " из " + (ArrayCount(lineArray)-1));
    		_counter_activate++;
	}
	catch(err)
	{
		alert("ОШИБКА: невозможно активировать/добавить объект сотруднику." + err);
		continue;
	}
    } 
    
    alert( (i - 1) + " курсов обработано, из них " + _counter_activate + " курсов успешно." );
    
    
    // ******************АКТИВАЦИЯ ТЕСТОВ*************************
        alert("Активация тестов");
    
    try
    {
	// Работаем со вторым листом книги Excel 
	// (нумерация загруженных в WebTutor листов начинается с 0; 
	// второй лист имеет индекс 1)
	lineArray1 = sourceList.TopElem[1];
    }
    catch(err)
    {
        alert(err);
        alert("Агент для активации курсов и тестов завершен аварийно.");
        return;
    }
    
    // Количество назначаемых тестов
    _counter_activate = 0;
    
    for (i = 1; i < ArrayCount(lineArray1); i++)
    {
	// Коды тестов находятся в ячейках A2, A3, A4 и т.д.
	// Нумерация загруженных в WebTutor ячеек начинается с 0 
	// (первый индекс – строка, второй – столбец)
	// Ячейке A2 соответствует индекс [1][0] второго листа, ячейке A3 – индекс [2][0], A4 – индекс [3][0] и т.д.
	// Производится отбор по коду теста
	assessmentArray = XQuery("for $elem in assessments where $elem/code = " + 
					XQueryLiteral(lineArray1[i][0]) + " return $elem");

	// Результатом отбора по запросу является массив
	// Работаем с первым (и единственным) элементом массива
	_object = ArrayOptFirstElem(assessmentArray);

	if (_object == undefined)
	{
		alert("ОШИБКА: объект с первичным ключом code = " + XQueryLiteral( lineArray1[i][0] ) + " не найден.");
		continue;
	}
	try
	{
		// Тест _object.id  назначается сотруднику PersonID
		tools.activate_test_to_person( PersonID, _object.id );
		alert( "Обработан тест " + i + " из " + (ArrayCount(lineArray1)-1));
		_counter_activate++;
	}
      catch(err)
      {
        alert("ОШИБКА: невозможно активировать/добавить объект сотруднику." + err);
        continue;
      }
    } 

    alert( (i - 1) + " тестов обработано, из них " + _counter_activate + " тестов успешно." );




После запуска программы загрузите скачанный ранее файл **Excel-TestFile01.xlsx**.


...

---

Результат выполнения агента:

![](excel02.PNG)

Внесите изменения в программу и в загружаемый файл Excel и понаблюдайте, как это повлияет на полученный результат.

***

<dd><li> <a href="5_practical_realization.md"> Возврат к части 5</a></dd>

<dd><li> <a href="README.md"> Возврат к оглавлению</a></dd>
