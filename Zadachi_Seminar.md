# 1.
  
    Console.WriteLine("Введите целое число: ");
    int number1 = Convert.ToInt32(Console.ReadLine());
    Console.WriteLine("Введите 2е целое число: ");
    int number2 = Convert.ToInt32(Console.ReadLine());
    int dubl = number2 * number2;
    if (number1 == dubl)
    {
        Console.WriteLine($"Число {number1} является квадратом {number2}");
    }
    else
    {
        Console.WriteLine($"Число {number1} не является квадратом {number2}");
    }

    //Напишите программу, которая на вход принимает два числа и проверяет, является ли первое число квадратом второго
  
# 2.
  
    // Console.WriteLine("Введите целое трехзначное число: ");
    // double N = Convert.ToInt32(Console.ReadLine()); 
    // double remains = N % 10; 
    // Console.WriteLine($"Последняя цифра: {remains} ");

    // Console.WriteLine("Введите целое трехзначное число: ");
    // string str = Console.ReadLine();
    // Console.WriteLine(str[str.Length - 1]);

    Console.WriteLine("Введите целое трехзначное число: ");
    Console.WriteLine(Convert.ToInt32(Console.ReadLine()) % 10); 

    // Console.WriteLine(Console.ReadLine().ToString().ToCharArray().LastOrDefault()); 
    // string? -> string -> char[]
    // LastOrDefault - последний или дефолтный элемент
  
# 3.

    namespace Helloworld // namespace показывает территорию где мы находимся, логическое структурирование
    {
    // Напишите программу, которая выводит случайное число из отрезка [10,99] и показывает наибольшую цифру числа.
    // 78 -> 8
    // 186 -> 8
        class Program // class единица, подпрограмка, выполняющая одну функцию
        {
            public static void Main(string[] args)
            {
                // Вызов метода и получение результата от метода
                int number = GetRandomNumber(10, 100);
                Console.WriteLine("Number: " + number);
                string str = number.ToString(); // Приведение number к строке (string)
                int result = Convert.ToInt32(str[0].ToString());//Записываю первую цифру числа
                for (int i = 1; i < str.Length; i++)
                {
                    if (result < Convert.ToInt32(str[i].ToString()))
                    {
                    result = Convert.ToInt32(str[i].ToString());
                    }
                }
                Console.WriteLine("Result: " + result);
            }

            //Объявляем функцию(метод)
            //<тип данных возвращаемого значения> <имя функции> (<параметры>)
            public static int GetRandomNumber(int first, int second)
            {
                int number = new Random().Next(first, second);// Получаем случайное число от first включительно до second не включительно
                return number;//Возвращаем значение
            } 
        }
    }
  
# 4.

    // Программа, которая выводит случайное трехзначное число и удаляет вторую цифру этого числа

      namespace Helloworld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int number = GetRandomNumber(100, 1000);
                  Console.WriteLine("Number: " + number);
                  string str = number.ToString();
                  int result = int.Parse(str.Remove(str.Length -2, 1));
                  Console.WriteLine("Result: " + result);
              }

              public static int GetRandomNumber(int first, int second)
              {
                  int number = new Random().Next(first, second);// Получаем случайное число от first включительно до second не включительно
                  return number;//Возвращаем значение
              } 

          }
      }
  
# 5.

    // Напиишите программу, которая принимает на вход трехзначное число и на выходе показывает вторую цифру этого числа.
    // Решение через рандом без учета отрицательных чисел.

      namespace Helloworld 
      {

          class Program
          {
              public static void Main(string[] args)
              {
                  int number = GetRandomNumber(100, 1000);
                  Console.WriteLine("Number: " + number);
                  string str = number.ToString(); 
                  int result = Convert.ToInt32(str[1].ToString());

                  Console.WriteLine("Result: " + result);
              }
              public static int GetRandomNumber(int first, int second)
              {
                  int number = new Random().Next(first, second);
                  return number;
              } 
          }
      }
  
