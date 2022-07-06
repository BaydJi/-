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

## 5. Parse
Функция позволяет удалить значение в нужном индексе.

Пример:

    int number = GetRandomNumber(100, 1000);
    Console.WriteLine("Number: " + number);
    string str = number.ToString();
    int result = int.Parse(str.Remove(str.Length -2, 1));
    Console.WriteLine("Result: " + result);
    
## 6. Split
Функция позволяет в консоли вводи значения через определенный разделитель.

Пример:

    Console.WriteLine("Введите числа через пробел");
    string str = Console.ReadLine();
    string[] nums = str.Split(' '); // split получение из строки массива по определенному разделителю
    for (int i = 0; i < nums.Length; i++) // Перебор массива строк с помощью цикла
    {
        Console.WriteLine(nums[i] + " ");
    }
    
## 7. GetSquare
Функция возводит значение в квадрат.

Пример:

    int a = Convert.ToInt32(Console.ReadLine()); // Читаем число с консоли
    int[] squares = GetSquare(a); // Получаем резкльтат функции GetSquare

    for (int i = 0; i < squares.Length; i++) // Перебор массива с помощью цикла
    {
        Console.WriteLine( squares[i] + " "); // вывод чисел в консоль
    }
    
