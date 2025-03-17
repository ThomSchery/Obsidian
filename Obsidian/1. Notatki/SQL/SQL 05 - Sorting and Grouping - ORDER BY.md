1. #ORDER BY - ustawiamy kolejność wyświetlania.
![[Pasted image 20241108115558.png]]
Jest to domyślne sortowanie, od wartości najmniejszej do największej (ascending order).
1.1 #ASC - Ascending order.
![[Pasted image 20241108115950.png]]
1.2 #DESC - Descending order.
![[Pasted image 20241108120018.png]]

![[Pasted image 20241108120134.png]]
1.3 #Sorting fields
1.4 #Dobrą praktyką jest również określenie wprost w SELECT pola służącego jako filtr.
![[Pasted image 20241108120336.png]]
![[Pasted image 20241108120355.png]]
![[Pasted image 20241108120432.png]]
1.5 #ORDER BY może również służyć do odfiltrowania wielu pól.
![[Pasted image 20241108120926.png]]
![[Pasted image 20241108120958.png]]
Przykład:
![[Pasted image 20241108121027.png]]
![[Pasted image 20241108121117.png]]
![[Pasted image 20241108121136.png]]
![[Pasted image 20241108121146.png]]
1.6 #Different orders - możemy dobrać odpowiedni sposób ułożenia dla każdego z pól za pomocą ASC - domyślne lub DESC.
![[Pasted image 20241108121409.png]]
Order of execution
![[Pasted image 20241108121433.png]]

2. Grouping data
2.1 #GROUP BY - Grupujemy i robimy na tym jakieś operacje. Czyli ustawiamy kolumny.
![[Pasted image 20241108123157.png]]
2.2 #GROUP BY jest często używany z aggregatowymi funkcjami. Jeśli dane pole było wyszczególnione w SELECT, ale później nie zostało wyszczególnione w GROUP BY to spowoduje ono błąd.
Musimy w takim przypadku użyć funkcji aggregatowej, aby temu zapobiec (title).
![[Pasted image 20241108123432.png]]
2.3 #Możemy pogrupować po wielu polach.
![[Pasted image 20241108124210.png]]
![[Pasted image 20241108124235.png]]
![[Pasted image 20241108124311.png]]
![[Pasted image 20241108124322.png]]
2.4 #GROUP BY z ORDER BY
![[Pasted image 20241108124635.png]]
Order of execution
![[Pasted image 20241108124927.png]]

3. Filtering grouped data
3.1 #HAVING (Filtering w grouping)
W SQL nie możemy filtrować funkcji agregujących z użyciem WHERE.
![[Pasted image 20241108132013.png]]
Musimy użyć HAVING.
![[Pasted image 20241108132226.png]]

![[Pasted image 20241108132311.png]]
![[Pasted image 20241108134103.png]]
3.2 #HAVING vs WHERE
![[Pasted image 20241108134233.png]]

![[Pasted image 20241108134320.png]]
Bardziej skomplikowany przykład:
#Musimy przeszukać po średniej, a funkcje agregujące nie mogą być używane z WHERE.
W związku z czym musimy użyć GROUP BY.
![[Pasted image 20241108134341.png]]

![[Pasted image 20241108134410.png]]
"Next, it asks for the average film duration, which tells us we need to place AVG(duration) somewhere.
Since we do not need to provide any additional information around the duration on its own, it is..."

![[Pasted image 20241108134527.png]]
"The last part of the question indicates we need to filter on the duration.
Since we can't filter aggregates with WHERE, this supports our theory about using HAVING!
Finally, we need to add a GROUP BY into our query since we have selected a column that has not been aggregated.
Recall the aggregate function will convert the duration values into one average value.
Going back to the start of our question, we're interested in...."
![[Pasted image 20241108134747.png]]