# 6.

      // Напишите программу, которая выводит третью цифру заданного числа или сообщает, что третьей цифры нет.
      // Не рандом, с учетом отрицательных.

      Console.WriteLine("Введите число: ");
      int number = Convert.ToInt32(Console.ReadLine());
      if (number < 0)
      {
          string str = number.ToString();
          if (str.Length > 3)
          {
              int result = Convert.ToInt32(str[3].ToString());
              Console.WriteLine("Третья цифра: " + result);
          }
          else
          {
              Console.WriteLine("Третьей цифры нет");
          }
      }    
      if (number > 0) 
      {
          string str = number.ToString();
          if (str.Length > 2)
          {
              int result = Convert.ToInt32(str[2].ToString());
              Console.WriteLine("Третья цифра: " + result);
          }
          else
          {
              Console.WriteLine("Третьей цифры нет");
          }
      }
  
# 7.

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
                  {
                      Console.WriteLine("Введите числа через пробел");
                      string str = Console.ReadLine();
                      string[] nums = str.Split(' '); // split получение из строки массива по определенному разделителю
                      for (int i = 0; i < nums.Length; i++) // Перебор массива строк с помощью цикла
                      {
                          Console.WriteLine(nums[i] + " ");
                      }
                  }
          }
      }
  
# 8.

      // Напишите программу, которая по заданному номеру четверти, показывает диапазон
      // возможных координат точек в этой четверти (x, y).

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  try
                  {
                      Console.Write("Введите номер четверти от 1 до 4: ");
                      int num = Convert.ToInt32(Console.ReadLine());
                      int max = int.MaxValue;
                      int min = int.MinValue;
                      if (num == 1) Console.WriteLine($"Диапозон X равен от 1 до {max}, диапозон Y равен от 1 до {max}");
                      if (num == 2) Console.WriteLine($"Диапозон X равен от -1 до {min}, диапозон Y равен от 1 до {max}");
                      if (num == 3) Console.WriteLine($"Диапозон X равен от -1 до {min}, диапозон Y равен от -1 до {min}");
                      if (num == 4) Console.WriteLine($"Диапозон X равен от 1 до {max}, диапозон Y равен от -1 до {min}");
                      else Console.WriteLine("Диапозона не существует");
                  Console.ReadKey();
                  }
                  catch 
                  {
                      Console.WriteLine("Не удовлетворяет условию");
                  }    
              }
          }
      }
  
# 9.

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int a = Convert.ToInt32(Console.ReadLine()); // Читаем число с консоли
                  int[] squares = GetSquare(a); // Получаем резкльтат функции GetSquare

                  for (int i = 0; i < squares.Length; i++) // Перебор массива с помощью цикла
                  {
                      Console.WriteLine( squares[i] + " "); // вывод чисел в консоль
                  }
              }

              public static int[] GetSquare(int n) // Объявляем функцию GetSquare
              {
                  int[] square = new int[n]; // Создание массива с размерностью n
                  for (int i = 1; i <= n; i++) // Объявление цикла от 1 до n включительно
                  {
                      square[i - 1] = i * i; // Запись в i - 1 элемент массива (по индексу) квадрата числа I           
                  }
                  return square;// Возвращение массива
              }
          }
      }
  
 # 10.
 
      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int a = Convert.ToInt32(Console.ReadLine());

                  for (int i = 1; i <= a; i++)
                  {
                      PrintSquare(i);
                  }
              }

              public static void PrintSquare(int n)
              {
                  Console.WriteLine(n * n);
              }
          }
      }
  
# 11.

      // Напишите программу, которая принимает на вход пятизначное число и проверяет, является ли оно палиндромом.
      // 14212 -> нет
      // 12821 -> да
      // 23432 -> да

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  try
                  {
                      Console.Write("Введите 5ти значное число: ");
                      int num = Convert.ToInt32(Console.ReadLine());
                      string str = num.ToString();
                      char[] strReverse = str.ToCharArray();
                      Array.Reverse(strReverse);
                      string str1 = new string(strReverse);
                      if (str.Length < 6 && str.Length > 4)
                      {
                          if (str == str1) Console.WriteLine("Число является палиндромом");
                          else Console.WriteLine("Число не является палиндромом");
                      }
                      else Console.WriteLine("Число не удовлетворяет условию");
                  }
                  catch 
                  {
                      Console.WriteLine("Не удовлетворяет условию");
                  }    
              }
          }
      }
  
