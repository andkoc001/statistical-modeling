# Modelowanie statystyczne
dr hab. Elżbieta Kubińska
tel. 600391111 
elkubinska@gmail.com
kubinska@uek.krakow.pl

========
Wideo 1., Wykład #1 z 04.11.2023


## Pojęcia wstępne
- Pojęcia wstępne
- Statystyka opisowa
- Wnioskowanie statystyczneMetoda naukowa i falsyfikowalność
- Wprowadznie do metod ilościowych
- Pojęcie, rola i domena statystyki
- Statystyka stosowana
- Procedura statstyczna
- Populacja, próba, zmienna
- Szereg czasowy (próby/obserwacje zależne) 
- Dane przekrojowe (np. dla tego samego przedziału czasowgo; obserwacje niezależne)

## Metody statystyki opisowej
- Skale statystyczne
- Porządkowanie i grupowanie danych
- Tendencja centralna
- Zmienność
- Standaryzacja danych, rozkład normalny
- Korelacja a przyczynowość
- Regresja, predykcja, klasyfikacja
- Podsatwowe opisowe modele regresji

## Metody statystyki matematycznej
- rachunek prawdopodobieństwa i jego znaczenie dla badań statystycznych
- wnioskowanie statystyczne
- dobór losowy do próby
- testowanie hipotez statystycznych
- interpretacja wyników, błędy I (FP) oraz II rodzaju (FN); https://statystykawpsychologii.blogspot.com/2020/11/bedy-i-i-ii-rodzaju.html
- moc testów statystycznych
- weryfikacja różnic między dwiema grupami niezależnymi
- weryfikacja różnic między dwiema grupami zależnymi
- wnioskowanie o korelacji
- wnioskowanie o częstości
- wnioskowanie między trzma i większo liczbą grup
- model ANOVA
- testy nieparametryczne

### Poziom istotności i poziom ufności
- Poziom istotności (α) jest ustalonym poziomem ryzyka błędu pierwszego rodzaju (błędu alfa, False Positive)
- istnieje ryzyko α popełnienia błędu, czyli odrzucenia prawdziwej hipotezy zerowej (H0), gdy ta hipoteza jest prawdziwa.
- 95% - poziom ufności, 5% - poziom istotności -> np. w przypadku estymacji przedziałowej 36%+-2%, na 95% obserwacja zmieści się w tym przedziale
- Poziom ufności = 1 − Poziom istotności
- poziom ufności 95% oznacza, że prawdziwy parametr populacji znajduje się w danym przedziale ufności.

## Cechy metody naukowej
- falsyfikowalność - jeśli czegoś nie można zweryfikować to nie jest to naukowe -> trzeba formułować proste pytania badawcze, znaleźć odpowiednie pytania i odpowieć na nie
- obiektywizm - wyniki uzyskane metodą naukową są powtarzalne, przez każdego
- moc przwewidywawcza - staje się podstawą do tworzenia modeli

## Metody ilościowe
- ogół metod badwczych, w których badane zjawiska opisywane są parametrami liczbowymi
- oparte o dorobek naukowy nauk matamatycznych
- ich wykorzystanie poprzedzone powinno być rozpoznaniem istoty zjawiska z wykorzystaniem metod jakościowych

## Statystyka
- nauka o: a) klasyfikowaniu, b) porządkowaniu, c) analizowaniu danych
- nauka o ilościowych metodach badania zjawisk procesów masowych

## Statystyka opisowa
- Statystyka opisowa - działa na próbie (same dane, bez inrepretacji)
- zbiór metod służących do opisu danych zebranych podczas badania
- jej celem jest porządkowanie i podsumowanie obserwacji w celu ich łatwiejszego zrozumienia

## Wnioskowanie statystyczne
- Wnisoskowanie statystyczne - na podstawie próby o całej populacji


===
wideo 2, wykład #1 z 04.11.2023

## Pojęcia uniwersalne
- Populacja - całkowity zbiór obserwacji na dany temat (definiowany przez badacza)
- Próba podzbiór populacji; dobór ściśle determinowany pryncypiami statystycznymi  
- Parametr - opisowy wskaźnik populacji, np. średnia populacji 'mi', odchylenie standardowe 'sigma', wariancja 'sigma kwadrat'; rozkłady prawdopodobieństwa etc
- Statystyka - opisowy wskaźnik próby, np. średnia próby 'x z kreską', albo 's', wariancja 's kwadrat'

- Cechy - (co, gdzie, jak) na poziome populacji; podlegają badaniu
- Rozkład cechy - rozkład zmiennych losowych (np. liczba osób które przeszły na emeryturę w poszczególnych latach, albo rzut monetą, albo ryzyko inwestycyjne) 
- Cechy zmienne jakościowe (niemierzalne): dwudzielne, wielodzielne
- Cechy zmienne ilościowe (mierzalne): skokowe, ciągłe, quasi-ilościowe (np. taka sama ilość przypadków w każdym kubełku)

