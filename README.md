# SI_2022_lab2_167001
 This is a remote repository
# Elena Efremovska 167001 
## Zadacha 1 SILab2.java
### Funkcijata vo Java kodot dava: 
#### za vlez niza od 0 i '#'
#### izlez niza od 0 i broevi
#### shto podrazbira broj na bombi i mesta kade nema bombi so 0.
## Kodot na funkcijata
### '''JavaScript
   import java.util.ArrayList;
import java.util.List;

public class SILab2 {

    public static List<String> function(List<String> list) {
        if (list.size() <= 0) {
            throw new IllegalArgumentException("List length should be greater than 0");
        }
        int n = list.size();
        int rootOfN = (int) Math.sqrt(n);
        if (rootOfN * rootOfN  != n) {
            throw new IllegalArgumentException("List length should be a perfect square");
        }
        List<String> numMines = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            if (!list.get(i).equals("#")) {
                int num = 0;
                if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) || (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ) {
                    if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) && (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ){
                        num += 2;
                    }
                    else {
                        num  += 1;
                    }
                }
                if (i - rootOfN >= 0 && list.get(i - rootOfN).equals("#")){
                    num++;
                }
                if (i + rootOfN < n && list.get(i + rootOfN).equals("#")){
                    num++;
                }
                numMines.add(String.valueOf(num));
            }
            else {
                numMines.add(list.get(i));
            }
        }
        return numMines;
    }
}
'''
## Zadacha 2
### Ova e Grafot za Java funkcijata !
![SI_lab2](https://user-images.githubusercontent.com/102921986/171959331-aad14724-4b70-4302-bbf6-73c92f811659.png)


### Control Flow Graph!
![Control Flow Graph Za Java Kod](https://user-images.githubusercontent.com/102921986/171273170-6894ea50-7dea-47fe-a739-7523a4135d14.png)

### Pregled na izvrshuvanje naredbi


## Zadacha 3
### Ciklomatska kompleksnost na daden kod 
### kompleksnost = rebra - jazli + 2  = 31 -25 +2 = 8

## Zadacha 4
### Test sluchai spored Every statement kriterium 25 statements
####      Test case '#1': Input empty list, Output "List length should be greather than 0". Gi dava statements:1,2,3,23
####      Test case '#2': Input 0,0,0,0,0,0,0,0 , Output "List length should be a perfect square" Gi ima :1,2,4,5,6,7,23. 
####      Test case '#3': Input 0,#,0,#,0,#,#,#,0,Nema exceptions, Output е 2,#,2,#,4,#,#,#,2. Gi ima:1,2,4,5,6,8,9.1,9.2,9.3,10,11,12,13,14,15,16,17,18,19,20,21,22,23.
## Zadacha 5
### Test sluchai spored Every Branch kriterium
#### Ima 31 branches 
#### Test case #1: Input empty list, Output "List length should be greather than 0" Gi ima branches:1-2,2-3,3-23.
#### Test case #2: Input 0,0,0,0,0,0,0,0 , Output "List length should be a perfect square". Gi ima branches:1-2,2-4,4-5,5-6,6-7,7-23. 
#### Test case #3: Input 0,#,0,#,0,#,#,0,#,  Nema exceptions, Output е 2,#,2,#,3,#,#,2,#. Gi ima branches:1-2,2-4,4-5,5-6,6-8,8-9.1,9.1-9.2,9.2-10,9.2-21,10-11,10-20,11-12,12-13,12-14,13-15,14-15,15-16,15-17,16-17,17-18,17-19,18-19,19-21,20-21,21-9.3,9.3-9.2,21-22,22-23.

Releases
## Komentar
#### Za Every Statement, izberi vrednosti sekoja linija da se aktivira. Zа Multiple Condition vrednostite treba da dadat site mozni kombinacii za vistins kivrednosti koi imaat logichka smisla. 