# 12.

    // Написать программу нахождения N!

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  Console.Write("Введите число: ");
                  int N = Convert.ToInt32(Console.ReadLine());
                  int i = 1;
                  int result = 1;
                  while (i <= N)
                  {
                      result = result * i;
                      i++;
                  }
                  Console.WriteLine(result);

              }
          }
      }
  
# 13.

    // Напишите программу, которая выводит массив из 8 элементов, заполненный нулями и единицами в случайном порядке.

      namespace HelloWorld
      {
          class Program
          {
              static void Main()
              {
                  int[] arr;
                  FillArray(out arr);
                  PrintArray(arr);

              }

              static void FillArray(out int[] arr)
              {
                  arr = new int[8];
                  for (int i = 0; i < 8; i++)
                  {
                      arr[i] = new Random().Next(0, 2);
                  }
              }

              static void PrintArray(int[] arr)
              {
                  for (int i = 0; i < arr.Length; i++)
                  {
                      Console.Write(arr[i] + " ");
                  }
                  Console.WriteLine();
              }
          }
      }
  
# 14.

    // Напишите цикл, который принимает на вход два числа (A и B) и возводит число A в натуральную степень B.

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  Console.Write("Введите первое число: ");
                  int a = Convert.ToInt32(Console.ReadLine());
                  Console.Write("Введите второе число: ");
                  int b = Convert.ToInt32(Console.ReadLine());
                  double c = Math.Pow(a, b);
                  Console.WriteLine("Ответ: " + c);
              }
          }
      }
  
# 15.

      // Напишите программу, которая принимает на вход число и выдаёт сумму цифр в числе.

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] array)
              {
                  try
                  {
                      Console.Write("Введите число: ");
                      int number = Convert.ToInt32(Console.ReadLine());
                      string str = number.ToString();
                      int sum = 0;

                      if (number > 0)
                      {
                          for (int i = 0; i < str.Length; i++)
                          {
                              sum = sum + Convert.ToInt32(str[i].ToString());;
                          }
                          Console.WriteLine("Сумма цифр = " + sum);
                      }

                      else
                      {
                          for (int i = 1; i < str.Length; i++)
                          {
                              sum = sum + Convert.ToInt32(str[i].ToString());;
                          }
                          Console.WriteLine("Сумма цифр = " + sum); 
                      }
                  }

                  catch 
                  {
                      Console.WriteLine("Значение не удовлетворяет условию");    
                  }
              }
          }
      }
  
# 16.

      // Напишите программу, которая задаёт случайный массив случайного размера (от 5 до 10) элементов (значение элементов от 1 до 40) 
      // и выводит на экран массив квадратов этих чисел. 
      // 1, 2, 5, 7, 19 -> [2, 4, 25, 49, 361]
      // 6, 1, 33 -> [36, 1, 1089] 

      namespace ConsoleApplication1
      {
          class Program
          {
              static void Main(string[] args)
              {
                  int[] arr;
                  FillArray(out arr);
                  PrintArray(arr);
                  GetScuare(arr);
              }

              static void FillArray(out int[] arr)
              {
                  Random rand = new Random((int)DateTime.Now.Ticks);
                  arr = new int[rand.Next(5, 10)];
                  for (int i = 0; i < arr.Length; i++)
                  {
                      arr[i] = rand.Next(1, 40);
                  }
              }

              static void PrintArray(int[] arr)
              {
                  for (int i = 0; i < arr.Length; i++)
                  {
                      Console.Write(arr[i] + " ");
                  }
                  Console.WriteLine();
              }

              static void GetScuare(int[] arr)
              {

                  for(int i = 0; i < arr.Length; i++)
                  {
                     Console.Write(arr[i] * arr[i] + " "); 
                  }
              }
          }
      }
  