- W przypadku zmiennych losowych dyskretnych, operujemy na prawdopodobieństwie każdego przypadku {xi, pi}
- W przypadku zmiennych losowych ciągłych, operujemy na przedziałach gęstości rozkładu prawdopodobieństwa

===
Wykład #2 z 04.11.2023

# Skośność
- jeżeli >0 rozkład prawstronny (ogonek z prawej); <0 rozkład lewostronny a, ~0 symetryczny
- Test istotności wsp. asymetrii: H0 czyli skośność ~0 (nieistotne stat.) lub H1 czyli skośność różna od 0 (istotna)

```
import scipy.stats as stats
data = [1, 2, 3, 4, 5, 5, 6, 7, 8, 9]
skewness = stats.skew(data)
significance_level = stats.skewtest(data).pvalue
print(f"Skewness: {skewness}")
print(f"Significance Level: {significance_level}")
```

# Średnia
- miara tendencji centralnej
- przedział ufności = średnia +- poziom ufności (zakres występowania na 95% (taki jak poziom ufności))

# Prawo trzech sigm
- dla rozkładów zbliżonych do normalnego (dla innych może nie mieć sensu)
- Rozkład standardowy, tj. rozkład o średniej (mi) = 0 oraz odchyleniu standarowemu (sigma) = 1
- jedna sigma => mi +- 1*sigma (prawdopo. = 68%)
- trzy sigma => mi +- 3*sigma (prawdopo. = 99.7%)


===
 Wykad 3 17.12.2023

## typy danych:
- nominalne -> wskaźniki struktury (procentowe), dominanta - rozkład wiernie odtwarza  strukturę zbiorowości - można je tylko ustawić w porządku (?)
- porządkowe -> wskaźnieki struktury, dominanta, percentyle - rozkład wiernie odtwarza  strukturę zbiorowości
- przedziałowe i ilorazowe -> wskaźniki stru., dominanta, percentyle, średnia i odch. std. - rozkład w pyrzybliżeniu (tylko) odtwarza strukturę zbiorowości 
a) o ile coś jest większe, nie ma zera absolutnego, np. temperatura w st.C (nie można powiedzieć, że jest 3x cieplej)
b) ile razy coś jest większe, jest zero abs., np zarobki
 
## Klaskyfikacja skal (patrz zrzut ekranu (17.12.2023, 08:20)): 
- nominalna (identyfikacja, nie można ich dodawać, mnożyć, porównywać), np płeć, kolor, województwo 
- Porządkowa (ranking), np subiektywna ocena samopoczucia
- Przedziałowa (ma sens dodawanie, ale nie mnożenie (nie ma zera absolutnego), np rano było -5C a teraz 10C), np temperatura; y=ax+b
- Ilorazowa (ma sens powiedzieć, że ktoś jest dwa razy wyższy; jest zero absolutne), np wzrost, temperatura w K; Y=ax

## Korelacja (wsp. korelacji)
- miara siły związku między dwiema zmiennymi
- mówi o współwystępowaniu zmiennych, ale nie przyczynowośći
- przyjmuje wartości <-1,1>
- może być dodatnia, jeżeli x i y rosną razem
- ujemna, jeżeli z rosnącym x, y maleje
- test istotności korelacji (czy uzyskana wartość korelacji świadczy o współzależności)
- dla różnych typów danych (nominalne, porządkowe, ilorazowe), są różne sposoby wyliczania korlacji (w excelu - Pearsona, tj. dla cech ilorazowych)
- ujemna korelacja między dwoma walorami - zmniejsza ryzyko inwestycji (dywersyfikacja)
- czy korelacja Pearsona (r) podniesiona do potęgi to wsp. determinacji (R^2), czyli r^2 = R^2 


## Korelacja Pearsona (r):
- Mówi o współwystępowaniu zmiennych
- Mierzy siłę i kierunek liniowej zależności między dwiema zmiennymi.
- Przyjmuje wartości z zakresu od -1 do 1; gdy ~0 to brak zależności
- Nie mówi nic o tym, jak dobrze zmienne niezależne przewidują zmienne zależne.

