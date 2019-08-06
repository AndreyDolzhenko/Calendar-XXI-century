/*
VERSION: 0.1
AUTHOR: Dolzhenko Andrey
COPYRIGHT: © Dolzhenko Andrey, 2019
LICENSE: MIT License
DESCRIPTION:
Программа позволяет вывести на экран календарь любого года XXI века от 2001 до 2099. Год вводит пользователь.

MIT License
Copyright (c) 2019 Dolzhenko Andrey
*/

#include<iostream>
#include<stdlib.h>
#include<time.h>

using namespace std;

int year;
int month;
int day;
int firstDay;
int counter;

void Enter_Date(); // // функция позволяет вводить первую дату, контролирует ее введение в рамках одного столетия, 12-ти месяцев и дней с учетом месяца
bool Check_Year(int X); // проверяет, чтобы год был в пределах 21 столетия от 2001 до 2099 года
int First_Day_Calculation(); // функция определяет, каким днем недели является первый день в году 
int First_Day_Definition(int C); // функция возвращает значение первого дня месяца - какой это день недели
int Continuation(); // предлагаем продолжить или закончить
void Logo(); // логотип
void Calendar();

int main()
{
	setlocale(LC_ALL, "ru");

	Logo(); // Выводим логотип
	cout << "\n\n";
	system("pause");

	cout << "\n\n\tПРОГРАММА ВЫВОДИТ   К А Л Е Н Д А Р Ь    X X I  ВЕКА";
	cout << "\n\n\tОТ  2001  ДО  2099 ГОДА";
	   
	cout << "\n\n\tГОД необходимо вводить четырмя цифрами. Например: 2019\n";
	Enter_Date();

	bool state = true;
	int number, degree;	
	///////////////////////////////////////
	//Основное тело программы:
	////////////////////////////////////
	while (1) // вводим цикл для повторного воспроизведения календаря, пока пользователь не введет "2"
	{
		cout << "\n";
		system("cls");

		Logo();
		cout << "\n\n";

		cout << "\n\t\t\tКАЛЕНДАРЬ НА " << year << " ГОД\n\n";

		year = year % 100;
		//cout << year<<endl;

		firstDay = First_Day_Calculation();
		//cout << "\n\n\tПервый день в году " << firstDay << endl;

		Calendar();			

		Continuation();
		cout << endl;
	}
////////////////////////////////
}

void Logo()
{
	cout << "\n\n\n";
	cout << "        **      **\t**      **    \t**  \t*******       \t******* \t**    **      \n";
	cout << "         **    ** \t **    **     \t**  \t*********     \t******* \t**   **     \n";
	cout << "          **  **  \t  **  **      \t**  \t**     **     \t**      \t**  **     \n";
	cout << "           ****   \t   ****       \t**  \t********      \t*****   \t*****     \n";
	cout << "           ****   \t   ****       \t**  \t********      \t*****   \t*****     \n";
	cout << "          **  **  \t  **  **      \t**  \t***    ***    \t**      \t**  **     \n";
	cout << "         **    ** \t **    **     \t**  \t**********    \t******* \t**   **     \n";
	cout << "        **      **\t**      **    \t**  \t********      \t******* \t**    **     \n";

	cout << "\n\n\n";

	cout << "(c) Долженко Андрей\n";	
}

