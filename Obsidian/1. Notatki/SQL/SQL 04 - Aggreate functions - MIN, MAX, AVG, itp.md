1.1 #Aggregate functions
![[Pasted image 20241108113349.png]]
![[Pasted image 20241108113411.png]]
1.2 Możemy tych funkcji używać do danych numerycznych oraz do nie numerycznych.
![[Pasted image 20241108113511.png]]
![[Pasted image 20241108113546.png]]
Przykłady:
![[Pasted image 20241108113611.png]]
Dobrą praktyką jest używanie aliasów:
![[Pasted image 20241108113641.png]]

2. #Using WHERE with aggregate functions
![[Pasted image 20241108113803.png]]
![[Pasted image 20241108114100.png]]
3. #ROUND() - zaokrąglenie
3.1 Zaokrąglenie do określonego miejsca po przecinku.
![[Pasted image 20241108114157.png]]
3.2 Zaokrąglenie całej liczby
![[Pasted image 20241108114324.png]]
3.3 Zaokrąglenie z negatywnym parametrem
![[Pasted image 20241108114445.png]]

4. #Aliasing and arithmetic
4.1 #Dostępne operatory.
![[Pasted image 20241108114608.png]]
Domyślnie jest to typ int dlatego takie wyniki, możemy mieć flouty:
![[Pasted image 20241108114722.png]]
4.2 #Jaka jest różnica pomiędzy funkcjami aggregatowymi, arytmetycznymi?
![[Pasted image 20241108114829.png]]
Pierwsze działają pionowo, drugie poziomo.
Przykład:
![[Pasted image 20241108115059.png]]
Musimy zawsze używać aliasów do pokazania wyniku.
![[Pasted image 20241108115204.png]]
4.3 
![[Pasted image 20241108115242.png]]