# Współczynnik determinacji (R^2):
-Mierzy stopień, w jakim zmienne niezależne (predyktorzy) wyjaśniają zmienność zmiennej zależnej w modelu regresji.
- Przyjmuje wartości z zakresu od 0 do 1.
- R^2 jest kwadratem współczynnika korelacji (r), co oznacza, że jest to znormalizowana korelacja, podniesiona do kwadratu. R^2 = r^2
- F = MSR / MSE; rozkład F o stopniach swobody k oraz n-k-1, z którego wyznaczamy istotność F, czyli p-value (n to liczba obserwacji, k to liczba regresowrów, czyli zmiennych objaśniających)
- testowanie istotności R^2: H0: R^2 = 0, H1 != 0; jeżeli p-value (istotność F) < 0,05 to odrzucamy H0 na korzyść H1, czyli R^2 jest istotny, czyli model regresji jest istotny (poprawnie opisuje zjawisko)

## Kowariancja (cov)
- powiązane z korelacją
- przyjmuje dowolne wartości
- Kowariancja12 = Korelacja12 * odchylenie std.1 * odchylenie std.2
- kowariancja dla par skojarzonych
- korelacja (r) to wystandardowiona kowariancja (cov), tak aby wartości <-1,1>


## Regresja liniowa (na przykładzie danych finansowych)
- Wzór na stopy zwrotu Rt dla czasu t
    Rt = (Pt / Pt-1) - 1
    Pt - cena dla czasu t
- zmienna zależna, zmienna objaśniana, np. stopa zwrotu Orlenu dla kolejnych pomiarów
- zmienna niezależna, zmienna obhaśniająca, np. stopa zwrotu WIG dla koljejnych dni
- dopasowanie metodą najmniejszych kwadratów -> suma wszystkich błędów = 0 (albo suma kadratów błędów minimalna)
- dla danych finansowych:
    - wsp. kierunkowy (a) nazywany jest wsp. beta i oznacza ryzyko; jeżeli a (czyli beta) jest >1, to mówi się, że spółka jest agresywna
    - wsp. b: jeżeli > 0, mówimy, że spółka systematycznie bije rynek, a jeżeli < 0, to systematycznie radzi sobie gorzej od szerokiego rynku
- R-kwadrat - dle tylu procent zmiany cen Orlenu (y) są wyjaśnione zmianami indeksu WIG (x), tym modelem regresji liniowej
- Ryzyko Orlanu zalerzy w 43% od ryzyka rynku (WIG, czyli zmiany systematyczne, całego systemu)
- R-kwadrat to wsp. korelacji do kwadratu

- a, b - estymatory współczyników
- błędy standardow estymatorów Sa, Sb

- t-stat =  estymator / błąd standardowy tego estymatora; estymator to np. wyraz wolny (b)
- partość p
- test t-studenta (istotności współczyników)
- rozkład statystyki testowej np. rozkład t-studenta (stopnie swobody = n-2, gdzie n to liczba obserwacji)

- interpretacja finansowa, gdy b jest nieistotne (p-walue > 0,05) (czyli brak podstaw do odrzucenia H0?)- spółka Orland nie osiąga istotnie różnych wyników niż rynek 
    - jeżeli b > 0 Orlen bije rynek
    - jeżeli b < 0 Orlan systematycznie traci
    - R^2 interpretacja: procent w jaki zmienna objaśniająca wyjaśnia zmienną objaśnianą

- estymator przedziałowy (dolne 95%, górne 95%, itp) - oznacza, że współczynik wpadnie w ten przedział z danym prawdopodobieństewem (95% w tym przypadku)

- Błąd standardowy - uśredniona odchyłka reszt błędów (?); im mniejsze tym lepiej

- MS (mean square), np. MSE(błędu), MSR(regersji) 

- rozkład F (Fishera), Istotność F
    - istotność wsp. determinacji (R^2)
    - F = MSR/MSE
    - rozkład F ma dwa stopnie swobody: 1) df = k oraz 2) df = n-k-1

- model regresji (R^2) jest tym lepszy, im istotność F jest mniejsza 

=======
Wykład 13.01.2024

# Dane 

- Korelacje lub kowariancje powinny być ~ 0 (tzn. coś tam nie istotne)
- Odchylenie standardowe rozkładów powinny być takie same
- homo- hetero skedastyczne
- homoskedastyczność - stałość wariancji skłądnika losoweg (Et ~ N(0, sigms))

# Regresja
- Znaleść równanie regresji liniowej y = ax + b + Et
- Znaleźć współczynnik kierunkowy (a)
- Jeżeli (a) jest większa niż 1, mówimy, że spółka jest agresywna (zachowuje się agresywnie względem rynku (WIG)))
- Jeżeli x rośnie o jednostkę, to y rośnie o (a) - interptetacja wsp kierunkowego
- Wyraz wolny (b), nazywany w excelu 'przecięciem'
- Sprawdzamy czy (b) jest < 0 lub > 0
- Jeżeli (b) jest istotnie > 0, mówimy, że spółka systematycznie bije rynek, a jeżeli (b) istotnie < 0, mówimy, że ma systematyczne straty
- Et (epsilon, błędy), mają rozkład w przybliżeniu normalny: Et ~ N(0, sigma), czyli wartość oczekiwana (mi) = 0, a błąd standardowy błędów (sigma = sigma)
- Et ma cechy i.i.d. (independent, identical, normally distributed) - to jest sprawdzane testem serii
    - independent oznacza, że korelacje lub kowariancje są bliskie 0 (a więc są nie istotne) (korelacja/kowariancja bada zależności między błędami)
    - identical oznacza, że pochodzą z takich samych rozkładów normalnych, a więc błędy standarowe powinny być takie same
