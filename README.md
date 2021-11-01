# automatic-doodle
just a new repository

#include <stdio.h>
#include <stdlib.h> /*叫出rand()和srand()*/
#include <time.h> /*叫出time()*/

int main(void)
{
 int i,ran[7],sex,city,sum,check;
 char city_abc;
/*設定變數：ran[]用來決定身分證的7個流水號、sex為性別(以1,2表示)、city為縣市的字母代號轉換而成的數值、city_abc為縣市字母代號、sum用來計算檢查號碼、check為檢查號碼*/

 srand(time(NULL));
 /*為了使每次產生的亂碼都不同，使用srand()和time()改變一開始的亂數值*/
 
 printf("請輸入你的性別(男:1,女:2)、縣市代號(字母請大寫): \n");
 scanf("%d",&sex);
 scanf("%c",&city_abc);
 /*指示使用者輸入*/
 
 switch(city_abc)
 {
     case 'A' : city = 10;
     break;
     case 'B' : city = 11;
     break;
     case 'C' : city = 12;
     break;
     case 'D' : city = 13;
     break;
     case 'E' : city = 14;
     break;
     case 'F' : city = 15;
     break;
     case 'G' : city = 16;
     break;
     case 'H' : city = 17;
     break;
     case 'I' : city = 34;
     break;
     case 'J' : city = 18;
     break;
     case 'K' : city = 19;
     break;
     case 'L' : city = 20;
     break;
     case 'M' : city = 21;
     break;
     case 'N' : city = 22;
     break;
     case 'O' : city = 35;
     break;
     case 'P' : city = 23;
     break;
     case 'Q' : city = 24;
     break;
     case 'R' : city = 25;
     break;
     case 'S' : city = 26;
     break;
     case 'T' : city = 27;
     break;
     case 'U' : city = 28;
     break;
     case 'V' : city = 29;
     break;
     case 'W' : city = 32;
     break;
     case 'X' : city = 30;
     break;
     case 'Y' : city = 31;
     break;
     case 'Z' : city = 33;
     break;
  }
/*用switch 將使用者輸入的縣市代號轉換為計算檢查號碼用的對應數值*/

 for (i = 0;i < 7;i++)
 ran[i] = rand () % 10;
 /*身分證字號第三到第九字元為流水號，以rand()決定*/

 sum = ( city / 10 ) + ( ( city % 10 ) * 9 ) + ( sex * 8 ) +( ran[0] * 7 ) +
    ( ran[1] * 6 ) + ( ran[2] * 5 ) + ( ran[3] * 4 ) + ( ran[4] * 3) +
    ( ran[5] * 2) + ( ran[6] * 1);
/*乘上權數並相加: 縣市代號轉換而來的數值第一位數字乘1另一位乘9，性別代號乘8，剩餘流水號各自由左至右按順序乘上7,6,5……1，接著所有數值相加 */

 sum = sum % 10;
 check = 10 - sum;
 /*sum除以10取餘數再由模數(即10)減去後得檢查號碼chech*/

 printf("%c",city_abc);
printf("%d%d%d%d%d%d%d%d%d",sex,ran[0],ran[1],ran[2],ran[3],ran[4],ran[5],ran[6],check);
 /*輸出得到的身分證字號，第一個字元為縣市字母代號，第二個是代表性別，但三個至第九個字元為流水號，最後一位為檢查號碼*/

 return 0 ;
}
