### Ferdy Fermadi

## Soal 1

```sql
SELECT b.KODEBRG, b.NAMABRG, COALESCE(SUM(j.JUMLAH), 0) as JML_JUAL
FROM BARANG b
JOIN JUAL j
ON b.KODEBRG = j.KODEBRG
GROUP BY b.KODEBRG, b.NAMABRG
ORDER BY b.KODEBRG
```

## Soal 2

```sql
SELECT KodeBarang, StokAkhir
FROM HistoriStokBarang hsb
WHERE KodeStok = (
SELECT MAX(KodeStok) FROM HistoriStokBarang
WHERE KodeBarang = hsb.KodeBarang
)
ORDER BY KodeBarang
```

## Soal 3

```c#
class Program
{
    static void Main()
    {
        Console.Write("Input: ");
        int inputNumber = int.Parse(Console.ReadLine());

        List<int> fibonacciNumbers = GenerateFibonacciNumbers(inputNumber);

        if (fibonacciNumbers.Contains(inputNumber))
        {
            foreach (var num in fibonacciNumbers)
            {
                Console.Write(num + " ");
            }
        }
        else
        {
            foreach (var num in fibonacciNumbers)
            {
                if (num > inputNumber) break;
                Console.Write(num + " ");
            }
        }
    }

    static List<int> GenerateFibonacciNumbers(int limit)
    {
        List<int> fibonacciNumbers = new List<int> { 1, 1 };
        int nextNumber = 0;

        while ((nextNumber = fibonacciNumbers[^1] + fibonacciNumbers[^2]) <= limit)
        {
            fibonacciNumbers.Add(nextNumber);
        }

        return fibonacciNumbers;
    }
}
```

# Soal 4

```C#
class Program
{
    static void Main()
    {
        Console.Write("Input: ");
        int input = int.Parse(Console.ReadLine());
        
        Console.WriteLine("Output:");
        for (int i = 1; i <= input * 2 - 1; i += 2)
        {
            for (int j = 0; j < i; j++)
            {
                Console.Write("*");
            }
            Console.WriteLine();
        }
    }
}
```

# Soal 5

```C#
class Program
{
    static void Main()
    {
        Console.Write("Input 1: ");
        int inputA = int.Parse(Console.ReadLine());   
        Console.Write("Input 2: ");
        int inputB = int.Parse(Console.ReadLine());
        string firstNumberString = inputA.ToString();
        string result = firstNumberString.PadLeft(inputB, '0');
        Console.WriteLine("Output: " + result);
    }
}
```