- standaryzacja (czyli mi=0, sigmma=1) wartości reszt Ei: Ei(std) = (Ei - mi) / sigma

- R-kwadrat (wsp. determinacji)
- R-kwadrat = SSR / SST  <- ułamek zmienności całkowitej wyjaśniona przez model (np. zmienność stóp zwrotu (ryzyko) Orlenu wyjaśniona przez model WIG w 43.41%)
- R-kwadrat daje możliwość estymacji błędu dla pomiaru (E = yi - y)

- Zmienność całkowita (SST) - ogólna zmienność danych, SST = sum((yi - yśr)^2) (wartość z obserwacji - wartość średnia (y z kreską płaską))
- Zmienność regresji (SSR) - mierzy zminność, (wyjaśnianych przez model), SSR = sum((yr - yśr)^2) (wartość obliczona z modelu - średnia)
- Zmienność błądów (SSE) - mierzy zmienność błędów modelu, SSE = sum((yi - yr(^2) (pomiar - odczyt z modelu regresji (y z daszkiem))
SST = SUM((yi - avg(y))^2), gdzie yi - indywidualna wartość obserwowana, dla SST df = n-1
SSR = SUM((yj - avg(y))^2), dla SSR df = liczba regresorów (zmiennych) (k)
SSE = SUM((yi-yj)^2), gdzie yj - to wartość przewidywana przez model dla każdej obserwacji, dla SSE df = n-k-1
SST = SSR + SSE
R^2 = SSR / SST, czyli ułamek zmienności całkowitej wyjaśniony przez model, np zmiennośð stóp zwrotu (ryzyko) Orlenu przez zmienność stóp WIG (w procentach)

MST / MSR / MSE - średnie sumy całkowite / regresji / błędów; odpowiednie MS = SS / odpowiednie df, np MST = SST/n-1

- Liczba stopni swobody (regresja ma tyle df ile ma zmiennych; natomiast df resztkowy - ilość obserwacji?)

# Test istotnośći współczynników
- Ogólny schemat postępowania (np test istotności współczynników)
1 hipotezy (H0 i H1)
2 statyka testowa (t-stat = -0,76786)
3 rozkład statystyki testowej (rozkłd statystyki testowej t-studenta o df=308)
4 Decysje na podstawie 2 i 3 (alfa = 0,05)
 a) zbiór krytyczney - jeżeli należy, wtedy odrzucamy H0 na korzyść hipotezy alternatywnej; jeżeli statystyka 
 b) p-value - jeżeli statystyka (alfa - poziom istotności?) jest < p-value wtedy odrzucamy H0 na korzyść H1

# np. dla (b):
p-value (=0.443) > alfa (=0.05), czyli nie ma podstaw do odrzycenia H0, czyli b jest nie istotne, czyli, że Orlen nie bije systematycznie rynku 
# np. test istotności wyrazu wolnego (b):
H0: b = 0, H1 != 0, (jak jest równość, to test dwustronny, a dla nierówności (<, >), wtedy test jednostronny); następnie wyznaczamy statystykę testową (t-stat = b / std. err), określamy st. swobody (dla rozkładu t-studenta: df = n-2); określamy p-value i porównujemy je z wsp. istotności (alfa); jeżeli p-value > alfa (czyli jest poza obszarem krytycznym) to nie ma podstaw do odrzucenia H0 na korzyść H1, czyli b jest nieistotny.
# np. Czy R^2 jest istotny?
sprawdzamy F oraz istotność F -> H0: R^2 = 0, H1: R^2 != 0; F = MSR/MSE; rozkład F o st. swobody k oraz n-k-1 (dwa różne stopnie swobody?); sprawdzamy p-value: Jeżeli p-value < alfa (a więc w obszarze krytycznym, odrzucenia); to odrzucamy H0 na korzyść H1, stąd R^2 jest istotny, model jest istotny

# Analiza wariancji (ANOVA):
- metoda stat. do porównywania średnich wartości między trzema lub więcej grupami