# 17.

      // Задайте массив заполненный случайными положительными трёхзначными числами. 
      // Напишите программу, которая покажет количество чётных чисел в массиве.
      // [345, 897, 568, 234] -> 2

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int[] arr;
                  FillArray(out arr);
                  PrintArray(arr);
                  EvenNumber(arr);
              }

              public static void FillArray(out int[] arr)
              {
                  Random rand = new Random((int)DateTime.Now.Ticks);
                  arr = new int[rand.Next(1, 10)];
                  for(int i = 0; i < arr.Length; i++)
                  {
                      arr[i] = rand.Next(100, 1000);
                  }

              }

              public static void PrintArray(int[] arr)
              {
                  for (int i = 0; i < arr.Length; i++)
                  {
                      Console.Write(arr[i] + " ");
                  }
                  Console.WriteLine();
              }

              public static void EvenNumber(int[] arr)
              {
                  int Result = 0;
                  for (int i = 0; i < arr.Length; i++)
                  {
                      if (arr[i] % 2 == 0)
                      {
                          Result = Result + 1;
                      }
                  }
                  Console.WriteLine("Количество четных чисел: " + Result);
              }
          }
      }
  
# 18.

      // Задайте одномерный массив, заполненный случайными числами. Найдите сумму элементов, стоящих на нечётных позициях.
      // [3, 7, 23, 12] -> 19
      // [-4, -6, 89, 6] -> 0

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int[] arr;
                  FillArray(out arr);
                  PrintArray(arr);
                  Sum(arr);
              }

              public static void FillArray(out int[] arr)
              {
                  Random rand = new Random((int)DateTime.Now.Ticks);
                  arr = new int[rand.Next(5, 15)];
                  for(int i = 0; i < arr.Length; i++)
                  {
                      arr[i] = rand.Next(1, 100);
                  }
              }

              public static void PrintArray(int[] arr)
              {  
                  for(int i = 0; i < arr.Length; i++)
                  {
                      Console.Write(arr[i] + " ");
                  }
                  Console.WriteLine();
              }

              public static void Sum(int[] arr)
              {
                  int sum = 0;
                  for(int i = 1; i < arr.Length; i = i + 2)
                  {
                  sum = sum + arr[i];
                  }
                  Console.WriteLine("Сумма: " +sum);
              }
          }
      }
  
# 19.

      // Задайте массив вещественных чисел. Найдите разницу между максимальным и минимальным элементов массива.
      // [3 7 22 2 78] -> 76

      namespace HelloWorld
      {
          class Program
          {
              public static void Main(string[] args)
              {
                  int[] arr;
                  FillArray(out arr);
                  PrintArray(arr);
                  Diff(arr);
              }

              public static void FillArray(out int[] arr)
              {
                  Random rand = new Random();
                  arr = new int[rand.Next(5, 10)];
                  for (int i = 0; i < arr.Length; i++)
                  {
                      arr[i] =  new Random().Next(1, 100);
                  }
              }


              public static void PrintArray(int[] arr)
              {
                  for (int i = 0; i < arr.Length; i++)
                  {
                      Console.Write(arr[i] + " ");
                  }
                  Console.WriteLine();
              }

              public static void Diff(int[] arr)
              {
                  int max = arr[0];
                  int min = arr[0];
                  int diff = 0;
                  for (int i = 1; i < arr.Length; i++)
                  {
                      if (max < arr[i]) max = arr[i];
                      if (min > arr[i]) min = arr[i];
                  }
                  diff = max - min;
                  Console.WriteLine("Разница: " + diff);
              }
          }
      }
      
  # 20.
  
    using Bag2;
    using Calc;

    namespace Bag1
    {
        internal class Program
        {
            static void Main()
            {
                Apple apple = new Apple();
                apple.weight = 100;
                apple.Name = "";
                apple.Count = 1;

                string s1 = apple.Name;
                Console.WriteLine(s1);

                apple.Name = "abcabc";
                Console.WriteLine(apple.Name);

                apple.Print(10, 100);


                int sum = Calculation.Sum(5, 5);
                Console.WriteLine("5 + 5 = " + sum);
            }
        }

        public class Apple
        {
            # region Поля_и_свойства
            public int weight;

            // public string Name2 = "Apple";

            private string name = "Apple";

            public string Name
            {
                get // get - специальная функция, которя вызывается при обращении к свойству (string s = apple.Name)
                {
                    return name;
                }

                set // set - специальная функция, которая вызывается, когда пытаемся записать что-то в свойство (apple.Name = какое-то значение)
                {
                    if (IsValid(value))     // string.IsNullOrEmpty(value) - возвращает true, если value == null или value == ""
                    {                       // ! -- меняем true на false и false на true
                        name = value;       // value -- кодовое слово, которое определяет входящее значение (apple.Name = какое-то значение) -- value = какое-то значение
                    }
                }
            }

            private bool IsValid(string name)
            {
                return true;
            }

            public string AppleInfo
            {
                get
                {
                    return GetAppleInfo();
                }
            }

            public int Count { get; set; }

            private string color = "red";

            # endregion

            public void Print(int x, int y)
            {
                Console.WriteLine(GetAppleInfo());
            }

            private string GetAppleInfo()
            {
                return $"Яблоко с названием {Name}, цветом {color}, весом {weight} и колличеством {Count}";
            }
        }

    }
    
    
    namespace Bag2
    {
        public class Banana
        {
            # region Поля_и_свойства
            public int weight = 20;

            private string name = "Banana";

            public string Name
            {
                get 
                {
                    return name;
                }

                set 
                {
                    if (string.IsNullOrEmpty(value))  // string.IsNullOrEmpty(value) - возвращает true, если value == null или value == ""
                    {                       
                        name = value;   
                    }
                }
            }

            public int Count { get; set; }

            private string color = "yellow";

            # endregion

            public void Print()
            {
                Console.WriteLine(GetBananInfo());
            }

            private string GetBananInfo()
            {
            return $"Яблоко с названием {Name}, цветом {color}, весом {weight} и колличеством {Count}";
            }
        }
    }
    
    
    namespace Calc
    {
        public static class Calculation
        {
            public static int Sum(int x, int y)
            {
                return x + y;
            }
        }
    }
    
