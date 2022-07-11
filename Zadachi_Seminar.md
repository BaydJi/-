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
