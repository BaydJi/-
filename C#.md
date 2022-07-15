# C#
Через *Console* мы обращаемся к системному терминалу.

    namespace Bag1 // namespace - специальный контейнер, который позволяет организовать код программы в логические блоки,
                   // позволяет объеденить и отелить от остального кода некоторую функуиональность,
                   // которая связана некоторой общей идеей или которая выполняет определенную задачу.
    {
        internal class Program // internal - компоненты класса или структуры, доступен из любого места кода в той же сборке,
                               // однако он недоступен для других программ и сборок.
        {

        }

        public class Apple // public - публичный, общедоступный компонент класса или структуры.
                           // Такой компонент доступен из любого места в коде, а так же из других программ в сборке
        {
                private class Apple1 // private - закрытый или приватный компонент класса или структуры.
                                     // Приватный компонент доступен только в рамках своего класса или структуры.
                {

                }
        } 

    }

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
    
## 8. Random()
Функция позволяет получить рандомные значения.

Пример:

    int what = new Random().Next(0, 3);//[0;3) 0 1 2
    
## 9. Break
Функция позволяет прервать алгоритм после получения нужного результата.

Пример:

    while (index < n)  
    {
        if (array[index] == find)
        {
            Console.WriteLine(index);
            break;//Прерывание алгоритма
        }
        index++;
    }
    
## 10. Replace
Функция позволяет заменить старый элемент на новый элемент.

Пример:

    string Replace(string text, char oldValue, char newValue)
    {
        string result = string.Empty;

        int length = text.Length;
        for (int i = 0; i < length; i++)
        {
            if (text[i] == oldValue) 
            result = result + $"{newValue}";
            else 
            result = result + $"{text[i]}";
        }
        return result;
    }

    string newText = Replace(text, ' ', '|');
    Console.WriteLine(newText);
    

# Виды методов

## Вид 1
Метод, который ничего не возвращает и ничего не принимает

    void Method1()
    {
        Console.WriteLine("");

    }
    Method1();

## Вид 2
Метод, который принимает аргумены, но ичего не возвращает

    void Method2(string msg, int count)
    {
        int i = 0;
        while (i < count)
        {
            Console.WriteLine(msg);
            i++;
        }
    }
    Method2(msg: "Текст сообщения", count: 4);

## Вид 3
Метод, который что то возвращает, но ничего не принимает

    int Method3()
    {
        return DateTime.Now.Year;
    }

    int year = Method3();
    Console.WriteLine(year);

## Вид 4 
Метод, который что то принимает и что то возвращает

    string Method4(int count, string text)
    {
        int i = 0;
        string result = string.Empty; // string.Empty - пустая строка
        while (i < count)
        {
            result = result + text;
            i++;
        } 
        return result;
    }

    string res = Method4(10, "asdf");
    
# Необработанное исключение.

    // Unhandled exceptions - необработанное исключение
    // Можно обрабатывать несколько исключений сразу


    namespace GB
    {
        class Program
        {
            public static void Main()
            {
                try
                {
                    Console.WriteLine("Введите число");
                    string? str = Console.ReadLine();
                    int num = Convert.ToInt32(str);
                    // num = num / 0;
                }

                catch (FormatException) //FormatException - неверный формат данных
                {
                    Console.WriteLine("Неверные данные");
                    // Main(); // Рекурсия, если будет введено не число, main будет перевызываться 
                }

                catch (DivideByZeroException) // Ошибка деления на ноль
                {
                     Console.WriteLine("Делить на ноль нельзя");
                }
                finally
                {
                    Console.WriteLine("finally");
                }
            }
        }

    }
