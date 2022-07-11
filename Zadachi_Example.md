# 1.

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
    
# 2.

    int xa = 1, ya = 1,
    xb = 1, yb = 30,
    xc = 60, yc = 30;

    Console.SetCursorPosition(xa, ya);
    Console.WriteLine("+");

    Console.SetCursorPosition(xb, yb);
    Console.WriteLine("+");

    Console.SetCursorPosition(xc, yc);
    Console.WriteLine("+");

    int x = xa, y = xb;

    int count = 0;

    while(count<100)
    {
        int what = new Random().Next(0, 3);//[0;3) 0 1 2
        if(what == 0)
        {
            x = (x + xa) / 2;
            y = (y + ya) / 2;
        }

        if(what == 1)
        {
            x = (x + xb) / 2;
            y = (y + yb) /2;
        }

        if(what == 2)
        {
            x = (x + xc) / 2;
            y = (y + yc) / 2;
        }

        Console.SetCursorPosition(x, y);
        Console.WriteLine("+");
        count = count + 1; 
    } 
    
# 3.

    int Max(int arg1, int arg2, int arg3)
    {
        int result = arg1;
        if (arg2 > result) result = arg2;
        if (arg3 > result) result = arg3;
        return result;
    }

    int a1 = 15;
    int b1 = 16;
    int c1 = 43;
    int a2 = 151;
    int b2 = 164;
    int c2 = 31;
    int a3 = 1523;
    int b3 = 9962;
    int c3 = 47;

    // int max1 = Max(a1, b1, c1);
    // int max2 = Max(a2, b2, c2);
    // int max3 = Max(a3, b3, c3);
    // int max = Max(max1, max2, max3);

    int max = Max(
        Max(a1, b1, c1),
        Max(a2, b2, c2),
        Max(a3, b3, c3));


    Console.WriteLine(max);

# 4.

    // Имеется одноименный массив array из n элементов,
    // требуется найти элемент массива, равный find.
    // 1. Установить счетчик index в позицию 0
    // 2. Если array[index] = find, алгоритм завершил работу успешно
    // 3. Edtktxbnm штвуч yf 1
    // 4. Если index < n, то перейти к шагу 2. В противном случае алгоритм завершил работу безуспешно.

    int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13};
    int n = array.Length;
    int find = 4;
    int index = 0;

    while (index < n)  
    {
        if (array[index] == find)
        {
            Console.WriteLine(index);
            break;//Прерывание алгоритма
        }
        index++;
    }
    
# 5.

    void FillArray(int[] collection)
    {
        int length = collection.Length;
        int index = 0;
        while (index < length)
        {
            collection[index] = new Random().Next(1, 10);
            index++;
        }
    }

    void PrintArray(int[] col)
    {
        int count = col.Length;
        int position = 0;
        while (position < count)
        {
            Console.WriteLine(col[position]);
            position++;
        }
    }

    int IndexOf(int[] collection, int find)
    {
        int count = collection.Length;
        int index = 0;
        int position = -1;

        while (index < count)
        {
            if (collection[index] == find)
            {
                position = index;
                break;
            }
            index++;
        }
        return position;
    }

    int[] array = new int[10];

    FillArray(array);
    PrintArray(array);
    Console.WriteLine();

    int pos = IndexOf(array, 4);
    Console.WriteLine(pos);
    
# 6.

    // Дан текс. В тексет нужно все пробелы заменить черточками,
    //  маленикие буквы "к" заменить большими "К",
    // а большие "С" заменить маленькими "с".

    string text = "- Я думаю, -сказал князь, улыбаясь, что, "
                + "ежели бы вас послали вместо нашего милого Винценгероде,"
                + "вы бы взяли приступом согласие прусского короля. "
                + "Вы так красноречивы. Вы дадите мне чаю?";

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
    Console.WriteLine();
    newText = Replace(newText, 'к', 'К');
    Console.WriteLine(newText);
    Console.WriteLine();
    Console.WriteLine(newText, 'С', 'с');
    
# 7.

    // 6 8 3 2 1 4 5 7 -> 1 2 3 4 5 6 7 8

    int[] arr ={1, 5, 4, 3, 2, 6, 7, 1, 1};

    void PrintArray(int[] array)
    {
        int count = arr.Length;

        for (int i = 0; i < count; i++)
        {
            Console.Write($"{array[i]} ");
        }
        Console.WriteLine();
    }

    void SelectionSort(int[] array)
    {
        for (int i = 0; i < array.Length - 1; i++)
        {
            int maxPosition = i;
            for (int j = i + 1; j < array.Length; j++)
            {
                if (array[j] > array[maxPosition])
                maxPosition = j;

            }
            int temporary = array[i];
            array[i] = array[maxPosition];
            array[maxPosition] = temporary;
        }
    }

    PrintArray(arr);
    SelectionSort(arr);

    PrintArray(arr);
    

