# Wyszukiwanie zaawansowane

Wyszukiwanie zaawansowane w zakładce Eksploruj \[Widok 10] umożliwia zaawansowane przeszukiwanie nagrań według ich treści oraz przypisanych do nich metadanych, a także wyszukiwanie po:&#x20;

⦁ zapytaniach, które można zapisać za pomocą przycisku Zapisz zapytanie, a także edytować, usuwać. Uwaga! Edycja zapytań wpłynie na zapytania wykorzystane w kategoriach!

&#x20;⦁ kategoriach utworzonych wcześniej w zakładce Zarządzaj → Kategorie,

&#x20;⦁ kartach oceny utworzonych wcześniej w zakładce Zarządzaj → Karty oceny,&#x20;

⦁ playlistach utworzonych wcześniej przez użytkownika w zakładce Eksploruj.

## Zapytania.

W polu wyszukiwania możliwe jest wpisanie dowolnego zapytania. Dzięki zastosowaniu lematyzacji, wpisanie słowa umowa wyszuka również odmiany takie jak np. umowę i umową. Domyślnym operatorem stosowanym przy wpisaniu więcej niż jednego słowa do wyszukiwania jest OR. Pozostałe obsługiwane operatory to AND i NOT. Operatory mogą być zagnieżdżane pomiędzy słowami oraz przy pomocy nawiasów okrągłych, przykładowo: rezygnować AND (pakiet OR internet) NOT nowy pozwala wyszukać rozmowy w których padło słowo rezygnować lub jego odmiany oraz słowo pakiet lub takie, w których padły słowa rezygnować i internet, ale nie padło słowo nowy lub jego odmiany

## Opcje wyszukiwania.

Wyszukiwanie można ograniczyć do wybranego przedziału czasowego oraz posortować według wybranej metadanej, używając pól wyboru dostępnych pod polem wprowadzania fraz. Poza wyszukiwaniem pojedynczych słów, możliwe jest również wyszukiwanie dłuższych fraz dzięki użyciu cudzysłowu, np. „przedłużyć umowę”. Pozwala to na wyszukanie wyrazów występujących obok siebie. Dobrym sposobem na uniknięcie pomijania wyników wyszukiwania, w których te słowa mogą paść w małej odległości od siebie jest dodanie po cudzysłowie znaku tyldy \~ i liczby, np. „przedłużyć umowę”\~3, wyszuka dwa zadane słowa nawet jeśli nie będą znajdować się bezpośrednio obok siebie, ale w odległości kilku, 2-3 słów. Nawiasy okrągłe służą do zagnieżdżania operatorów oraz podawania większej liczby warunków dla metadanych kategorialnych. Nawiasy kwadratowe służą do podawania zakresu dla metadanych zakresowych. Po rozwinięciu zaawansowanej wyszukiwarki, użytkownik ma początkowo dostępne cztery podstawowe metadane, które dotyczą każdego nagrania i nie można ich usunąć (można operować na ich przedziałach): okres, liczba słów, procent ciszy oraz czas nagrania. Za pomocą rozwijanego menu z wbudowaną wyszukiwarką. Użytkownik ma możliwość wyszukiwania innych metadanych, które zostały zaimportowane w systemie. Po wybraniu metadanej, jest ona dodawana do wyszukiwarki w formie filtru, którego rodzaj różni się w zależności od wybranego typu metadanej. Użytkownik może wykonać zapytanie klikając przycisk Szukaj. Wówczas zapytanie zostaje przekazane do Solr i lista zostaje aktualizowana o wyszukane nagrania. Pojedyncze nagranie zawiera podstawowe informacje o nazwie nagrania (podawanej przy imporcie), początku transkrypcji, długości nagrania, procencie ciszy oraz dacie.

## Składnia zapytań - elementy składni.

Elementy składni zapytań stosowane są do tworzenia zapytań. Zapytania mogą być użyte do tworzenia kategorii, stąd znajdują się tutaj elementy odnoszące się również do kategorii. Element OR, AND oraz NOT może być używany do łączenia zapytań między sobą w procesie tworzenia kategorii. Elementy składni dzielą się na odnoszące się do transkrypcji (T) i metadanej (M), co oznaczono jako typ. Składnię formułuje się poprzez użycie elementu oraz zmiennej.

## Zastosowanie elementów składni do tworzenia zapytań.

## Łączenie zapytań w kategoriach oraz stosowanie nawiasów.

## Wyszukiwanie po kartach oceny oraz playlistach.

##
