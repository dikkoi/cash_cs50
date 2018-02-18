# cash_cs50
Совершил кучу мелких ошибок по невнимательности, пока добивался исправной работы  
Некоторое время получал правильный результат, но из за того, как запрограммировал его вывод, воспринимал как неверный и ковырялся,     хорошо хоть исправил, но блин, сколько же я теряю из за невнимательности  
Больше всего конечно разочаровало то, как комп обрабатывает числа с плавающей точкой, это жесть.  
Использовал только те знания о языке, которые были на данном уроке, так что выглядит программа не очень эффективной, из за того что одну и туже операцию но с разными значениями описываю отдельными строками кода.  


#include <stdio.h>  
#include <cs50.h>  
#include <math.h>  
int main(void) {  
    float cashback2 = get_float("Сумма для сдачи: ");  
    int coins = 0;  
    //float her;  
    int cashback = round(cashback2*100);  
   //printf("кешбек в целых = %d\n", cashback);  
   // printf("her %f\n", her = round(20.5));  
    int reminder;  

    //step quarter  

    int quarter = 25;  
    int coins25 = floor(cashback / quarter);  
    reminder = round(cashback - (floor(cashback / quarter) * quarter) );  
   // printf("целых четвертаков: %d", coins25);  
    //printf("\nостаток от деления %d", reminder);  
    coins+=coins25;  
    //step TEN  

    //int coins10;  
    if (reminder > 0) {  
    int ten = 10;  
    int coins10 = floor(reminder /ten);  
    reminder = round( reminder - (floor(reminder / ten) * ten) );  
    //printf("\nцелых десяток: %d", coins10);  
    //printf("\nостаток от деления %d", reminder);  
    coins+=coins10;  
    }  

    //step FIVE  
    if (reminder > 0) {  
    int five = 5;  
    int coins5 = floor(reminder / five);  
    reminder = reminder - (floor(reminder / five) * five);  
    //printf("\nцелых пятерок: %d", coins5);  
    //printf("\nостаток от деления %d", reminder);  
    coins+=coins5;  
    }  

    //step ONE  
    if (reminder > 0) {  
    int one = 1;  
    int coins1 = floor(reminder / one);  
    reminder = cashback - (floor(cashback / one) * one);  
    //printf("\nцелых центов: %d", coins1);  
    //printf("\nостаток от деления %d", reminder);  
    coins+=coins1;  
    }  

// All coins to back  
    if (reminder < 1) {  
       printf("%d\n", coins);  
    }  

}  
