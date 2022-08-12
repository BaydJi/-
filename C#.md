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

# Алгоритмы:

## Константные алгоритмы.

Все постоянно, ничего не зависит друг от друга.

    int n = 2;
    if (n >= 0) n++;
    else n *= 2;
    
## Линейные алгоритмы.

Линейная зависимость: y = kx + b (функция зависит от х)

    int n = Convert.ToInt32(Console.ReadLine());
    int result = 0;
    for (int i = 1; i <= 0; i++)
        result *= i;
    Console.WriteLine(result);
    
Переменная **result** полностью зависит от переменной **i**.

## Логарифмические алгоритмы.

Пользователь загадал от 1 до 100 (например 67)
Нам нужно отгадать число за мин. кол-во ходов это число
Максимальное кол-во ходов мы знаем - 100.

    Существует алгоритм - **БИНАРНЫЙ ПОИСК(двоичный поиск)**
    Смысл: сложить левый конец с правым и разделить на 2.
    
    (100 + 1) / 2 = 51 - Спрашиваем у пользователя число больше 50 / да
    Число лежит от 50 до 100
    (50 + 100) / 2 = 75 - число больше 75? / нет 
    Число лежит от 50 до 75
    (50 + 75) / 2 = 62 - число больше 62? да
    Число лежит от 62 до 75
    И так далее.
    
    **(log2(n))**
    
## Квадратичные и кубические алгоритмы.

Цыкл в цыкле.

    int count = 0;
    for (i = 0; i < 5; i ++)
    {
        for (j = 0; j > 5; j++)
        {
            count++;
        }
    }
    
Так же и для кубического добаавляется еще один цыкл(двумерный и трехмерный массивы).

## Алгоритм Евклида.
Нахождение НОД(наибольшего общего делителя).
НОД(14, 21) = 7

    int n = 140;
    int m = 175;
    while (n != m)
    {
        if (n > m) n = n- m;
        else m = m - n;
    }
    
Нахождение НОК(наименьшее общее кратное)
НОК(a,b) = a*b/НОД(a,b)
    
    int n = 140;
    int m = 175;
    int c = n * m;
    while (n != m)
    {
        if (n > m) n = n- m;
        else m = m - n;
    }
    Console.WriteLine(c / n);
    
# Сложность алгоритма **Big O Nation** (О-натация)

О(1) - О от одного - колличество действий, чтобы узнать конечный результат. 


# Сортировки.

## Сортировака выбором.
Предпологаем что первый элемент это то что нам нужно и сравниваем его с последующими.
Время выполнения: O(n^2/4)
Память: O9(n+1)

    Console.WriteLine("Введите кол-во элементов массива:");
    int n = Convert.ToInt32(Console.ReadLine());
    // Заполнение массива
    int[] array = new int[n];
    for (int i = 0; i < n; i++)
    {
        Console.Write("Введите число: ");
        array[i] = Convert.ToInt32(Console.ReadLine());
    }
    Console.WriteLine();
    Console.WriteLine("Начальный массив: [" + string.Join(", ", array) + "]");
    // Cортировка
    for (int i = 0; i < n - 1; i++)
    {
        int MinIndex = i;
        for (int j = i + 1; j < n; j++)
        {
            if (array[j] < array[MinIndex])
                MinIndex = j; 
        }
        int temp;
        temp = array[MinIndex];
        array[MinIndex] = array[i];
        array[i] = temp;
    }
    Console.WriteLine("Конечный массив: [" + string.Join(", ", array) + "]");
    
## Сортировка пузырьком.
Проверка двух элементов идущих последовательно друг за другом(парные элементы). Если условие удовлетворяет, двигаемся дальше, если нет, меняем местами и начинаем заново.
Проходиться по массиву мы будем столько раз, сколько элементов в нем находится.
Время выполнения: O(n^2)
Память: O(n)

