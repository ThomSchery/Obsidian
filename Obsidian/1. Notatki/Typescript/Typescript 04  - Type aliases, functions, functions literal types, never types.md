1. #Type_Aliases
Możemy tworzyć tzw aliasy typów. Zmienne te mogą przyjmować dwa różne typy wartości.
![[Pasted image 20241031085742.png]]
Obiekt też jest aliasem.
strinOrNumber oraz stringOrNumberArray również.
Możemy zawrzeć aliasa w aliasie.

2. #Literal_types
Jest to specyficzne powiązanie, które nie może zostać zmienione.
![[Pasted image 20241031100833.png]]

Możemy #przypisać_alias_do_literałów_słownych, aby powiększyć ich użyteczność. 
![[Pasted image 20241031101206.png]]
3. #Funkcje
Musimy określić jakiego typu parametry muszą być zawarte w funkcji oraz
![[Pasted image 20241031101446.png]]
jaki typ funkcja zwraca:
![[Pasted image 20241031101604.png]]
Jeśli funkcja nic nie zwraca:
![[Pasted image 20241031104343.png]]
![[Pasted image 20241031104418.png]]
Możemy przekazać takiej funkcji "any" wszystko,
![[Pasted image 20241031104615.png]]
pod warunkiem, że nie kłuci się to z wymaganymi parametrami metody.
![[Pasted image 20241031104512.png]]
Przykład funkcji nie strzałkowej.
![[Pasted image 20241031111529.png]]
Różnica jest jedynie taka, że używamy słowa "function".
3.1 #Function Type Aliases
Możemy również stworzyć jakby interfejs dla funkcji, gdzie definiujemy parametry oraz to co ma zwracać. Ciało funkcji definiujemy w innej funkcji, której typ jest tym interfejsem.
![[Pasted image 20241031122457.png]]
Ciało funkcji czyli zastosowanie.
![[Pasted image 20241031122538.png]]
![[Pasted image 20241031122557.png]]
Jest podejście, które jest bardziej preferowane niż stosowanie interfejsów.
3.2 #Function Interfaces
Tutaj mamy przykład interfejsu funkcji:
![[Pasted image 20241031123511.png]]
Jednakże interfejsy są w domyśle powiązane klasą i z takimi intuicyjnie się wiążą.
3.3 Optional parameters. Opcjonalny parametr musi być ostatni na liście.
Te parametry są wymagane, ale możemy powiedzieć, że są opcjonalne.
![[Pasted image 20241031124001.png]]
Opcjonalne parametry:
![[Pasted image 20241031124153.png]]
Jednakże TS zgłasza błąd, że może być to "undefined"
![[Pasted image 20241031124251.png]]
Aby temu zaradzić wprowadzmy 'type guard'.
![[Pasted image 20241031124437.png]]
Jednakże znowu TS nie może zaakceptować takiego stanu rzeczy, ponieważ to nie jest jedyne możliwe zakończenie.
Musimy zdefiniować wszystkie możliwe przypadki:
![[Pasted image 20241031124618.png]]
3.3 #Default parameters.
![[Pasted image 20241031124830.png]]
Jeśli nie chcemy nadpisywać defaultowych parametrów to musimy w jawny sposób zadeklarować dany parametr jako "undefined"
![[Pasted image 20241031125210.png]]
Parametry są przekazywane do funkcji po kolei.
Nie działa to dla aliasów funkcji, tak jak to było tu:
![[Pasted image 20241031125351.png]]
3.4 #Functions with rest parameters - nie określamy ile tych parametrów jest. Musi być to umieszczone jako ostatni parametr.
Tutaj jest to zdefiniowane jako tablica
![[Pasted image 20241031125843.png]]
Możemy też zrobić coś takiego:
![[Pasted image 20241031130149.png]]
Metoda reduce:
![[Pasted image 20241031130323.png]]
3.5 #Never types

![[Pasted image 20241031130642.png]]
Widzimy, że ta funkcja zwraca typ "never".
![[Pasted image 20241031130724.png]]
I to jest typ dla funkcji, które w sposób jawny wyrzucają błąd.

Dla funkcji z nieskończoną pętlą też będziemy mieć ten typ.
![[Pasted image 20241031130924.png]]
Trzeba zawsze wywołać komunikat o błędzie jeśli będziemy mieć ten typ.
Czyli:
![[Pasted image 20241031131039.png]]
Zastosowanie:
Mamy taką funkcję:
![[Pasted image 20241031131333.png]]
String jest podkreślony, a wszystkie możliwości zostały zdefiniowane. O co chodzi?
Funkcja nie ma returna oraz nie odpowiada w przypadku "undefined".
![[Pasted image 20241031131508.png]]
Jako return definiujemy komunikat o błędzie:
![[Pasted image 20241031131700.png]]
3.6 #Custom Type Guard
Zabezpieczamy się, aby wartość zwracana był określonego typu za pomocą "typeof" oraz operatora "?" jeśli true to true, jeśli false to false.
![[Pasted image 20241031132418.png]]Modyfikacja wcześniejszej funkcji:
![[Pasted image 20241031132506.png]]
