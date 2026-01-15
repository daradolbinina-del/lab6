# Домашнее задание к работе 6
## Условие задачи
Дано шестизначное число, определить является ли оно "счастливым".

## 1. Алгоритм и блок-схема
### Алгоритм
1. **Начало**
2. Ввод шестизначного числа:
- int number;
3. Разделение числа на три первые и три последние цифры:
- first = number / 1000;
- second = number % 1000;
4. Вычисление суммы цифр первой половины:
- Сумма цифр = первая цифра + вторая цифра + третья цифра
5. Вычисление суммы цифр второй половины аналогично
  
6. Использование тернарной операции для сравнения сумм:
- result = (sum1 == sum2) ? "СЧАСТЛИВОЕ" : "НЕСЧАСТЛИВОЕ";
7. Вывод результата
8. **Конец**
   
### Блок-схема
<img width="401" height="814" alt="image" src="https://github.com/user-attachments/assets/5a5ea397-0cbd-44ed-b2fb-8aaf5bfb0243" />


## 2. Реализация программы
#define _CRT_SECURE_NO_WARNINGS
#include <locale.h>
#include <stdio.h>

int main() {
    setlocale(LC_ALL, "RUS");

    int number;
    int firs, second;
    int sum1 = 0, sum2 = 0;

    printf("Введите шестизначное число: ");
    scanf("%d", &number);

    firs = number / 1000;   
    second = number % 1000;   

    
    sum1 = (firs / 100) +         
        ((firs / 10) % 10) +   
        (firs % 10);            

    sum2 = (second/ 100) +         
        ((second / 10) % 10) +   
        (second % 10);            

    
    const char* result = (sum1 == sum2) ? "СЧАСТЛИВОЕ" : "НЕСЧАСТЛИВОЕ";

    printf("Число %d является %s\n", number, result);
    printf("Сумма первых трех цифр: %d\n", sum1);
    printf("Сумма последних трех цифр: %d\n", sum2);

    return 0;
}

## 3. Результаты работы программы
## Число несчастливое 
<img width="445" height="117" alt="image" src="https://github.com/user-attachments/assets/7f938d62-9ed3-477e-b93a-885b2f8a9087" />

## Число счастливое
<img width="430" height="112" alt="image" src="https://github.com/user-attachments/assets/071e4fa4-8172-447b-b6b9-5619290b12b9" />
