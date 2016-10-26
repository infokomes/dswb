# GDB

Z uwagi, iż w zadaniach domowych wykorzystywane jest alokowanie pamięci za pomocą "new" kompilacje zadań należy wykonywać za pomocą g++ a nie gcc.

## Zadanie domowe 2
Znajdź błędy za pomocą gdb w programie tablica.c

Rozwiązanie

    ulimit -c 1024
    g++ -g double_free.c -o double_free_gdb


## Zadanie domowe 3
Znajdź błędy za pomocą gdb w programie odwroc_tablice.c

Rozwiązanie

    tablica
 
## Zadanie domowe 4
Znajdź błędy za pomocą gdb w programie wielomian.c

Rozwiązanie

    tablica
    
## Zadanie domowe 1
Wersja release to ta, w której program jest dostarczany użytkownikowi. Plik programu jest zoptymalizowany pod względem rozmiaru i/lub szybkości działania. Można sterować stopniem optymalizacji gcc m.in. za pomocą opcji -OX, gdzie X jest liczbą większą lub równą 0. Większa liczba oznacza włączenie większej liczby optymalizacji (co nie zawsze skutkuje szybszym kodem). 0 oznacza wyłączenie optymalizacji.
Opcja -g w gcc powoduje dołączenie do wynikowego pliku wykonywalnego informacji debugowych, takich jak np. odpowiedniość między instrukcjami programu a liniami w kodzie źródłowym. Debugowanie programów skompilowanych z tą opcją jest dużo łatwiejsze.
Mając core dump programu skompilowanego bez informacji debugowych może się pojawić pokusa, aby skompilować program jeszcze raz z opcją –g i wykorzystać go w gdb do analizy pliku core. Trzeba jednak mieć na uwadze, że kompilator może generować inny kod, kompilując z opcją –g, w związku z czym nie musi on odpowiadać plikowi core. W takich sytuacjach należy powtórzyć wystąpienie błędu w programie z informacjami debugowymi.
Polecenie strip jest przydatne do usuwania z plików binarnych informacji o symbolach i informacji debugowych. Aby zaoszczędzić rozmiar uruchamianego pliku wykonywalnego można użyć go na pliku będącym efektem kompilacji z opcją -g. Mając core dump takiego programu możemy ponownie przekompilować go z opcją -g i używać do analizy pliku core.
Zadanie: W katalogu  objdump  dana jest wykonywalna binarka bez informacji debugowych i core dump z niej. Mając źródło programu należy powiedzieć, w której funkcji (najchętniej) program zakończył działanie. Przydatne polecenie:
    
    objdump -d -M intel <plik> 

Rozwiązanie

    tablica