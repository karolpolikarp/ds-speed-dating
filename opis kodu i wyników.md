**1\. Kontekst Analizy i Cel**

Analiza została przeprowadzona na zbiorze danych pochodzących z wydarzeń speed dating, podczas których uczestnicy oceniali preferencje dotyczące potencjalnych partnerów oraz swoje zainteresowania. Początkowy zestaw (ok. 8 378 obserwacji) obejmował szeroki zakres informacji: od danych demograficznych (wiek, płeć, kierunek studiów) po preferencje dotyczące cech partnera (atrakcyjność, inteligencja, szczerość, zabawność, ambicja, wspólne zainteresowania) oraz aktywności (sport, muzyka, teatr, kino).

**Kluczowe cele analizy:**

- Zidentyfikowanie segmentów użytkowników aplikacji randkowej Meeter w oparciu o ich preferencje i zainteresowania.
- Przedstawienie profili użytkowników w sposób zrozumiały dla zespołu marketingowego, aby skutecznie zaplanować targetowaną kampanię promocyjną.

**2\. Przygotowanie i Przetwarzanie Danych**

- **Redukcja wymiaru:** Dane zawierały pierwotnie blisko 200 zmiennych, jednak do analizy klastrowej wybrano kluczowe cechy związane z preferencjami i zainteresowaniami (łącznie 10 zmiennych: 6 związanych z preferencjami, 4 z zainteresowaniami).
- **Normalizacja preferencji:** Ponieważ preferencje uczestników były wyrażone w różnych skalach, dokonano ich normalizacji, w różny sposób zależności od przypadku, do zakresu 1-10.
- **Czyszczenie danych:** Z puli 8 378 obserwacji usunięto duplikaty i rekordy niekompletne w wybranych zmiennych. Ostatecznie do analizy klastrowej pozostało 541 obserwacji (N=541), tj. 541 uczestników speed dating (z 551, 10 usunięto w procesie czyszczenia danych)
- **Uzupełnianie braków:** Brakujące dane liczbowo uzupełniono wartościami średnimi dla danej zmiennej, aby zminimalizować utratę informacji.

**3\. Metody Analizy**

- **PCA (Analiza Składowych Głównych):**  
   Zastosowano PCA, aby zredukować wymiarowość danych i zilustrować strukturę obserwacji. Dwie główne składowe wyjaśniły ok. 64% całkowitej wariancji. Choć nie jest to 80-90%, w praktyce już 64% pozwala na stosunkowo klarowną wizualizację i interpretację podziałów.
- **Klasteryzacja (K-Means):**  
   Przeanalizowano różne liczby klastrów (2-10) za pomocą wskaźnika silhouette. Najwyższy wynik silhouette uzyskano dla K=2 (wartość ~0,241), zaś K=3 dał wartość ~0,220. Ponieważ jednak zależało nam na bardziej zróżnicowanym podziale na grupy, ostatecznie zdecydowano o przyjęciu 3 klastrów. Podział na 3 grupy okazał się wystarczająco interpretable i przydatny z perspektywy marketingowej.
- **Liczebności klastrów:**
  - Klaster 0: 208 obserwacji (~38% uczestników)
  - Klaster 1: 178 obserwacji (~33% uczestników)
  - Klaster 2: 155 obserwacji (~29% uczestników)

**4\. Charakterystyka Zidentyfikowanych Grup**

Poniżej przedstawiono średnie oceny w kluczowych kategoriach. Preferencje dotyczą cech przyszłego partnera (wszystkie w skali 1-10), a aktywności (sport, teatr, muzyka, kino) w skali 1-10 odzwierciedlają stopień zainteresowania daną formą spędzania czasu.

**Klaster 0 - „Aktywni" (38%)**

- **Preferencje (średnie):**
  - Atrakcyjność: 2,21
  - Szczerość (sinc): 1,78
  - Inteligencja: 1,98
  - Zabawność: 1,68
  - Ambicja: 1,16
  - Wspólne zainteresowania (shar): 1,20  
     _(Preferencje dość zrównoważone, brak skrajnych wymagań, umiarkowany nacisk na różne cechy)_
- **Aktywności (średnie):**
  - Sport: 8,0
  - Teatr: 7,86
  - Muzyka: 8,41
  - Kino: 8,62  
     _(Bardzo wysoki poziom zainteresowania różnorodnymi formami spędzania wolnego czasu - od sportu po kulturę)_