- ANOVA analizuje zmienność w danych, rozkładając ją na trzy składniki: składnik związany z grupami (SSB), składnik związany z błędami (SSE) i ogólny składnik (SST).
- Statystyka testowa: ANOVA generuje statystykę testową F, która porównuje stosunek zmienności między grupami (SSB) do zmienności wewnątrz grup. Wyższa wartość F sugeruje większe różnice między grupami.
- F oraz istotność F (test istotności R-kwadrat - w jaki sposób model wyjaśnia R-kwadrat)
- F = MSR/MSE
- F ma dwa stopnie swobody
- dla F: H0 -> R-kwadrat = 0; H1 -> R-kwadrat != 0
# Jeżeli R-kwadrat jest nie istotny, to cały model jest nie istotny
- Wybieramy taki model, dla którego R-kadrat jest najbardizej istotny, czyli H0 jest najmocniejsza
# testowanie hipotez
- H0: Nie ma istotnych różnic między średnimi wartościami grup.
  H1: Istnieją istotne różnice między co najmniej jedną parą grup.
- Niska wartość p (zazwyczaj poniżej ustalonego poziomu istotności, np. 0,05) oznacza odrzucenie hipotezy zerowej. Jeśli wartość p jest niska, odrzucamy hipotezę zerową i przyjmujemy, że istnieją istotne różnice między przynajmniej jedną parą grup. Jeśli wartość p jest wysoka, brak jest statystycznie istotnych różnic między grupami.


===
Dopasowanie dodatkowych zmiennych do medelu (np. wibor)
- homoskedastyczność (i.i.d. (independent, identical, normally distributed)) - to jest sprawdzane testem serii

- Zbyt mało wartości dodatnich (powyżej lini regresji) świadczy, że błędy nie są niezależne, czyli zła postać analityczna modelu


# Regresja korokowa wsteczna 1:41:25
- Regresja wielowymiarowa, wielokrokowa
1- budujemy model dla wszystkich zmiennych niezależnych
2- eliminujemy zmienną niezależną, która jest najgorzej powiązana z Y (mierzone za pomocą testu t-studenta) H0 (wsp. nie istotny) H1 (wsp istotny); zależy nam, żeby H0 zostało, z jak największą siłą, czyli max p-value; czyli odrzucamy H1 lub H0 o najmniejszym(?) p-value
3- powtarzamy punkt 2-, aż zostaną w modelu zmienne o p-value < alfa= 5% (1:43:52)

Przykład dla Orlenu (nasza zmienna y), natomiast zmienne niezalene to (Wig, millenium, Azoty, ...)

- buduję model - Regresja
- identyfikujemy te zmienne o p-value jest największe (1:49:45) - wyrzucamy tą zmienną z modelu
- buduję model jeszcze raz
- wyrzucam zmienną z modelu o największym p-value, itd, aż do momentu, gdy wszystkie zmienne mają p-value < 0.05
- dla przygotowanych danych robimy nowy model


===
### Test statystyczne (część wnioskowania statystycznego)
- Mediana - miara tendencji centralnej, cecha pozycyjna, jest odporna na wartości nietypowe (outlayery)
- Tryb (dominanta) - wartość najczęściej przyjmowana
- Odchylenie standardowe (sigma = sqrt(wariancja^2))
- Wariancja - miara rozrzutu od wartości centralnej (oczekiwanej)
- Wsp. zmienności = średnia/odchylenie standardowe
- Rozstęp między kwartylowy = Q3 - Q1 = środkowe 50%
  (1 sigma = środkowe 68%; 2sig = 95%; 3sig = 99,7%)
- rozkład odwrotny: na podstawie wartośći prawdopodobieństwa -> wartość funkcji

- Obserwacje typowe a odstające (typowe wewnąrz przedziału, np 1sigma (wtedy 68%), a odstające: 100% - typowe (czyli 100% - 68% dla 1sigma))

===
### hipotezy
- Hipotezy mogę dotyczyć np. testu danych z 2006 vs 2022; np. H0: średnia z 2006 jest taka sama jak z 2022, lub H1: są różne (wtedy test dwustronny; dla testu jednostronnego znak nierówności zamianst równości; robimy albo jednostronne albo dwustronne)
- statystyka - wartość obliczona na podstawie próby
- rozkład statystki -> np. normalny, albo t-studenta
- alfa - poziom istotności testu, zwykle alfa=0,05; poziom istotności to prawdoposobieństwo błędu pierszego typu (FP)
- Budujemy zbiór (obszar na wykresie rozkładu?) krytyczny - zbiór o prawdopodobieństwie alfa
- Decyzje:
    a) "Odrzucamy H0 na korzyść H1"
    b) "Nie ma podstwa do odrzucenia H0"

- p-value - prawdopodobieństwo zbioru kryt. zbudowanego na statystyce (tj. w oparciu o próbę)
- prównujemy p-value z alfa:
    - jeżeli p-value > alpha, wtedy nie ma podstaw od odrzucenia H0
    - Jeżeli p-value < alfa, wtedy odrzucamy H0