# 21.

    // Напишите программу замены элеиентов массива: положительные на отрицательные и наоборот.
    // [-4, -8, 8, 2] -> [4, 8, -8, -2]

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int[] arr;
                FillArray(out arr);
                PrintArray(arr);
                Transformation(arr);
            }

            public static void FillArray(out int[] arr)
            {
                Random rand = new Random();
                arr = new int[rand.Next(5, 11)];
                for (int i = 0; i < arr.Length; i++)
                {
                    arr[i] = new Random().Next(-20, 21);
                }
            }

            public static void PrintArray(int[] arr)
            {
                for (int i = 0; i < arr.Length; i++)
                {
                    Console.Write(arr[i] + " ");
                }
                Console.WriteLine();
            }

            public static void Transformation(int[] arr)
            {
                for (int i = 0; i < arr.Length; i++)
                {
                    if (arr[i] > 0) arr[i] = arr[i] * -1;
                    else arr[i] = arr[i] * -1;
                    Console.Write(arr[i] + " ");
                }

            }
        }
    }
    
# 22.

    // Задайте массив. Напишите программу, которая определяет присутсвует ли заданное число в массиве.


    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                Console.Write("Введите целое число: ");
                int N = Convert.ToInt32(Console.ReadLine());
                int[] arr;
                FillArray(out arr);
                PrintArray(arr);
                // Result(arr);
                if (Valid(arr, N)) Console.WriteLine($"Число {N} присутствует");
                else Console.WriteLine($"Число {N} отсутствует");
            }

            public static bool Valid(int[] arr, int c)
            {
                bool N = false;
                for (int i = 0; i < arr.Length; i++)
                {
                    if (c == arr[i]) N = true;
                }
                return N;
            }

            public static void FillArray(out int[] arr)
            {
                Random rand = new Random();
                arr = new int[rand.Next(5, 11)];
                for (int i = 0; i < arr.Length; i++) arr[i] = rand.Next(-20, 20);
            }

            public static void PrintArray(int[] arr)
            {
                for (int i = 0; i < arr.Length; i++) Console.Write(arr[i] + " ");
                Console.WriteLine();
            }
        }
    }
    
# 23.

    // Напишите программу, которая перевернет одномерный массив(последний элемент будет первым и наоборот)
    // [1 2 3 4] -> [4 3 2 1]

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int[] arr;
                FillArray(out arr);
                PrintArray(arr);
                Console.WriteLine();
                Reverse(arr);
            }

            public static void FillArray(out int[] arr)
            {
                Random rand = new Random();
                arr = new int[rand.Next(3, 6)];
                for (int i = 0; i < arr.Length; i++)
                {
                    arr[i] = new Random().Next(0, 11);
                }
            }

            public static void PrintArray(int[] arr)
            {
                for (int i = 0; i < arr.Length; i++)
                {
                    Console.Write(arr[i] + " ");
                }
            }

            public static void Reverse(int[] arr)
            {
                int[] arr1 = Enumerable.Reverse(arr).ToArray();
                for (int i = 0; i < arr.Length; i++)
                {
                    Console.Write(arr1[i] + " ");
                }
            }
        }
    }
    
