# Conversational Intelligence

<p>Rozwiązanie Voicelab.ai Conversational Intelligence to nowoczesny system umożliwiający automatyczną transkrypcję, analizę, kategoryzację i kontrolę nagranych rozmów. Dzięki najnowszym technologiom z dziedziny rozpoznawania mowy i uczenia maszynowego zapewnia on wysoką skuteczność transkrypcji oraz weryfikacji zgodności rozmowy ze zdefiniowanym scenariuszem, jak również pozwala na odkrywanie trendów i nowych tematów pojawiających się w interakcjach.</p>

## Główne funkcjonalności
<p>System działa zarówno w trybie online jak i offline. 
W zależności od potrzeb klienta oferujemy możliwość integracji potrzebnej do działania systemu. Jako offline rozumie się ładowanie rozmów historycznych - po znalezieniu się danej rozmowy w kolejce nagrań do przetworzenia rozmowa jest zaimportowana do systemu. Jako online rozumie się przetwarzanie na żądanie wybranych przez użytkownika rozmów w postaci ustalonych wcześniej kanałów które są przesyłane w realtime.
System umożliwia integrację z narzędziami BI poprzez REST API.
Zarządzanie biznesowe funkcjonalnościami dostępne jest poprzez interfejs WEB.
System, na podstawie rozmów wideo, analizuje głos Agenta oraz Klienta i na tej podstawie dokonuje dalszej oceny tak jak w przypadku zwykłego połączenia Voice. 
Wymaganie jest spełniane, jeżeli pliki pochodzące ze źródła video będą dostarczone w formacie audio do analizy. To znaczy, że system działa i dokonuje dalszych analiz jak w przypadku zwykłych połączeń.
System daje możliwość pozyskiwania informacji o stanie parametrów systemu, których rozumienie i lista jest uzgodniona (logi, zdarzenia systemu itp.).
System udostępnia alertowanie – to znaczy zdefiniowane wcześniej kryteria powiadamiania użytkowników (np. supervisorów) o zwiększeniu trendu w danej kategorii lub zdarzeń w karcie oceny.</p>

## Wykorzystywane technologie

###	Automatic Speech Recognition – ASR

<p>Podstawową technologią wykorzystywaną w produkcie VoiceLab CI jest Automatyczne Rozpoznawanie Mowy, w skrócie – ASR (ang. Automatic Speech Recognition). Pozwala ona na automatyczną zamianę mowy na tekst, czyli transkrypcję.</p>

### Moonlight LVCSR

<p>Moonlight LVCSR jest wysoko wydajnym dekoderem rozpoznawania mowy ciągłej. System wykorzystuje metody uczenia maszynowego m.in. głębokie sieci neuronowe (ang. Deep Neural Networks). Moonlight LVCSR jest rozwiązaniem niezależnym od mówcy.Dekoder przetwarza strumień audio zwracając w wyniku rozpoznawania tekst. Wymawiane słowa dzielone są na sekwencję podstawowych jednostek mowy – fonemów. Model akustyczny reprezentuje zależności pomiędzy sygnałem akustycznym a fonemami. Ciągi fonemów dopasowywane są do słów zawartych w modelu języka, z uwzględnieniem prawdopodobieństwa występowania po sobie danych wyrazów, na przykład: „to będzie miły dzień” jest bardziej prawdopodobne niż „to będzie miły cień”.</p>


### Solr

<p>Apache Solr jest bazą pełno-tekstową, która przechowuje dane oraz metadane z nagranych rozmów. Bardzo wydajnie obsługuje funkcje wyszukiwania dużych zasobów tekstowych. Solr jest rozwiązaniem wysoce niezawodnym, skalowalnym horyzontalnie i odpornym na uszkodzenia dzięki mechanizmom replikacji indeksu.
Dzięki wykorzystaniu technologii Apache Solr, wyszukiwarka w systemie Voicelab.ai Conversational Intelligence pozwala na tworzenie złożonych zapytań z uwzględnieniem treści transkrypcji oraz wielu metadanych i uzyskanie szybkich i trafnych wyników wyszukiwania.
</p>

### Lematyzacja
<p>System VoiceLab CI zawiera moduł lematyzacji. Lematyzacja to proces wyznaczania dla każdego słowa w tekście opisującej je jednostki ze słownika morfologicznego – leksemu. W potocznym znaczeniu jest to sprowadzenie słowa do jego „podstawowej” formy gramatycznej. Dla czasownika taką formą będzie bezokolicznik, dla rzeczownika – mianownik liczby pojedynczej. 
Dzięki zastosowaniu lematyzacji, użytkownik systemu podczas tworzenia zapytania tekstowego nie musi podawać wszystkich możliwych form gramatycznych słowa. </p>

## Podstawy składni zapytań

<p>Poza podstawowym wyszukiwaniem, opartym na prostym sprawdzeniu, czy dane słowo występuje w tekście, Solr pozwala m.in. na:
</p>
<ol>⦁	wyszukiwanie w otoczeniu – poprzez symbol ~N (gdzie N to liczba) możemy określić, ile maksymalnie słów może znaleźć się pomiędzy dwoma wyszukiwanymi słowami, na przykład:
```bash
„jak pomóc”~2
```
odnajdzie „jak mogę pomóc” i „jak mogłabym pani pomóc”, ale nie „jak mogłabym dzisiaj panu pomóc”.
</ol>
<ol>⦁	określanie zakresów dla wartości liczbowych – poprzez nawiasy klamrowe dla nierówności ostrych (<, >) i kwadratowe dla nierówności nieostrych (≤, ≥), na przykład:
```bash
metadana:[50 TO 60]
```
odnajdzie dokumenty, dla których wartość podanej metadanej jest większa lub równa 50 i mniejsza lub równa 60.
</ol>
<ol>⦁	użycie operatorów logicznych AND (lub znaku +), NOT (lub znaku –) i OR (domyślnie - brak znaku) dla każdego elementu zapytania, na przykład:
```bash 
+„jak pomóc”~2 +”dzień dobry”
```
odnajdzie „dzień dobry jak mogę panu pomóc” ale nie „witam jak mogę panu pomóc”, natomiast:
```bash
+„jak pomóc”~2 ”dzień dobry”
```
odnajdzie zarówno „dzień dobry jak mogę panu pomóc”, jak i „witam jak mogę panu pomóc”.
</ol>











