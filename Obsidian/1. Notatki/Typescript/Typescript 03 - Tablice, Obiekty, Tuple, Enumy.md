tsc -w - do automatycznej kompilacji pliku jeśli zajdzie jakaś zmiana

1. #Tablice
Możemy miksować różne typy w tablicach.
![[Pasted image 20241030084224.png]]
Jednakże jak próbujemy przyporządkować inny typ do typu, który jest zdefiniowany jako
domyślny w tablicy to typescript zgłasza błąd:
![[Pasted image 20241030084502.png]]
To samo za pomocą polecenia:
![[Pasted image 20241030084748.png]]Tutaj nie ma problemu ponieważ tablica może zawierać albo stringi albo numery:
![[Pasted image 20241030084909.png]]
Przypisanie tablic też powoduje błąd:
![[Pasted image 20241030085113.png]]Odwrotnie możemy:
![[Pasted image 20241030085159.png]]Definiujemy nową tablicę bands:
![[Pasted image 20241030085400.png]]

2. #Tuple
Definiujemy Tuple, czyli tablicę w której możemy zawrzeć wiele typów, np:
![[Pasted image 20241030085542.png]]Możemy przypisać do "Tuple" tablicę, której typy są zgodne z typami z Tupla:
![[Pasted image 20241030085719.png]]Jednakże odwrotnie już nie:
![[Pasted image 20241030085745.png]]Dzieje się tak dlatego, że mixed może zawierać więcej elementów, które nie będą spełniały wymogów Tupla.
To samo dzieje się, gdybyśmy chcieli przypisać do Tupla coś poza jego zakresem:
![[Pasted image 20241030090017.png]]
Nie mamy tutaj indeksu nr 3.


3. #Obiekty_w_Typescript
Deklaracja obiektu:
![[Pasted image 20241030090607.png]]
Tablica jest również obiektem i możemy jedno do drugiego przypisać
![[Pasted image 20241030090710.png]]
#[Konfiguracja tsconfig.json]
Ścieżki w konfiguracji `tsconfig.json`, takie jak `rootDir` i `outDir`, są zawsze interpretowane względem lokalizacji samego pliku `tsconfig.json`.

Drugi sposób deklaracji obiektu:
![[Pasted image 20241030094315.png]]
Przykład zainicjalizowanego obiektu:
![[Pasted image 20241030095308.png]]
Jednakże tutaj nie powiedzieliśmy wprost, że to jest obiekt. 
Typescript "domyślił, że to jest obiekt.

Jeśli chcielibyśmy wprost powiedzieć, że tworzymy obiekt to robimy to tak:
![[Pasted image 20241030095819.png]]
Tworzymy obiekt zgodnie ze wzorem:
![[Pasted image 20241030095940.png]]

![[Pasted image 20241030100249.png]]
Możemy dodawać opcjonalne property - za pomocą "?":
![[Pasted image 20241030100808.png]]
3.1 #Przekazywanie_obiektu_do_funkcji_jako_parametru
![[Pasted image 20241030101203.png]]"guitarist" to nadany tytuł dla przekazywanego parametru.

3.3 Type vs interface
Zmieniamy "type" na "interface".
(Bez znaku równości)
![[Pasted image 20241030101603.png]]
![[Pasted image 20241030101636.png]]
Robi to w zasadzie to samo i zależy od preferencji.
Jednakże jeśli mamy zamiar pracować z klasami to raczej stosujemy interface.

3.4 Narrowing with optional properties
![[Pasted image 20241030102017.png]]
Przestawmy "?" na "name".
![[Pasted image 20241030102113.png]]
i jeśli w takiej funkcji, gdzie powołujemy się na "name" 
![[Pasted image 20241030102153.png]]
za pomocą, np jakiejś metody - "toUpperCase()"
![[Pasted image 20241030102318.png]]
to będzie to powodowało błąd.
Jeśli natomiast zrobimy to jako opcjonalne "?" to błędu nie będzie:
![[Pasted image 20241030102445.png]]
Możemy również sprawdzić czy to istnieje:
![[Pasted image 20241030102631.png]]
4. #Enumy
Nie są one częścią Javascriptu, jednakże TS dodaje je w czasie runtime.
![[Pasted image 20241030102842.png]]
![[Pasted image 20241030102906.png]]
Dodaliśmy tylko "1":
![[Pasted image 20241030103001.png]]
, a pozostałe elementy uzupełniły się automatycznie:
![[Pasted image 20241030103058.png]]
