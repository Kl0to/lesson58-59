# lesson58-59
Болкарева Анна

1-Цикл это многократное выполнение одинаковых действий

2-Цикл по переменной будет всегда выполняться конечное число раз, но в решении задач, где заранее неизвестно количество повторений, он не применим. Цикл с условием надо использовать аккуратно и следить, чтобы не было бесконечного зацикливания

3-цикл с предусловием - цикл, где проверка условия выполняется в начале цикла

4-Если условие сразу ложно

5-В случае когда условие никогда не выполнится

6-В случае, если начальное значение параметра больше конечногj

7-Верно, если в тело цикла добавить переменную, являющуюся счетчиком, каждый повтор цикла её изменять на один шаг, а в условии цикла указать конечное значение счетчика

8-В случае, если известно количество итераций цикла

9-

задачи

1-#include <iostream>
 
int product(const int a, const int b)
{
    int product = 0;
    for (unsigned i = 0; i < abs(b); ++i)
        product += a;
 
  return (b < 0 ? -product : product);
}
 
int main()
{
    int a, b;
    std::cin >> a >> b;
    std::cout << product(a, b) << std::endl;
    return 0;
}

(не судите за с++, я его дольше всего изучала)

2-n=int(input('n='))

x=0

for i in range(0,n+1):

   x=x+i;
    
print(x)

3-n = int(input())

for i in range (1,2*n,2):

print (i+1)

4-a = 4

b = 5

print(list(filter(lambda x: all(x % i for i in range(2, x)), list(range(a,b+1)))))

5-a, b = map(int, input().split())

print(*(x for x in range(a, b) if all(x % y for y in range(2, x))))

6-#include <iostream>

#include <cstdlib> // для std::rand и std::srand

#include <ctime>   // для std::time

int main() {
  
  std::srand(static_cast<unsigned int>(std::time(0))); 

  unsigned int N;
  
   std::cout << "Введите натуральное число N: ";
    
  std::cin >> N;

  std::cout << "Псевдослучайные числа: ";
  
  for (unsigned int i = 0; i < N; ++i) {
    
   int random_number = std::rand() % 100; 
        
  std::cout << random_number << " ";
  
  }
    
  std::cout << std::endl;

   return 0;
   
}

7-print(*filter(lambda x: x % 133 == 125 and x % 134 == 111, range(10000, 100000)))

8-#include <iostream>

bool helpmepls(int number) {
    int original = number;
    
  while (number > 0) {
        int digit = number % 10;
        if (digit == 0 || original % digit != 0) {
            return false;
        }
        number /= 10;
    }
    
   return true;
}

int main() {
    b int N;
    std::cout << "Введите натуральное число N: ";
    std::cin >> N;

  std::cout << "Числа, не превосходящие " << N << " делящиеся на каждую из своих цифр: ";
    for ( b int i = 1; i <= N; ++i) {
        if (helpmepls(i)) {
            std::cout << i << " ";
        }
    }
    std::cout << std::endl;

  return 0;
}

9-for i in range(100,1000):

   sum = 0
    
   for s in range(0, 3):
    
  i = str(i)
        
   sum = sum + int(i[s]) ** 3
        
  i = int(i)
        
  if sum == i:
    
   print(i)

10-mod = 10

for i in range(1, N + 1):

  if i == mod:
    
   mod *= 10
        
  if (i * i) % mod == i:
    
   print(i)

11-def count_even_digits(number):

  count = 0
    
  for digit in str(number):
    
  if digit.isdigit() and int(digit) % 2 == 0:
        
   count += 1
            
 return count;

number = input("Введите число: ")

even_digits_count = count_even_digits(number)

print(f"Количество четных цифр в числе {number}: {even_digits_count}")

12-n, s = int(input()), 0 

while n: s += n % 10; n //= 10 

print(s)

13-#include <iostream>

#include <string>

bool has_adjacent_equal_digits(const std::string& number) {

  for (size_t i = 0; i < number.length() - 1; ++i) {
    
   if (number[i] == number[i + 1]) {
        
  return true; // Найдены две одинаковые цифры рядом
    }
    
  }
  
  return false; // Рядом одинаковых цифр не найдено
  
}

int main() {
    std::string number;
    std::cout << "Введите число: ";
    std::cin >> number;

  if (has_adjacent_equal_digits(number)) {
        std::cout << "Число содержит две одинаковые цифры, стоящие рядом." << std::endl;
    } else {
        std::cout << "Число не содержит две одинаковые цифры, стоящие рядом." << std::endl;
    }

  return 0;
}

14-#include <iostream>
#include <string>