# 24.

    // Пользователь вводит с клавиатуры M чисел. Посчитайте, сколько чисел больше 0 ввёл пользователь.
    // 0, 7, 8, -2, -2 -> 2
    // 1, -7, 567, 89, 223-> 3

    namespace HelloWorld
    {
        class Program
        {

            public static void Main()
            {
                try{
                Console.Write("Enter the numbers separated by a space: ");
                int[] arr = Array.ConvertAll(Console.ReadLine().Split(" "), int.Parse);
                int count = 0;
                for (int i = 0; i < arr.Length; i++)
                {
                    if (arr[i] > 0) count++;
                }
                Console.WriteLine(count);
                }

                catch {Console.WriteLine("Oooopps, enter the numbers please!");}
            }
        }
    }
    
# 25.

    // Напишите программу, которая найдёт точку пересечения двух прямых, заданных уравнениями y = k1 * x + b1, y = k2 * x + b2; 
    // значения b1, k1, b2 и k2 задаются пользователем.
    // b1 = 2, k1 = 5, b2 = 4, k2 = 9 -> (-0,5; -0,5)

    // Приравниваем правые части данных равенств: k1*x+b1=k2*x+b2
    // x=(b2-b1)/(k1-k2)
    // y=k1(b2-b1)/(k1-k2)+b1


    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                Console.Write("Введите координату b1: ");
                double b1 = Convert.ToInt32(Console.ReadLine());
                Console.Write("Введите координату k1: ");
                double k1 = Convert.ToInt32(Console.ReadLine());
                Console.Write("Введите координату b2: ");
                double b2 = Convert.ToInt32(Console.ReadLine());
                Console.Write("Введите координату k2: ");
                double k2 = Convert.ToInt32(Console.ReadLine());

                // double x = (b2 - b1) / (k1 - k2);
                // double y = ((k1 * (b2 -b1)) / ((k1 - k1) + b1));

                double x = -(b1 - b2) / (k1 - k2);
                double y = k1 * x + b1;

                x = Math.Round(x, 3);
                y = Math.Round(y, 3);

                Console.WriteLine($"Точка пересечения: {x}, {y}");
            }
        }
    }
    
# 26.

    // Сумма элементов главной диагонали
    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int rows = 8;
                int columns = 5;
                int[,] massiv = new int[rows, columns];
                FillArray(massiv);
                PrintArray(massiv);
                Sum(massiv);
            }

            public static void FillArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 11);
                    }
                }
                return;
            }

            public static void PrintArray(int[,] massiv)
            {
                Console.WriteLine("Массив:");
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();
                }
                return;
            }

            public static void Sum(int[,] massiv)
            {
                int sum = 0;
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        if (i == j) sum += massiv[i, j];
                    }
                }
                Console.WriteLine("Сумма по диагонали: " + sum);
                return;
            }
        }
    }

# 27.

    // Задайте двумерный массив m на n, каждый элемент в массиве находится по формуле A(m,n) = m + n

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int m = new Random().Next(0, 5);
                int n = new Random().Next(0, 5);
                int[,] massiv = new int[m, n];
                FillArray(massiv);
                PrintArray(massiv);
            }

            public static void FillArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = i + j;
                    }  
                }
            }

            public static void PrintArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();
                }
            }
        }
    }
    
 # 28.
 
    // Задайте двумерный массив размером m×n, заполненный случайными вещественными числами.
    // m = 3, n = 4.
    // 0,5 7 -2 -0,2
    // 1 -3,3 8 -9,9
    // 8 7,8 -7,1 9

    namespace KakVsegda
    {
        class Program
        {
            public static void Main()
            {
                double[,] massiv = new double[3, 4];
                FillArray(massiv);
                PrintArray(massiv);
            }

            public static void FillArray(double[,] massiv)
            {
                double minRange = -10;
                double maxRange = 10;
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().NextDouble() * (maxRange - minRange) + minRange;
                    }
                }
            }

            public static void PrintArray(double[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(Math.Round(massiv[i, j], 2) + " ");
                    }
                    Console.WriteLine();
                }
            }
        }
    }
    