- Dezycyzja na podstawie testów (np. p-value ~ alfa)

- Korelacje Pearsona (r)
- Różnica średnich wg. hipotezy: jeżeli = 0, to oznacza, że średnia z 2006 i 2022 są sobie równe
- statystyka testowa (t stat) 

- Rozkład t-studenta, podobny do normalnego (-inf, inf)
- Rozkład chi-kwadrat (0, inf)

- Test istotności współczynnika skośności A (wg. regóły kciuka, |A| < 0.5 oznacza rozkład symetryczny): H0: A=0 (nieistotny), H1!=0 (istotny)


=====
Lab 3, 27.01.2024

- Miary współwystępowania (zależą od typu cechy, np: zależna, nominalne, porządkowe, ilorazowe)

- Chi-kwadrat - do badania zgodności rozkłady (czy jest jak z rozkładu normalnego) lub do badania 

- Wsp. Cramera

- Wsp. eta
Co jest zmienną grupującą? zmienna ilorazowa

WSS - zmienność wewnątrz grupowa
BSS - bewtween 
TSS - total

- Korelacja rang Spearmana

- Tablice rozkładu serii

- Standaryzacja zmiennej

# Test serii
- H0 odrzucamy, gdy jest mało serii (seria to nieprzerwany ciąg plusów lub minusów) lub jest zbyt wiele serii (sprawdzamy z dwóch srton). To świadczy o złym doborze danych (27:31)
k - liczba serii
n - liczba obserwacji
- test dwustronny, tj. alfa = 0.025 i alfa = 0.975 -> odczytujemy z tablic k_0.025 oraz k_0.975 na przecięciu liczby plusów i liczby minusów, anastępnie porównujemy z liczbą serii (k) 
    - jeżeli k < k_0.025 lub k k_0.975 --> wtedy odrzucamy H0 na korzyść H1
    - jeżeli k <= k_kryt -> nie ma podstaw do odrzucenia H0, czyli dobór próby jest losowy

- tablice testu serii tylko do dla N <= 20, w przeciwnym razie -> trzeba zrobić standardyzacja rozkadu E(K)
- Test serii warto zrobić dla wartości jakie są, kwadratu i pierwiastka

- Obszar krytyczny, czyli obszar odrzucenia (hipotezy H0); jeżeli k należy do obszaru krytycznego - odrzucamy H0.

- p-value - wartość dystrybuanty w punkcie Z

- Test znaków 01:29:04   
    H0 w teście serii zakłada, że dane są rozłożone losowo, czyli nie ma żadnych istotnych wzorców, sekwencji czy skupisk wartości
    H1 dwie próby są różne  
?   H0 dwie próby są podobne (np rozkłądy) ()H0 oznacza, że układ (rozkład) jest losowy)
?   H1 dwie próby są różne 


- decyzja czy test jednostronny czy dwustronny



=====================

# Terminologia

### Statystyka
- na podstawie zredukowanej liczby danych (próby)
- wnioskowanie statystyczne, to wyciąganie wniosków o populacji na podstawie próby
- kategorie wnioskowania statystycznego: 
    a) miara tendencji centralnej: średnia, mediana, dominanta, 
    b) miara rozposzenia(?, spread): zakres/rozstęp, IQR (inter quartile range, tj. Q3-Q1), wariancja, ochylenie standardowe  

### Średnia dla populacji (μ), dla próby (x z kreską)
- For a population, the mean (average) is denoted by the Greek letter μ (mu) and is calculated by adding up all the values in the population and then dividing by the total number of values.
- For a sample, the mean is denoted by (\bar{X}) (read as "X-bar") and is calculated similarly, but you divide by the sample size ((n)).

### Mediana (me)
- Wartość środkowa, ale po uporządkowaniu
- Dla parzystej liczby obserwacji: obliczamy średnią aryt. z dwóch środkowych wartości

### Moda (inne nazwy: dominanta, tryb)
- wartość najczęściej występująca

### Wartość oczekiwana (EX)

### Funkcja gęstości prawdopodobieństwa (probability density function, pdf)
- np. rozkład normalny (Gaussa)
- całka z tej funkcji - w odpowiednich granicach - jest równa prawdopobieństwu wystąpienia zdarzenia
- rozkład prawdopodobieństwa

### Dystrybuanta (cumulative distribution function, cdf)
- prawdopodobieństwo skumulowane
- np. dla rozkładu normalnego, kształtem przypomina funkcję sigmoidalną

### Rozkład normalny
N(mi, sigma kwadrat)
- średnia (wartość oczkiwana) = mi
- odchylenie standardowe = sigma kwadrat

