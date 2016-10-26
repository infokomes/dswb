# GDB

Z uwagi, iż w zadaniach domowych wykorzystywane jest alokowanie pamięci za pomocą "new" kompilacje zadań należy wykonywać za pomocą g++ a nie gcc.

## Dla zadan 2-4 brak zabezpieczenia przed wprowadzeniem zmiennych błednych
## Dla zadan 2-3 mozna dodac wiecej niz 100 el.

## Zadanie domowe 2
Znajdź błędy za pomocą gdb w programie tablica.c

Rozwiązanie

    ulimit -c 1024
    g++ -g tablica.c -o tablica

    frame 8 18
    int m = 0; funkcja przyjmuje zawsze 0 jesli 
    (min elementy > 0 ) (max elementy < 0)
    ,a powinno być int m = tabl[0]

    frame 34 
    avg dzielenie przez 0
    input 0 5

    frame 46 49
    
    scanf("%d", &tabl[1]);  # zaczyna od 1 , a tabl zaczyna sie od 0 -> tab[0] = 0
    
    for (i=2; i<=n; i++) # <=n przec co tracimy ostatnia zmienna
    
## Zadanie domowe 3
Znajdź błędy za pomocą gdb w programie odwroc_tablice.c

Rozwiązanie

    ulimit -c 1024
    g++ -g odwroc_tablice.c -o odwroc_tablice
    
    0 shuold be cout pusta tablica
    
    frame 28
    wyswietl(tablica, 5);  5 should be n
    
    frame 32
    for (int i=0; i<n; i++) should be for (int i=0; i<n/2; i++) {n/2}


 
## Zadanie domowe 4
Znajdź błędy za pomocą gdb w programie wielomian.c

Rozwiązanie

    ulimit -c 1024
    g++ -g wielomian.c -o wielomianT
    
    powinny być flout zmienne
    
    dla zmiennych 0 0 0
    frame 12 43
    
    Signal = SIGFPE (Arithmetic exception)
    a = {int} 0
    b = {int} 0
    
    dla zmiennych 0 2 2  a nie moze byc = 0 dla x^2
    
    Podaj a: 0 2 2
    Podaj b: Podaj c: Podaj a: Sa dwa rozwiazania rowne: 
     x1=-nanx2=-inf, 
    X jest rowne: -1 
    
## Zadanie domowe 1
Wersja release to ta, w której program jest dostarczany użytkownikowi. Plik programu jest zoptymalizowany pod względem rozmiaru i/lub szybkości działania. Można sterować stopniem optymalizacji gcc m.in. za pomocą opcji -OX, gdzie X jest liczbą większą lub równą 0. Większa liczba oznacza włączenie większej liczby optymalizacji (co nie zawsze skutkuje szybszym kodem). 0 oznacza wyłączenie optymalizacji.
Opcja -g w gcc powoduje dołączenie do wynikowego pliku wykonywalnego informacji debugowych, takich jak np. odpowiedniość między instrukcjami programu a liniami w kodzie źródłowym. Debugowanie programów skompilowanych z tą opcją jest dużo łatwiejsze.
Mając core dump programu skompilowanego bez informacji debugowych może się pojawić pokusa, aby skompilować program jeszcze raz z opcją –g i wykorzystać go w gdb do analizy pliku core. Trzeba jednak mieć na uwadze, że kompilator może generować inny kod, kompilując z opcją –g, w związku z czym nie musi on odpowiadać plikowi core. W takich sytuacjach należy powtórzyć wystąpienie błędu w programie z informacjami debugowymi.
Polecenie strip jest przydatne do usuwania z plików binarnych informacji o symbolach i informacji debugowych. Aby zaoszczędzić rozmiar uruchamianego pliku wykonywalnego można użyć go na pliku będącym efektem kompilacji z opcją -g. Mając core dump takiego programu możemy ponownie przekompilować go z opcją -g i używać do analizy pliku core.
Zadanie: W katalogu  objdump  dana jest wykonywalna binarka bez informacji debugowych i core dump z niej. Mając źródło programu należy powiedzieć, w której funkcji (najchętniej) program zakończył działanie. Przydatne polecenie:
    
    objdump -d -M intel <plik> 

Rozwiązanie

    tablica