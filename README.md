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
### Control Flow Graph!
![Control Flow Graph Za Java Kod](https://user-images.githubusercontent.com/102921986/171273170-6894ea50-7dea-47fe-a739-7523a4135d14.png)

### Pregled na izvrshuvanje naredbi


## Zadacha 3
### Ciklomatska kompleksnost na daden kod 
### kompleksnost = Broj + 1 C = 5

## Zadacha 4
### Test sluchai spored Every statement kriterium
#### '    [], [‘#’,0,’#’]     '
## Zadacha 5
### Test sluchai spored Every Branch kriterium
#### '     [], [‘#’, 0, ’#’], [0, ‘#’, 0], [0, 0]    '
## Komentar
#### Za Every Statement, izberi vrednosti sekoja linija da se aktivira. Zа Multiple Condition vrednostite treba da dadat site mozni kombinacii za vistins kivrednosti koi imaat logichka smisla. 
