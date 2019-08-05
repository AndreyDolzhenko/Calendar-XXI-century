# Calendar-XXI-century
Консольное приложение для вывода на экран календаря на любой год в диапазоне от 2001 до 2099.

    © Dolzhenko Andrey, 2019. adol2000@rambler.ru
      Версия: 0.1 (Август 2019)

СОДЕРЖАНИЕ

   - [Что делает?](#what)
   - [Воспроизведение](#relis)
   - [Начало работы](#start)
   - [Описание кода программы](#kod)
   - [Планируемые доработки](#improvements)

### <a name="what">Что делает?</a>

Приложение позволяет вывести на экран календаря на любой год XXI века в диапазоне от 2001 до 2099.  
Год вводит пользователь. После вывода года на экран программа предлагает выбрать другой год либо выйти из программы.

### <a name="relis">Воспроизведение:</a>

• Приложение воспроизводится в консоле.  
• Все команды необходимо вводить ЦИФРАМИ, следуя инструкциям в приложении.

***Пример использования:***  

<img src=https://github.com/AndreyDolzhenko/Calendar-XXI-century/blob/master/Calendar1.gif  width="320" height="320" />

### <a name="start">Начало работы:</a>

Скопируйте файл .exe в любое место на вашем компьютере. Если у вас установлена программа Visual Studio, игра запустится.
Если программа Visual Studio не установлена, система может запросить следующие файлы: msvcp140d.dll, vcruntime140.dll, ucrtbased.dll — это компоненты пакета от корпорации Microsoft Visual C++ 2015.
Скачайте данные файлы и разместите в корневой директории windows:

    C:\Windows\System32 для x32 системы;
    C:\Windows\SysWOW64 для x64 системы.
    Перезагрузите компьютер и запустите программу.

Скачать файлы для Windows 10 и других версий можно пройдя по ссылкам:

Для x64:

    msvcp140d.dll
    vcruntime140.dll
    ucrtbased.dll

Для x32:

    msvcp140d.dll
    vcruntime140.dll
    ucrtbased.dll

### <a name="kod">Описание кода программы:</a>

**Подключение библиотек и пространства имен:**

#include<iostream> - Библиотека ввода и вывода информации  
#include<stdlib.h> - Стандартная библиотека для контроля выполнения программы  
#include<time.h> - Библиотека для работы с системной датой и временем. Используется при расчете случайного значения  

**Основные функции:**

    void Logo() - Заставка. Выводится каждый раз при смене экрана. Является логотипом программы
         
    int First_Day_Calculation() - функция определяет, каким днем недели является первый день в году. Определяет все последующие дни недели в году.
    
    void Enter_Date() - функция позволяет вводить первую дату, контролирует ее введение в рамках одного столетия
    
    bool Check_Year(int X) - Функция, которая проверяет принадлежность года к диапазону от 2001 до 2099 года
    
    int Continuation() - Функция выводит меню для повторного введения года, либо выхода из программы
      
### <a name="improvements">Планируемые доработки:</a>

- добавление синтаксического анализатора;
- добавление функции определения дня недели введенной даты;
- добавление функции для расчета количества рабочих дней во введенном периоде.
 
