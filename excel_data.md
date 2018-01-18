# ������ ������ �� ����� Excel
***

![](underconstruction.png)

---

	// ������� ������ ��������� ����� �� ������� ������� � �������� ���� Excel.
	// ���� Excel ������ ���� ������.
	excelFileUrl = Screen.AskFileOpen( '', '�������� ����&#09;*.*' );
try
{
	sourceList = OpenDoc(excelFileUrl, 'format=excel' );
	// ����������� ��� ������, ��������� � ����� Excel.

	workbook = sourceList.TopElem;
	// workbook - ��� ���������� ������ ������ �� ������ ����� Excel.
	// ������ ������� �������� ������� workbook (������� �����), � ���� �������, ������������ � ��������� ������.

	// ���������� ������������ ����������� ������
	for (_sheet in workbook)
	{
		alert(_sheet.name);
	}

	// �������� � ������� �� ������� ������������ �����
	lineArray = sourceList.TopElem[0];
	// sourceList.TopElem[0] - ��� �� �� �����, ��� � ArrayFirstElem(sourceList.TopElem)
	// � ������ ����������� ��������� ������ ������ lineArray[][].
	// ������ �������� ������� - ����� ������� (�� 0: ����� 0 - ������ 1; ����� 1 - ������ 2; ����� 2 - ������ 3 � �.�.).
	// ������ �������� ������� - ����� ������ (�� 0: ����� 0 - ������� A; ����� 1 - ������� B; ����� 2 - ������� C � �.�.).
}
catch(err)
{
	alert("������: ���������� �������� ������ � ����� " + excelFileUrl + ".");
	alert("����� �������� ��������.");
	return;
}

	alert("���������� ����� �� ����� " + sourceList.TopElem[0].name + " � ����� Excel (ArrayCount(lineArray)) = " + ArrayCount(lineArray) );

// ����� ���������� �� �������� A, B � � ������� ����� �� ����� (6 �����)
for (i = 0; i < ArrayCount(lineArray); i++)
{
	alert("lineArray[i][0] = " + lineArray[i][0] + "\n" + 
		"lineArray[i][1] = " + lineArray[i][1] + "\n" + 
		"lineArray[i][2] = " + lineArray[i][2] );
}



## ������ ������ �� ����� � ������ Sheet2 � ����� Excel

	// ������� ������ ��������� ����� �� ������� ������� � �������� ���� Excel.
	// ���� Excel ������ ���� ������.

	// ��������� �������� �����, � �������� ����� ������� ������ (��� ����� ��������� � ��������� ���������� WORKSHEET).
	WORKSHEET = 'Sheet2';
	excelFileUrl = Screen.AskFileOpen( '', '�������� ����&#09;*.*' );
	try
	{
		sourceList = OpenDoc(excelFileUrl, 'format=excel' );
		// ����������� ��� ������ �� ����� Excel.

		workbook = sourceList.TopElem;
		// workbook - ��� ���������� ������ ������ �� ������ ����� Excel.
		// ������ ������� �������� ������� workbook (������� �����), � ���� �������, ������������ � ��������� ������.
	}
	catch(err)
	{
		alert("������: ���������� �������� ������ � ����� " + excelFileUrl + ".");
		alert("����� �������� ��������.");
		return;
	}

	worksheet = undefined;
	// ������������ �������� ������������ ����������� ������ � ����� ������� ����� 
	for (_sheet in workbook)
	{
		alert(_sheet.name);
		if (_sheet.name == WORKSHEET)	
		{
			alert("���� " + WORKSHEET + " ������");
			worksheet = _sheet;
			// ����� �� ����� ������ ������� �����
			break;
		}
	}

	// ���� ���� �� ������...
	if (worksheet == undefined)
	{
		alert("������: ������� ���� [" + WORKSHEET + "] �� ������");
		// ����� �� ������
		return;
	}


	// ������ worksheet - ��� ������� ��������� ������ ������ �� ����� Sheet2
	alert("���������� ����� �� ����� " + worksheet.name + " � ����� Excel (ArrayCount(worksheet)) = " + ArrayCount(worksheet) );

	// ����� ���������� �� �������� A, B � � ���������� ����� �� ����� (4 �����)
	for (i = 0; i < ArrayCount(worksheet); i++)
	{
		alert("worksheet[i][0] = " + worksheet[i][0] + "\n" + 
			"worksheet[i][1] = " + worksheet[i][1] + "\n" + 
			"worksheet[i][2] = " + worksheet[i][2] );
	}




 

***



<dd><li> <a href="5_practical_realization.md"> ������� � ����� 5</a></dd>



<dd><li> <a href="README.md"> ������� � ����������</a></dd>