### Rozkład standardowy (standaryzowany)
N(0,1)
- rozkład o średniej = 0 
- odchyleniu standarowym = 1


### Wariancja (dla próby) - (s2) - miara rozrzutu
- dzielimy przez n-1
- obliczamy różnicę pomiędzy uzyskanymi wynikami a wyliczoną średnią, podnosimy te wyniki do kwadratu i sumujemy; następnie dzielimy otrzymany wynik przez liczbę wyników minus 1 (n-1).
- [ s² = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \bar{X})^2 ]
- wyrażona w jednostkach do kwadratu (stąd odchylenie standardowe)

### Odchylenie standardowe (dla próby) - ()
- pierwiastek z wariancji
- warażone w jednostkach (właściwych mierzonej cesze)
- średnia odległość od średniej arytm.

### Wariancja (dla populacji) (sigma)
- dzielimy przez n
obliczamy różnicę pomiędzy uzyskanymi wynikami a wyliczoną średnią, podnosimy te wyniki do kwadratu i sumujemy; następnie dzielimy otrzymany wynik przez liczbę wyników (n)
- [ \sigma² = \frac{1}{N} \sum_{i=1}^{N} (X_i - \mu)^2 ]

### Odchylenie standardowe (dla populacji)
- 

### mi - sigma oraz mi + sigma -> punkty przegięcia na rozkładzie normalnym
- mi - średnia
- sigma - odchylenie standardowe

### Wsp. zmianności (coef. var.)
- tylko dla zmiennych, które posiadają tzw. zero bezwględne, czyli zero oznacza brak, np. waga (ale już nie temp. w st. C; zero st. C nie oznacza braku temperatury)
coef.var = odchyl.std. / śred.arytm.
- może być wyrażone w procentach (lub <0,1>) 
- im bliższa zeru, tym mniej zróżnicowane pomiary
- przydatne do badań danych różnego typu (np. zarobki w dwóch firmach)

### Zakres / rozstęp
- max - min
- miara rozproszenia

### kwartyl (Q) 
- jest ich 4: Q0 (min), Q1, Q2 (mean), Q3 i Q4 (max) (a więc przedziały, po 25%)
- Q0 = min; Q2 = mi; Q4 = max
- Q3 - Q1 = IQR
- jest to statystyka pozycyjna

### kwantyl (k)
- jest to jakaś liczba (punkt na osi)
- 10% ???

### percentyl 
- 1%

### Skośność
~0 rozkład symetryczny
> 1 skośność prawostronna
< 1 skośność lewostronna

### Kurtoza (eng. kurtosis)
- bada czy rozkład jest płaski, czy stromy
- jeżeli histogram odzwierciedla rozkład normalny, wtedy kurtoza = 0
- jeżeli histogram słupek (słupki) centralne wykraczają poza linię rozkładu normalnego, wtedy kurtoza > 0 (rozkład leptokurtyczny, czyli wąski i wysoki, skupiony)
- jeżeli histogram słupek (słupki) centralne poniżej linii rozkładu normalnego, wtedy kurtoza < 0 (rozkład platykurtyczny, czyli rozkład niski i szeroki; Wartości zmiennej są rozrzucone wokół średniej oraz mamy mniejsze prawdopodobieństwo spotkania wartości ekstremalnych)
- przyjmuje się, że jeżeli kurtoza > 0.5 lub < 0.5, wtedy rozkład nie przypomina rozkładu normalnego

### Poziom istotności (significance level), α
- Also known as alpha (α).
- Represents the probability of rejecting a true null hypothesis (Type I error (FP)).
- Common choices for significance level include 0.05, 0.01, etc.
- Lower significance levels indicate a lower tolerance for Type I errors.

- dla testu dwustronnego, bierzemy alfa/2 na obu końcach rozkładu (obszary krytyczne), wtedy H0 = ileś tam, H1 różne od tylu tam
- dla testu jednostronnego, bierzemy alfa na jednym z końców rozkładu (obszar krytyczny), wtedy dla testu prawostronnego H0 <= ileś tam i H1 > tylu tam; lub dla testu lewostronnego H0 >= ileś tam i H1 < tylu tam

### Poziom ufności (Confidence Level)
- It is associated with confidence intervals.
- Represents the range within which we are confident the true population parameter -lies.
- Commonly expressed as a percentage (e.g., 95% confidence level).
- Higher confidence levels correspond to wider intervals.
- Poziom ufnosci = 1 − α 
- zwykle poziom ufności = 0.95

### Przedział ufności (CI.mean.95 -> confidence interval for mean with 95% prob.)
- na tyle procent średnia znajdzie się w danym przedziale
- śred.arytm +- CI.mean.95 -> oznacza, że na 95% w tym przedziale znajdzie się średnia z całej populacji

### Obszar krytyczny (odrzucenia) 
- na obu końcach rozkładu