bool has_all_equal_digits(const std::string& number) {
    if (number.empty()) return false; // Проверка на пустую строку

   char first_digit = number[0]; // Запоминаем первую цифру

  for (size_t i = 1; i < number.length(); ++i) {
        if (number[i] != first_digit) {
            return false; // Найдена цифра, отличная от первой
        }
    }
    return true; // Все цифры одинаковые
}

int main() {
    std::string number;
    std::cout << "Введите число: ";
    std::cin >> number;

  if (has_all_equal_digits(number)) {
        std::cout << "Число состоит из одинаковых цифр." << std::endl;
    } else {
        std::cout << "Число не состоит из одинаковых цифр." << std::endl;
    }

   return 0;
}

15-def foo(m:str):
    nums = map(str, range(0, 10))
 
  for num in nums:
        if m.count(num) > 1:
            return True
 
   return False
 
m = input()
print('YES' if foo(m) else 'NO')

16-for exponent in range(10, 1, -1); 

if exponent % 2 == 0; 

print(f"2^{exponent} = {2 ** exponent}")

17-a = int(input("Введите первое число: ")) b = int(input("Введите второе число: ")) steps = 0

while b != 0: a, b = b, a - b steps += 1

print("НОД =", a) print("Количество шагов:", steps)

18-a = int(input("Введите первое число: ")) b = int(input("Введите второе число: ")) steps = 0

while b != 0: a, b = b, a % b steps += 1

print("НОД =", a) print("Количество шагов:", steps)

19-1.steps1 = 0 while b != 0: a, b = b, a - b steps1 += 1

nod1 = a

2.a = 64168 b = 82678 steps2 = 0 while b != 0: a, b = b, a % b steps2 += 1

nod2 = a

print("НОД(a, b):", nod1) print("Шаги-1:", steps1) print("Шаги-2:", steps2)

20-sum_nums = 0 product = 1

for _ in range(10): number = int(input("Введите число: ")) sum_nums += number product *= number

print("Сумма:", sum_nums) print("Произведение:", product)

21-while True:

  n = int(input('|>'))
    
  if not n:
    
  break
        
  tm.append(n)
 
count_n = 0

for i in range(len(tm) - 1):

  if tm[i + 1] > tm[i];
  
   count_n += 1
        
print(count_n)

22-min_num = float('inf') max_num = float('-inf')

while True: number = int(input("Введите число (0 для выхода): ")) if number == 0: break if number < min_num: min_num = number if number > max_num: max_num = number

print("Минимальное число:", min_num)