void Calendar()
{
	int Month_31[40];
	int x = 0;
	month = 0; // Обнуляем месяц для корректного повторного воспроизведения календаря

	for (counter = 0; counter < 12; counter++) // в данном цикле переменная month будет увеличиваться на единицу, определяя месяц
	{

		First_Day_Definition(counter);

		month++; // определяет изменение месяца с каждым проходом цикла
		cout << "\n\tПн\tВт\tСр\tЧт\tПт\tСб\tВс\n";

		if ((month < 8 && month % 2 != 0) || (month >= 8 && month % 2 == 0)) // построение календаря для месяца с 31 днем
		{
			for (int i = 0; i < 31 + firstDay; i++)
			{
				if (i < firstDay)
				{
					cout << "\t  ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}
				else
				{
					cout << "\t";
					x++;
					Month_31[i] = x;
					cout << Month_31[i] << " ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}

			}
		}

		else if ((month > 8 && month % 2 != 0) || (month < 8 && month % 2 == 0 && month != 2)) // определяет месяц с 30 днями
		{
			for (int i = 0; i < 30 + firstDay; i++)
			{
				if (i < firstDay)
				{
					cout << "\t  ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}
				else
				{
					cout << "\t";
					x++;
					Month_31[i] = x;
					cout << Month_31[i] << " ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}

			}
		}

		else if ((year % 4 != 0) && (month == 2)) // определяет февраль с 28 днями
		{
			for (int i = 0; i < 28 + firstDay; i++)
			{
				if (i < firstDay)
				{
					cout << "\t  ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}
				else
				{
					cout << "\t";
					x++;
					Month_31[i] = x;
					cout << Month_31[i] << " ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}

			}
		}

		if ((year % 4 == 0) && (month == 2)) // определяет високосный февраль
		{
			for (int i = 0; i < 29 + firstDay; i++)
			{
				if (i < firstDay)
				{
					cout << "\t  ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}
				else
				{
					cout << "\t";
					x++;
					Month_31[i] = x;
					cout << Month_31[i] << " ";
					if (i % 7 == 0)
					{
						cout << endl;
					}
				}

			}
		}



		x = 0;

		cout << endl;
	}
}

int First_Day_Calculation() // расчитывает каким днем недели будет первый день в году
{
	int FD = 0;
	int checkYear = 0;
	int x = 5;

	year = year % 100;

	for (int i = 0; i < year; i++)
	{
		checkYear++;

		if (checkYear % x != 0)
		{
			FD++;
		}
		else
		{
			FD += 2;
			x += 4;
		}


		if (FD <= 7)
		{
			FD = FD;
		}
		else
		{
			FD -= 7;
		}


		//cout << FD << " ";

	}

	return FD;
}

int First_Day_Definition(int C) // расчитывает каким днем недели будет первый день в месяце
{
	switch (C) // условие для вывода названия месяца и определения дня недели в первый день месяца
	{

	case 0:
		firstDay = firstDay;
		cout << "\n\t\tЯ Н В А Р Ь\n";
		break;
	case 1:
		if (firstDay <= 4 && firstDay > 0)
		{
			firstDay = (firstDay - 4) + 7; // условие позволяет менять дни в пределах от 1 до 7
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tФ Е В Р А Л Ь\n";
		break;
	case 2:
		if (year % 4 != 0)
		{
			firstDay = firstDay;
		}
		else
		{
			if (firstDay < 7)
			{
				firstDay += 1;
			}
			else
			{
				firstDay = (firstDay + 1) - 7;
			}

		}

		cout << "\n\t\tМ А Р Т\n";
		break;
	case 3:
		if (firstDay <= 4)
		{
			firstDay = (firstDay - 4) + 7;
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tА П Р Е Л Ь\n";
		break;
	case 4:
		if (firstDay <= 5)
		{
			firstDay = firstDay + 2;
		}
		else if (firstDay > 5 && firstDay <= 7)
		{
			firstDay = (firstDay + 2) - 7;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tМ А Й\n";
		break;
	case 5:
		if (firstDay <= 4)
		{
			firstDay = (firstDay - 4) + 7;
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tИ Ю Н Ь\n";
		break;
	case 6:
		if (firstDay <= 5)
		{
			firstDay = firstDay + 2;
		}
		else if (firstDay > 5 && firstDay <= 7)
		{
			firstDay = (firstDay + 2) - 7;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tИ Ю Л Ь\n";
		break;
	case 7:
		if (firstDay <= 4)
		{
			firstDay = (firstDay - 4) + 7;
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tА В Г У С Т\n";
		break;
	case 8:
		if (firstDay <= 4)
		{
			firstDay = (firstDay - 4) + 7;
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tС Е Н Т Я Б Р Ь\n";
		break;
	case 9:
		if (firstDay <= 5)
		{
			firstDay = firstDay + 2;
		}
		else if (firstDay > 5 && firstDay <= 7)
		{
			firstDay = (firstDay + 2) - 7;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tО К Т Я Б Р Ь\n";
		break;
	case 10:
		if (firstDay <= 4)
		{
			firstDay = (firstDay - 4) + 7;
		}
		else if (firstDay > 4 && firstDay <= 7)
		{
			firstDay = firstDay - 4;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tН О Я Б Р Ь\n";
		break;
	case 11:
		if (firstDay <= 5)
		{
			firstDay = firstDay + 2;
		}
		else if (firstDay > 5 && firstDay <= 7)
		{
			firstDay = (firstDay + 2) - 7;
		}
		else
		{
			cout << "\n\t!!!ОШИБКА!!!\n";
		}
		cout << "\n\t\tД Е К А Б Р Ь\n";
		break;

	default:
		break;
	}
	return firstDay;
}

void Enter_Date() // функция позволяет вводить первую дату, контролирует ее введение в рамках одного столетия, 12-ти месяцев и дней с учетом месяца
{
	do
	{
		cout << "\n\n\tВведите ГОД: "; cin >> year;

	} while (!Check_Year(year));

}

bool Check_Year(int X)
{
	if (X < 2001 || X > 2099)
	{
		cout << "\n\n\tВведите год от 2001 до 2099!!!";
		return false;

	}
	return true;
}

int Continuation()
{
	char start;
	int startCheck = 0;
	
	cout << "\n\n\tПосмотреть другой год?\n\tДа - 1\tНет - 2\t"; cin >> start;	
	
		do
		{

			if (start >= 49 && start <= 50)
			{
				startCheck = start - 48;
				
			}

			else
			{
				cout << "\n\t!!!Введенный символ некорректен!!!\n";
				cout << "\n\n\tПосмотреть другой год?\n\tДа - 1\tНет - 2\t"; cin >> start;

				continue;
			}
		}while (startCheck < 1 || startCheck > 2);
	
	
	//cout << "\n\n\t" << startCheck << endl;
	
	switch (startCheck)
	{
		case 1:
		{
		Enter_Date();
		break;
		}
						
		case 2:
		{
		exit(0);
		break;
		}	
	}   
	
}

