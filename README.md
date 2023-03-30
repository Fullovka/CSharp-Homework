# C#-Homework

Только отрицательные числа из диапазона от A до B в обратном порядке.

```csharp
using System;
class HelloWorld {
  static void Main() {
    int a = -22; // здесь ввести последнее число из диапазона
    int b = -6; // здесь ввести начальное число из диапазона
    for (int i = a; i <= b; i++) {
        if (i % 2 == 0) {
            Console.WriteLine(i);
        }
    }
  }
}
``` 

Вычислить значение полинома (1/a)*(1/(a+2))*(1/(a+4)))..., где a = любое число

```csharp
using System;
class HelloWorld {
  static void Main() {
      
    double a = 1; // здесь введите число отличное от нуля ( на 0 делить нельзя же :) )
    int b = 2; // здесь ввести количество множителей
    
    
    if (a == 0) {
          throw new ArgumentException("Нельзя делить на 0");
      }
    
    double rsl = ((double) 1 / a) * ((double) 1 / calculatePolinom(a, b));
    
    Console.WriteLine(Math.Round(rsl, 3));
  }
  
  static double calculatePolinom(double a, int numberOfMultipliers) {
      
      double result = 1;
      
      for (int i = 1; i <= numberOfMultipliers; i++) {
          result *= a + (i * 2);
      }
      
      return result;
  }
}
```

Заменить все точки на многоточие

```csharp
using System;
class HelloWorld {
  static void Main() {
    string param = "..."; // можно ввести любой параметр, не только троеточие
    string paramToChange = "."; // можно ввести любой параметр для замены
    
    string randomStringFirst = "aklfj.uaidhuiahd.ahduiashd.";
    string randomStringSecond = "dsfmlksadfkl..asdasd...sadasdsa";
    string randomStringThird = "";
    string randomStringFourth = "fdasfdsa";
    string randomStringFifth = "...";
    
    string[] strings = {randomStringFirst, randomStringSecond, randomStringThird, randomStringFourth, randomStringFifth};
    
    foreach (string stringValue in strings) {
        Console.WriteLine(stringValue.Replace(paramToChange, param));
    }
  }
}
```
Найти минимальное число из массива состоящих из 8 чисел

```csharp
using System;
using System.Linq;
class HelloWorld {
  static void Main() {
    int[] randomArray = generateArray();
    Console.WriteLine("Min is - " + randomArray.Min());
  }
  
  static int[] generateArray() {
      Random random = new Random();
      int[] values = new int[8];
      for (int i = 0; i < 8; i++) {
 	 values[i] = random.Next();
	 Console.WriteLine("generateValue in Array is - " + values[i]);
      }
      return values;
  }
}
```

Решить квадратное уравнение
```csharp
using System;
using System.Text;
class Program {
    static void Main(){
        
        // Квадратное уравнение имеет вид - ax^2 + bx + c = 0
        
        double a = 1;
        double b = 4;
        double c = 4;
        double x1, x2;
        var discriminant = Math.Pow(b, 2) - 4 * a * c;
        if (discriminant < 0) {
            Console.WriteLine("Квадратное уравнение не имеет корней");
        } else {
            if (discriminant == 0) //квадратное уравнение имеет 1 решение
            {
                x1 = -b / (2 * a);
                Console.WriteLine($"x1 = {x1}");
            } else { 
	    	// уравнение имеет два корня
                x1 = (-b + Math.Sqrt(discriminant)) / (2 * a);
                x2 = (-b - Math.Sqrt(discriminant)) / (2 * a);
                Console.WriteLine($"x1 = {x1}; x2 = {x2}");
            }
        }
    }
}
```
Решить матрицу

```csharp
/**
Matrix
[1, 2, -3]
[4, 5, 6]
[-5, 8, 9]
[12, 1, 9]
[0, 1, 4]
**/
using System;
class HelloWorld {
  static void Main() {
    int n = 2; // столбцы (итерация начинается с нуля 0, 1, 2)      
    int m = 4; // строки (итерация начинается с нуля 0, 1, 2, 3, 4)
    // Исходный размер матрицы можно считать 3x5
    
    int[,] matrix = new int[,]{ {1, 2, -3},
                                {4, 5, 6 }, 
                                {-5, 8, 9}, 
                                {12, 1, 9}, 
                                {0, 1, 4 } 
        
    };  
    
    // Для каждой строки вычисляем сумму элементов
    
    for (int i = 0; i <= m; i++) {
        int result = 0;
        for (int j = 0; j <= n; j++) {
            result += matrix[i,j];
        }
        Console.WriteLine(result);
        result = 0;
    }
  }
}
```

Запрашивать у пользователя числа и выводить по условию
```csharp
using System;
class Program {
    static void Main() {
        while (true) {  
        Console.WriteLine("Введите целое число");
        
        int c = int.Parse(Console.ReadLine());
        
        bool firstBool = c % 2 == 0;
        bool secondBool = c % 3 == 0;
        bool thirdBool = firstBool && secondBool;
        
        if ((firstBool || secondBool) && !(thirdBool)) {
            Console.WriteLine("Данное число делится либо на 2, либо на 3, но не делится одновременно на 2 и на 3. Число - " + c);
        } else {
            Console.WriteLine("Данное число нам не подходит.");
        }
    }
  }
}
```