# 29.

    // Напишите программу, которая на вход принимает позиции элемента в двумерном массиве, и возвращает значение этого элемента 
    // или же указание, что такого элемента нет.
    // Например, задан массив:
    // 1 4 7 2
    // 5 9 2 3
    // 8 4 2 4
    // 17 -> такого числа в массиве нет

    namespace NuVotOpyat
    {
        class Program
        {
            public static void Main()
            {
                Console.Write("Введите номер строки: ");
                int length = Convert.ToInt32(Console.ReadLine()) - 1;
                Console.Write("Введите номер столбца: ");
                int column = Convert.ToInt32(Console.ReadLine()) - 1;
                int a = new Random().Next(5, 11);
                int b = new Random().Next(1, 20);
                int[,] massiv = new int[a, b];
                FillArray(massiv);
                PrintArray(massiv);
                CheckValue(massiv);
            }

            public static void FillArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 100);
                    }
                }
            }

            public static void PrintArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();
                }
            }

            public static void CheckValue(int[,] massiv)
            {
                if (length < 0 | length > massiv.GetLength(0) - 1 | column < 0 | column > massiv.GetLength(1) - 1)
                {
                    Console.WriteLine("Такого элемента нет.");
                }

                else
                {
                    Console.WriteLine("Значение элемента: " + massiv[length, column]);
                }
            }
        }
    }
    
# 30.

    // Задайте двумерный массив из целых чисел. Найдите среднее арифметическое элементов в каждом столбце.
    // Например, задан массив:
    // 1 4 7 2
    // 5 9 2 3
    // 8 4 2 4
    // Среднее арифметическое каждого столбца: 4,6; 5,6; 3,6; 3.

    namespace NuVotOpyat
    {
        public class Program
        {
            /// <summary>Основной метод программы</summary>
            static void Main()
            {

                int[,] massiv = new int[5, 5];
                FillArray(massiv);
                PrintArray(massiv);
                Average(massiv);
            }

            public static void FillArray(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 21);
                    }
                }
                return;
            }

            public static void PrintArray(int[,] massiv)
            {
                Console.WriteLine("Massiv: ");
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();
                }
                return;
            }

            public static void Average(int[,] massiv)
            {
                Console.WriteLine("Average: ");
                for (int i = 0; i < massiv.GetLength(1); i++)
                {
                    double sum = 0;
                    for (int j = 0; j < massiv.GetLength(0); j++)
                    {
                        sum += massiv[j, i];
                    }
                    sum = sum / massiv.GetLength(0);

                    Console.Write(Math.Round(sum, 1) + " ");
                }
                return;
            }
        }
    }
    
# 31.

    // Задайте двумерный массив. Транспонируйте матрицу, если нет возможности, вывести сообщение что сделать нельзя

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int rows = new Random().Next(1, 5);
                int colums = new Random().Next(2, 5);
                int[,] massiv = new int[rows, colums];
                Console.WriteLine("Массив:");
                FillMassiv(massiv);
                PrintMassiv(massiv);
                Console.WriteLine();
                TranspMassiv(massiv);
            }

            public static void FillMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 10);
                    }
                }
            }

            public static void PrintMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();
                }
            }

            public static void TranspMassiv(int[,] massiv)
            {
                int[,] massivTransp = new int[massiv.GetLength(0), massiv.GetLength(1)];
                if (massiv.GetLength(0) == massiv.GetLength(1))
                {
                    Console.WriteLine("Транспорированный массив:");
                    for (int i = 0; i < massiv.GetLength(0); i++)
                    {
                        for (int j = 0; j < massiv.GetLength(1); j++)

                        {
                            massivTransp[i, j] = massiv[j, i];
                            Console.Write(massivTransp[i, j] + " ");
                        }
                        Console.WriteLine();
                    }
                }
                else Console.WriteLine("Невозможно транспорировать матрицу.");

            }
        }
    }
    
