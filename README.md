# Profilowanie użytkowników — segmentacja na danych speed dating 💘

Projekt data science: **segmentacja użytkowników** aplikacji randkowej na podstawie ich preferencji dotyczących partnera i zainteresowań. Celem jest wyłonienie wyraźnych grup docelowych i przełożenie ich na **rekomendacje marketingowe** zrozumiałe dla zespołu nietechnicznego.

Analiza powstała na klasycznym zbiorze *Speed Dating Experiment* i była realizowana jako projekt na przedmiocie UMBD (*Uczenie Maszynowe w Big Data*).

## Cel

- Zidentyfikować segmenty użytkowników (fikcyjnej) aplikacji randkowej **„Meeter"** w oparciu o preferencje i zainteresowania.
- Przedstawić profile grup w formie gotowej do zaplanowania **targetowanej kampanii promocyjnej**.

## Dane

- **Zbiór:** *Speed Dating Experiment* — dane z wydarzeń speed dating, na poziomie pojedynczego spotkania; ~8 378 obserwacji i blisko 200 zmiennych (demografia, preferencje cech partnera, zainteresowania).
- **Pliki w repo:** `Speed Dating Data.csv` (dane) oraz `Speed dating v4.pdf` (słownik/klucz zmiennych). W notebooku dane wczytywane są też bezpośrednio z dysku Google.

## Metodyka

1. **Wybór cech** — z ~200 zmiennych wybrano 10 kluczowych: 6 preferencji (atrakcyjność, szczerość, inteligencja, zabawność, ambicja, wspólne zainteresowania) i 4 zainteresowania (sport, teatr, muzyka, kino).
2. **Czyszczenie** — usunięcie duplikatów i rekordów niekompletnych → **N = 541** uczestników; imputacja braków średnią; normalizacja preferencji do skali 1–10.
3. **EDA** — automatyczny raport eksploracyjny (**sweetviz**), m.in. w podziale na płeć.
4. **PCA** — redukcja wymiarowości; dwie pierwsze składowe wyjaśniają **~64% wariancji** (wizualizacja 2D/3D, scree plot).
5. **K-Means** — dobór liczby klastrów wskaźnikiem **silhouette** (testowano k=2–10); ostatecznie przyjęto **k=3** jako najbardziej użyteczny marketingowo.

## Wyniki — 3 segmenty

| Segment | Udział | Charakterystyka |
|---|---|---|
| **„Aktywni"** | ~38% | Eklektyczni, wysokie zainteresowanie różnymi formami rozrywki i kultury (sport, muzyka, kino, teatr). |
| **„Intelektualiści"** | ~33% | Najwyższy nacisk na inteligencję partnera; nastawieni na kulturę i sztukę, niski sport. |
| **„Imprezowicze"** | ~29% | Liczy się atrakcyjność i zabawa; rozrywka lekka, niższe zainteresowanie kulturą wysoką. |

Dla każdego segmentu przygotowano osobne **rekomendacje kanałów i treści** (szczegóły i interpretacje w pliku [`opis kodu i wyników.md`](./opis%20kodu%20i%20wyników.md)).

## Pliki

| Plik | Opis |
|------|------|
| `UMBD_2324Z_profiling_speed_dating_users (3).ipynb` | Notebook z całą analizą (EDA → PCA → K-Means), narracja po angielsku. |
| `opis kodu i wyników.md` | Szczegółowy opis metodyki, charakterystyka klastrów i rekomendacje marketingowe (PL). |
| `Speed Dating Data.csv` | Zbiór danych. |
| `Speed dating v4.pdf` | Słownik zmiennych. |

## Uruchomienie

```bash
pip install pandas numpy scikit-learn matplotlib plotly sweetviz
```

Otwórz notebook w Jupyterze lub Google Colab i uruchom komórki po kolei.

## Tech stack

`Python` · `pandas` · `numpy` · `scikit-learn` (PCA, KMeans, silhouette, StandardScaler) · `plotly` · `matplotlib` · `sweetviz`