**Interpretacja:**  
Grupa najbardziej eklektyczna. Osoby w tym klastrze chętnie angażują się w różne formy rozrywki i kultury. To segment otwarty na różnorodne aktywności - będą cenić wydarzenia łączące aspekty towarzyskie z kulturalnymi i sportowymi.

**Klaster 1 - „Intelektualiści" (33%)**

- **Preferencje (średnie):**
  - Atrakcyjność: 1,90
  - Szczerość: 1,77
  - Inteligencja: 2,17 (relatywnie najwyższy nacisk na inteligencję)
  - Zabawność: 1,73
  - Ambicja: 1,17
  - Wspólne zainteresowania: 1,26

_(Wyróżnia się wysoki priorytet inteligencji - najwyższy spośród wszystkich klastrów)_

- **Aktywności (średnie):**
  - Sport: 3,25 (znacznie niższy niż w pozostałych grupach)
  - Teatr: 7,79
  - Muzyka: 8,06
  - Kino: 8,30

_(Wyraźne nastawienie na kulturę i sztukę, mniejszy nacisk na aktywność fizyczną)_

**Interpretacja:**  
Osoby z tej grupy preferują spotkania i randki w otoczeniu wydarzeń kulturalnych (wernisaże, ambitne kino, dyskusje literackie). To segment wyrafinowany, ceniący wartość intelektualną i głębię rozmowy, a mniej zainteresowany aktywnościami sportowymi.

**Klaster 2 - „Imprezowicze" (29%)**

- **Preferencje (średnie):**
  - Atrakcyjność: 2,71 (najwyższa wśród wszystkich klastrów)
  - Szczerość: 1,62
  - Inteligencja: 1,90
  - Zabawność: 1,85
  - Ambicja: 0,86 (najmniejszy nacisk na ambicję)
  - Wspólne zainteresowania: 1,06

_(Najważniejsze są cechy "powierzchowne" i towarzyskie: atrakcyjność fizyczna, zabawność)_

- **Aktywności (średnie):**
  - Sport: 7,83
  - Teatr: 4,19 (znacznie niższe zainteresowanie kulturą wysoką)
  - Muzyka: 6,97
  - Kino: 6,53

_(Chętniej spędzają czas w rozrywkowy sposób, wolą luźne formy aktywności niż zaangażowane kulturalnie.)_

**Interpretacja:**  
Segment nastawiony na szybkie, przyjemne doświadczenia i dobrą zabawę, gdzie liczy się przede wszystkim atrakcyjność i miła atmosfera. To idealna grupa docelowa dla kampanii marketingowych podkreślających lifestyle, imprezy, koncerty i lekkie kino rozrywkowe.

**5\. Rekomendacje Marketingowe**

Na bazie powyższych charakterystyk przygotowano trzy różne profile działań marketingowych:

**Dla klastra 0):**

- Promuj wydarzenia łączące różne formy rozrywki: np. pakiety randkowe obejmujące krótki trening sportowy (fitness, squash), a następnie wyjście do kina lub teatru.
- Kanały: media społecznościowe, strony z wydarzeniami kulturalnymi i sportowymi.

**Dla klastra 1:**

- Skup się na ofertach w kinach studyjnych, spotkaniach literackich, klubach dyskusyjnych, ambitnych festiwalach muzycznych.
- Kanały: newslettery uczelni, portale kulturalne, niszowe grupy na Facebooku.

**Dla klastra 2 :**

- Promuj aktywne i lekkie formy spędzania czasu: imprezy klubowe, koncerty popularnych zespołów, eventy sportowe z afterparty.
- Kanały: Instagram, TikTok, influencerzy lifestyle'owi, sportowi.

**6\. Podsumowanie i Wartość Biznesowa**

Zidentyfikowano trzy wyraźne segmenty, które różnią się priorytetami i stylami życia. Zespół marketingowy może teraz kierować spersonalizowane komunikaty:

- **Aktywni (38%):** Największa grupa, otwarta na różnorodne doświadczenia.
- **Intelektualiści (33%):** Drugie co do wielkości grono, ceniące głębię i kulturę wysoką.
- **Imprezowicze (29%):** Mniejszy, ale wyraźny segment ceniący prostą, atrakcyjną i aktywną rozrywkę.

Dzięki takiemu podziałowi można efektywniej wykorzystać budżet marketingowy, przygotowując oferty i treści dopasowane do potrzeb każdej grupy, co powinno przełożyć się na większą satysfakcję użytkowników, wyższą retencję i skuteczniejszą konwersję.
