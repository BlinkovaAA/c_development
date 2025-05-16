// The first program :)

#include <stdio.h>              

int main()                      
{
    printf("Hello, world!");    

    return 0;                   
}

// Задача. Эксперимент длится h часа m минут. Сколько это в минутах? Сколько это в секундах?

#include <stdio.h>

int main()
{
    int h, m;

    scanf("%d%d", &h, &m);

    printf("%d\n", h * 60 + m);
    printf("%d", (h * 60 + m) * 60);

    return 0;
}

// Задача. 

#include <stdio.h>

int main() 
{
    int rub, kop;
    
    scanf("%d %d", &rub, &kop);
    
    // Приводим всю сумму к копейкам
    int total_kop = rub * 100 + kop; 
    
    // Ищем максимальное количество n, которое можно оставить
    int n = 0;
    while (total_kop >= (n * 100 + n * 5 + n)) { // 100*n + 5*n + 1*n = 106*n
        n++;
    }
    
    n--;

    // Рассчитываем остаток
    int used_kop = n * (100 + 5 + 1); 
    int rest = total_kop - used_kop; 

    // Вывод результата
    printf("%d %d\n", n, rest);
    
    return 0;
}

// Задача. Формула Герона

#include <stdio.h>

int main()
{
    int g1, s1, k1, g2, s2, k2;
    
    
    scanf("%d %d %d\n", &g1, &s1, &k1);
    scanf("%d %d %d", &g2, &s2, &k2);
    
    int money = (g1 + g2) * 17 * 29 + (s1 + s2) * 29 + (k1 + k2);
    
    printf("%d %d %d", money / 493, (money % 493) / 29, (money % 493) % 29);
    
    return 0;
}

// Задача. 

#include <stdio.h>
#include <math.h>

float dist(int x1, int y1, int x2, int y2)
{
    int x, y;
    x = abs(x1 - x2);
    y = abs(y1 - y2);
    return sqrt((x * x) + (y * y));
}

float area(int x1, int y1, int x2, int y2, int x3, int y3)
{
    float n1, n2, n3;
    float p;
    n1 = dist(x1, y1, x2, y2);
    n2 = dist(x2, y2, x3, y3);
    n3 = dist(x1, y1, x3, y3);
    p = (n1 + n2 + n3) / 2;
    return sqrt(p * (p - n1) * (p - n2) * (p - n3));
}


int main()
{
    int x1, y1, x2, y2, x3, y3;
    float P;
    
    scanf("%d%d%d%d%d%d", &x1, &y1, &x2, &y2, &x3, &y3);
    P = area(x1, y1, x2, y2, x3, y3);
    printf("%.3f", P);
    return 0;
}    

// Задача. Swap

#include <stdio.h>

void swap(int * px, int * py)
{
    int temp;
    temp = *px;
    *px = *py;
    *py = temp;
}
    

int main()
{
    int x, y;
    scanf("%d%d", &x, &y); 

    swap(&x, &y);
   

    printf("%d %d\n", x, y); 

    return 0;
}