print("Максимальное число:", max_num

23-import math

N = int(input("Введите натуральное число: ")) factorial = 1 for i in range(1, N + 1): factorial *= i

print("Факториал:", factorial)

24-a = int(input("Введите натуральное число a: ")) N = int(input("Введите натуральное число N: ")) A = a ** N;  print("A =", A)

25-number = input("Введите число: ") for digit in number: print(digit)

26-N = int(input("Введите натуральное число N: ")) fib = [1, 1] while len(fib) < N: fib.append(fib[-1] + fib[-2]) print(f"Первые {N} чисел Фибоначчи: {fib[:N]}")

27-a = int(input("Введите число a: ")) b = int(input("Введите число b: "))

def is_prime(n): if n < 2: return False for i in range(2, int(n**0.5) + 1): if n % i == 0: return False return True

primes = [num for num in range(a, b + 1) if is_prime(num)] print("Простые числа в диапазоне:", primes)

28-N = int(input("Введите натуральное число N: ")) sum_divisors = sum(i for i in range(1, N) if N % i == 0) is_perfect = sum_divisors == N print("Является ли N совершенным:", is_perfect)

29-N = int(input("Введите натуральное число N: "))

def is_perfect(num): return sum(i for i in range(1, num) if num % i == 0) == num

perfect_numbers = [num for num in range(1, N + 1) if is_perfect(num)] print("Совершенные числа в диапазоне:", perfect_numbers)

30-count = 0

for x in range(186 // 15 + 1);

for y in range(186 // 17 + 1);

for z in range(186 // 21 + 1);

if 15 * x + 17 * y + 21 * z == 185;

print(f"15*{x} + 17*{y} + 21*{z}") count += 1

print("Количество способов:", count)

31-def find_period(n): result = "0." seen_remainders = {} numerator = 1 index = 0

while True:
    numerator *= 10
    digit = numerator // n
    remainder = numerator % n

  result += str(digit)

  if remainder == 0:
        return result 

  if remainder in seen_remainders:
        period_start = seen_remainders[remainder]
        non_period = result[:period_start]
        period = result[period_start:]

  return f"{non_period}({period})"

  seen_remainders[remainder] = len(result)
    numerator = remainder

  N = int(input("Введите натуральное число N: ")) print("1/", N, "=", find_period(N), sep="")

32-import random

def simulate_monty_hall(rounds=1000): stay_wins = 0 switch_wins = 0

for _ in range(rounds):
    # Случайно выбираем ящик с призом
    prize_box = random.randint(0, 2)
    # Участник случайно выбирает один из трех ящиков
    player_choice = random.randint(0, 2)
    
  
   empty_box = next(box for box in range(3) if box != player_choice and box != prize_box)
    
   
  new_choice = next(box for box in range(3) if box != player_choice and box != empty_box)

   
  if player_choice == prize_box:
        stay_wins += 1
    if new_choice == prize_box:
        switch_wins += 1

print("Количество побед, оставаясь при своём выборе:", stay_wins)
print("Количество побед, меняя выбор:", switch_wins)

simulate_monty_hall()

#59

1-Процедуры — это именованные фрагменты кода, которые выполняют определённую задачу. Они позволяют структурировать программу, повторно использовать код и улучшать его читаемость

2-В школьном алгоритмическом языке процедуры могут оформляться как "Процедура имя(параметры) ... КонецПроцедуры". В Паскале они оформляются аналогично с ключевым словом "procedure":

pascal procedure MyProcedure(parameter: type); begin; end.

3-Нет, нужно также вызвать процедуру в тексте основной программы. В противном случае код процедуры не выполнится

4-Параметры — это значения, которые передаются в процедуру. Они позволяют обрабатывать входные данные и делать процедуру более универсальной

5-Локальные переменные объявляются внутри процедуры и доступны только в пределах этой процедуры

6-Процедуры с несколькими параметрами оформляются, перечисляя параметры через запятую в заголовке процедуры:

pascal procedure MyProcedure(param1: type1; param2: type2);

7-Изменяемые параметры позволяют процедуре изменять значения переменных, переданных ей в качестве аргументов. Это полезно, когда нужно возвращать несколько значений из процедуры

8-В Питоне все параметры неизменяемые по умолчанию, кроме объектов. В Паскале изменяемые параметры обозначаются ключевым словом "var":

pascal procedure MyProcedure(var param: type);

9-В школьном алгоритмическом языке можно выделить простые, массивные и структурные параметры. Они объявляются через соответствующий тип данных.

Задача

1-pascal procedure PrintOctalNumber(num: Integer); begin if num < 810 then WriteLn(Octal(num)); end;

2-pascal procedure PrintHexadecimalNumber(num: Integer); begin if num < 65536 then WriteLn(Hex(num)); end;

3-pascal procedure PrintStarSquare(N: Integer); var i, j: Integer; begin for i := 1 to N do begin for j := 1 to N do Write('*'); WriteLn; end; end;

4-pascal procedure PrintAge(age: Integer); begin if (age mod 10 = 1) and (age mod 100 <> 11) then WriteLn(age, ' год') else if (age mod 10 >= 2) and (age mod 10 <= 4) and (age mod 100 <> 12) and (age mod 100 <> 13) and (age mod 100 <> 14) then WriteLn(age, ' года') else WriteLn(age, ' лет'); end;

5-procedure PrintNumberInWords(num: Integer);
begin; 
end;

6-pascal procedure PrintFibonacci(N: Integer); var a, b, temp, i: Integer; begin a := 0; b := 1; for i := 1 to N do begin Write(a, ' '); temp := a; a := b; b := temp + b; end; end;

7-pascal procedure CheckPrime(var num: Integer; var isPrime: Boolean); var i: Integer; begin isPrime := True; if num < 2 then isPrime := False; for i := 2 to Trunc(Sqrt(num)) do if (num mod i = 0) then begin isPrime := False; Break; end; end;

8-pascal procedure PrintDigitsReversed(num: Integer); begin while num > 0 do begin WriteLn(num mod 10); num := num div 10; end; end;

9-pascal procedure PrintDigitsForward(num: Integer); var digits: array of Integer; i: Integer; begin while num > 0 do begin SetLength(digits, Length(digits) + 1); digits[High(digits)] := num mod 10; num := num div 10; end; for i := High(digits) downto 0 do WriteLn(digits[i]); end;

10-pascal procedure PrintDivisors(num: Integer); var i: Integer; begin for i := 1 to num do if (num mod i = 0) then Write(i, ' '); WriteLn; end;

11-pascal procedure PrintLine(M: Integer); var i: Integer; begin for i := 1 to M do Write('-'); WriteLn; end;

12-pascal procedure PrintRoman(num: Integer); var roman: array[1..13] of String = ('I', 'II', 'III', 'IV', 'V', 'VI', 'VII', 'VIII', 'IX', 'X', 'L', 'C', 'D', 'M'); begin; end;