___

# Testy statystyczne

### t-test (z-test unikamy, choć podobne)
- dobre do testowania średniej dla jednej zmiennej (jednej próby)
- dobre do testowania proporcji (np. 45% próby woli kawe niż herbatę) dla jednej zmiennej (próby)

Dwie zmienne (dwie próby - np. grupa testowa i grupa kontrolna; nie zależne od siebie) do testowania średniej; czy średnia dla obu prób jest statystycznie taka sama (H0)

Dwa test dla tej samej próby (np. przed i po jakimś wydarzeniu) - próby są zatem zależne od siebie

### Test regresji
- czy jest korelacja między dwoma zmiennymi numerycznymi

### Chi-kwadrat
- sprawdzamy, czy jest relacja (korelacja?) między dwoma zmiennymi kategorycznymi

### ANOVA = N-sample independent test



======
### Projekt - do zrobienia

1. Dane - szereg czasowy
2. Obróbka wstępna
3. Wizualizacja danych - interpretacja i wnioskowanie
4. Agregacja danych, np. histogram - interpretacja i wnioskowanie
5. Statystyka opisowa (skośność), dla 3 przedziałów czasowych
6. Regresja krokowa wsteczna


# Model regresji danych ze stooq
Znaleść równanie regresji liniowej
Opisujemy zmienne (zależna i niezależna, tekże epsilony (błędy standardowe, 1:29:48)
Znaleźć współczynnik kierunkowy (a), (b) <- interpretacja
Test istotności współczynników a i b (opisujemy te testy) z komentarze dotyczącym przedziałów ufności dla 95%
Składniki resztowe (2:06:46) - te obserwacje, które wypadają poza +-2sigma (odstające); usuwamy te obserwacje z modely (dla wszystkich zmiennych)

# Analiza wariancji:
- R-kwadrat opisać
- R-kw interpretacja
- błąd std
- F oraz istotność F
- hipoteza

# W projekcie
- analiza danych (np. inwestycyjnych portfelowych) 
- źródło np. bank danych lokalnych (BDL), czyli GUS
- interpretacja, np. które województwa wymagają dofinansowania
- wybór cechy (np liczba szkół) wraz z opisem
- Powinna zawierać:
    - graficzne przedstawienie całgo dostępnego szeregu czasowego
    - Ostatnie dane do analizy wraz z dodatkowymi historycznymi, np. 5 i 10 lat wstecz
    - Histogramy dla 3 wybranych (okresów?)
    - Statystyki opisowe z interpretacją powiązaną z histogramami
    - omówienie statystyk
    - identyfikacja wartośći (np. województw/powiatów etc.) odstających od średniej z rekomendacją implementacji programów (np. dofinansowani)

# Interpretacja - odpowiedż na pytania
- Zidentyfikuj województwa, które odbiegają od średniej z województw (dla Polski ;)) o 2 odchylenia standardowe, czyle z prawdopodobieństwem 5%.
- testy i decyzja, na podstawie tabelki

Inspiracje:
- https://mateuszgrzyb.pl/3-metody-analizy-normalnosci-rozkladu-w-python/
- https://szufel.pl/python/


=======
### Egz

15 pytań teoretycznych: pytania z regresji, statystyki opisowej, testów z dwóch prób, i serii

- np. SST w jakimś teście wynosi tyle a tyle, co to znaczy
- Warunki formalne dla regresji liniowej (patrz zrzut z 20240113-120546.png):
    - związek między dwiema zmiennymi musi być związkiem linowym
    - liczba obserwacji większa lub równa liczbie szacowanych parametrów
    - istnieje homoskedastyczność, czyli stałość wariancji składnika losowego (rozkład błędów mają ~ rozkład normalny E = N(0, sigma))
    - brak autokoleracji reszt (czyli błędów? )
    - normalność rozkładu reszt 
    - brak współliniowości zmiennych (zmienne między sobę nieskorelowane)
- Weryfikacja merytoryczna modelu regresji:
    - weryfikacja istotności zmiennych (test t)
    - weryfikacja łącznej istotności (test F Fishera-Snedecora): istotności wspł. kierunkowego (a), istoności wspł. determinacji (R^2), istoności liniowgo związku między zmiennymi
    - weryfikacjia przez współczynnik determinacj R^2
- miary współwystępowania (korelacji) - metody wyznaczania dla typów cech (np. Pearsona dla ilorazowych, albo Spearmana dla rang)
- kryteria oceny inwestycji -> zyskowność (wartość oczekiwana stopy zwrotu) i ryzyko (wariancja, potencjalne odchylenie)

### zadania na egz
- Czy należy do przedziału ufności 95%? (56:22)
- Test istotności (współczynnika a) (53:37) 
















