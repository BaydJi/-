# C#
Через *Console* мы обращаемся к системному терминалу.

## Для начала работы с С# в терминале нужно ввести:

    dotnet new console - создать новый проект
    dotnet run - запустить проект

- Write(); - вывод в одну строку
- WriteLine(); - В конце перейти на новую строку
- ReadLine(); - считать строку из терминала

Пример:

    Console.Write("Введите ваше имя ");
    string username = Console.ReadLine();
    Console.Write("Привет, ");
    Console.Write(username);

# Типы данных:

1. int - целые числа
2. double - вещественные числа
3. string - строки
4. bool - логический тип данных(истина или ложь, 1 или 0)

# Арифметические операции:

1. Сложение +
2. Вычетание -
3. Деление / 
4. Умножение *
5. Остаток от деления %
6. Менять приоретет операций ()

# Вспомогательные функции

## 1. ToLower
Функция tolower выполняет преобразование прописных букв в строчные. То есть, преобразует свой параметр в строчный эквивалент, если символ с заглавной буквы.

Пример:

    Console.Write("Введите имя пользователя: ");
    string username = Console.ReadLine();

    if(username.ToLower() == "маша")
    {
        Console.WriteLine("Ура, это же МАША!");
    }
    else
    {
        Console.Write("Привет, ");
        Console.WriteLine(username);
    }

## 2. new Random().Next(min,max)
Рандомные, случайные чилсла(int numberA = new Random().Next(1,10);)

Пример:

    int numberA = new Random().Next(1,10);//1,2,3,...9
    Console.WriteLine(numberA);
    int numberB = new Random().Next(1,10);
    Console.WriteLine(numberB);
    int result = numberA + numberB;
    Console.WriteLine(result);

## 3. Convert.ToInt32(Console.ReadLine())
Функция позволяет конвертировать введенную строку в числа.

Пример:

    Console.WriteLine("Введите целое число: ");
    int number = Convert.ToInt32(Console.ReadLine();
    
## 4. ToString()
Функция позволяет привести числа к строке.

Пример:

    int number = GetRandomNumber(10, 100);
    Console.WriteLine("Number: " + number);
    string str = number.ToString();
    int result = Convert.ToInt32(str[0].ToString());//Записываю первую цифру числа
    for (int i = 1; i < str.Length; i++)
    {
        if (result < Convert.ToInt32(str[i].ToString()))
        {
            result = Convert.ToInt32(str[i].ToString());
        }
     }
     Console.WriteLine("Result: " + result);