Cортировка пузырьком
Начальный массив: [3, 1, 5, 0, 7, 9, 8]

    Console.WriteLine("Введите кол-во элементов массива: ");
    int n = Convert.ToInt32(Console.ReadLine());
    int[] array = new int[n];
    for (int i = 0; i < n; i++)
    {
        Console.Write("Введите значения массива: ");
        array[i] = Convert.ToInt32(Console.ReadLine());
    }
    Console.WriteLine("Начальный массив: [" + string.Join(", ", array) + "]");
    Console.WriteLine();
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n - 1; j++)
        {
            if (array[j] > array[j + 1])
            {
                int temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
        Console.WriteLine(i + "[" + string.Join(", ", array) + "]");
    }
    
## Быстрая сортировка.
Время выполнения: O(n * log n)
Память: O(n)

    int[] arr = { 0, -5, 2, 3, 5, 9, -1, 7 };
    QuickSort(arr, 0, arr.Length - 1);
    Console.Write($"Отсортированный массив {string.Join(", ", arr)}");

    static void QuickSort(int[] inputArray, int minIndex, int maxIndex)
    {
        if (minIndex >= maxIndex) return;
        int pivot = GetPivotIndex(inputArray, minIndex, maxIndex);
        QuickSort(inputArray, minIndex, pivot - 1);
        QuickSort(inputArray, pivot + 1, maxIndex);
        return;
    }
    static int GetPivotIndex(int[] inputArray, int minIndex, int maxIndex)
    {
        int pivotIndex = minIndex - 1;
        for (int i = minIndex; i <= maxIndex; i++)
        {
            if (inputArray[i] < inputArray[maxIndex])
            {
                pivotIndex++;
                Swap(inputArray, i, pivotIndex);
            }
        }
        pivotIndex++;
        Swap(inputArray, pivotIndex, maxIndex);
        return pivotIndex;
    }
    static void Swap(int[] inputArray, int leftValue, int rightValue)
    {
        int temp = inputArray[leftValue];
        inputArray[leftValue] = inputArray[rightValue];
        inputArray[rightValue] = temp;
    }
    
## Сортировка подсчетом.
По умолчанию она работает только с цифрами.

    int[] array = {-10, -5, -9, 0, 2, 5, 1, 3, 1, 0, 1};
    int[] sortedArray = CountingSortExtended(array);

    CountingSort(array);

    Console.WriteLine(string.Join(", ", array));

    void CountingSort(int[] inputArray)
    {
        int[] counters = new int[10]; //массив повторений

        for (int i = 0; i < inputArray.Length; i++)
        {
            counters[inputArray[i]]++;
            // ourNumber = inputArray[i];
            // counters[ourNumber]++;
        }

        int index = 0;
        for (int i = 0; i < counters.Length; i++)
        {
            for (int j = 0; j < counters[i]; j++)
            {
                inputArray[index] = i;
                index++;
            }
        }
    }
    
Код для подсчета чисел:

int[] array = {-10, -5, -9, 0, 2, 5, 1, 3, 1, 0, 1};
int[] sortedArray = CountingSortExtended(array);

Console.WriteLine(string.Join(", ", sortedArray));

int[] CountingSortExtended(int[] inputArray)
{
    int max = inputArray.Max();
    int min = inputArray.Min();

    int offset = -min;
    int[] sortedArray = new int[inputArray.Length];
    int[] counters = new int[max + offset + 1];



    for (int i = 0; i < inputArray.Length; i++)
    {
        counters[inputArray[i] + offset]++;
    }

    int index = 0;
    for (int i = 0; i < counters.Length; i++)
    {
        for (int j = 0; j < counters[i]; j++)
        {
            sortedArray[index] = i - offset;
            index++;
        }
    }

    return sortedArray;
}

    

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
    
## 11. "/t"
Форматированный вывод в консоль.

    Console.WriteLine("/t");
    
## 12. Join
Функция Join позволяет соединить каэждый элемент массива через указанный разделитель.
Указываем в каком формате и какие элементы мы соединяем.

    Console.WriteLine("Конечный массив: [" + string.Join(", ", array) + "]");
    

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
    
# List

    namespace GB
    {
        class Program
        {
            /// <summary>Основной метод Main</summary>
            static void Main(string[] args)
            {
                int[] a = new int[5] { 1, 2, 3, 4, 5 };
                // int[,] b = new int[5, 2] { {1, 2, 3, 4, 5} {1, 2, 3, 4, 5} };
                List<int> list = new List<int>();
                FillList(list, 5);

                List<Point> program = new List<Point>();
                Point[] programList = new Point[5];
                // list.Add(6);  // С помощью Add можно добавить доп. значения 
                // list.Add(7);
                // list.Add(10);

                list.Remove(5);   // Удалим число 5
                list.RemoveAt(4); // Удалим значение с индексом 4

                // list.AddRange(a);

                foreach (int number in list) // Удобней этим циклом выводить массив. Но в нем нельзя ничего изменить.
                {
                    Console.WriteLine(number);
                }

                // for (int i = 0; i < list.Count; i++)
                // {
                //     Console.WriteLine(list[i] + " ");
                // }

                int num = list.Find(x => x % 2 == 0); // Лямбда выражение или стрелочная функция

                // foreach (int x in list)  // Верхний вариант взамен этого цикла
                // {
                //     if (x % 2 == 0)
                //     {
                //         num = x;
                //         break;
                //     }
                // }

                Console.WriteLine(num);

            }

            /// <summary>Заполнение коллекции List<int> случайными числами от 0 до 10</summary>
            /// <param name="list">List<int> Для заполнения значениями</param>
            /// <param name="count">Количество случайных значений</param>
            public static void FillList(List<int> list, int count)
            {
                for (int i = 0; i < count; i++)
                {
                    list.Add(new Random().Next(0, 11));
                }
            }
        }

        public class Point
        {
            int x;
            int y;
        }
    }