# 32.

    // Задайте двумерный массив. Напишите программу, которая упорядочит по возрастанию элементы каждой строки двумерного массива.
    // Например, задан массив:

    // 1 4 7 2
    // 5 9 2 3
    // 8 4 2 4

    // В итоге получается вот такой массив:

    // 1 2 4 7
    // 2 3 5 9
    // 2 4 4 8

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int rows = new Random().Next(2, 5);
                int colums = new Random().Next(2, 5);
                int[,] massiv = new int[rows, colums];
                Console.WriteLine("Массив:");
                FillMassiv(massiv);
                PrintMassiv(massiv);
                Console.WriteLine();
                Console.WriteLine("Упорядоченный массив: ");
                RegularMassiv(massiv);
                PrintMassiv(massiv);
            }

            public static void FillMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 10);
                    }
                }
            }

            public static void PrintMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();

                }
            }

            public static void RegularMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        for (int k = 0; k < massiv.GetLength(1) - 1; k++)
                        {
                            if (massiv[i, k] > massiv[i, k + 1])
                            {
                                int temp = massiv[i, k + 1];
                                massiv[i, k + 1] = massiv[i, k];
                                massiv[i, k] = temp;
                            }
                        }
                    }
                }
            }
        }
    }
    
# 33.

    // Задайте прямоугольный двумерный массив. Напишите программу, которая будет находить строку с наименьшей суммой элементов.
    // Например, задан массив:
    // 1 4 7 2
    // 5 9 2 3
    // 8 4 2 4
    // 5 2 6 7
    // Программа считает сумму элементов в каждой строке и выдаёт номер строки с наименьшей суммой элементов: 1 строка

    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int rows = 3;
                int colums = 3;
                int[,] massiv = new int[rows, colums];
                Console.WriteLine("Массив:");
                FillMassiv(massiv);
                PrintMassiv(massiv);
                Console.WriteLine();

                int SumLineElements(int[,] massiv, int i)
                {
                    int sumLine = massiv[i, 0];
                    for (int j = 1; j < massiv.GetLength(1); j++)
                    {
                        sumLine += massiv[i, j];
                    }
                    return sumLine;
                }

                int minSumLine = 0;
                int sumLine = SumLineElements(massiv, 0);
                for (int i = 1; i < massiv.GetLength(0); i++)
                {
                    int tempSumLine = SumLineElements(massiv, i);
                    if (sumLine > tempSumLine)
                    {
                        sumLine = tempSumLine;
                        minSumLine = i;
                    }
                }
                Console.WriteLine(minSumLine+1 + "-я строкa с наименьшей суммой элементов = " + sumLine);
            }

            public static void FillMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        massiv[i, j] = new Random().Next(0, 10);
                    }
                }
            }

            public static void PrintMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        Console.Write(massiv[i, j] + " ");
                    }
                    Console.WriteLine();

                }
            }

        }
    }
    
# 34.

    // Задача 62: Заполните спирально массив 4 на 4.
    // 1 2 3 4
    // 12 13 14 5
    // 11 16 15 6
    // 10 9 8 7
    namespace HelloWorld
    {
        class Program
        {
            public static void Main()
            {
                int n = 4;
                int[,] spiralMassiv = new int[n, n];

                int temp = 1;
                int i = 0;
                int j = 0;

                while (temp <= spiralMassiv.GetLength(0) * spiralMassiv.GetLength(1))
                {
                    spiralMassiv[i, j] = temp;
                    temp++;
                    if (i <= j + 1 && i + j < spiralMassiv.GetLength(1) - 1)
                        j++;
                    else if (i < j && i + j >= spiralMassiv.GetLength(0) - 1)
                        i++;
                    else if (i >= j && i + j > spiralMassiv.GetLength(1) - 1)
                        j--;
                    else
                        i--;
                }

                PrintMassiv(spiralMassiv);
            }

            public static void PrintMassiv(int[,] massiv)
            {
                for (int i = 0; i < massiv.GetLength(0); i++)
                {
                    for (int j = 0; j < massiv.GetLength(1); j++)
                    {
                        if (massiv[i, j] / 10 <= 0)
                            Console.Write($" {massiv[i, j]} ");

                        else Console.Write($"{massiv[i, j]} ");
                    }
                    Console.WriteLine();
                }
            }
        }
    }
