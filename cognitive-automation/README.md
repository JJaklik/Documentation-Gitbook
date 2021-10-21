# Cognitive Automation

Całościowa platforma do tworzenia chatbotów (po podłączeniu TTS/ASR, voicebotów), z własnym silnikiem NLU.

Rozmowa jest modelowana za pomocą grafu skierowanego:&#x20;

•Wierzchołkami są wypowiedzi bota (pytania do użytkownika, komunikaty) oraz interakcje z innymi systemami (np. wysłanie zebranych danych do formularza)&#x20;

•Krawędziami są między innymi intencje z ew. slotami.&#x20;

•Na podstawie rozpoznania NLU z puli wychodzących krawędzi wybierana jest następna krawędź prowadząca do nowego węzła&#x20;

•System prowadzi dialog w sposób synchroniczny&#x20;

•Istnieje możliwość bezpośredniego pytania o konkretną informację z pominięciem NLU&#x20;

•W przypadku Voicebota możliwość wyboru dedykowanej konfiguracji ASR w konkretnym miejscu

aktualnie rozwijany system został zaprojektowany w oparciu o koncepcję „microservice architecture”. Zapewnia do wysoką skalowalność i redundancję oraz ułatwi rozwój aplikacji •większość komponentów została napisała w języku Python, przy wykorzystaniu frameworku webowego FastAPI&#x20;

•do obsługi baz danych jest używany SqlAlchemy&#x20;

•cześć systemu odpowiedzialna za bezpośrednią obsługę frontendu została napisana w języku Golang\


## NATURAL LANGUAGE UNDERSTANDING

Jedna z dziedzin NLP, polegająca na zrozumienia języka ludzkiego przez maszynę w celu pozyskania konkretnych informacji. Silniki NLU są wykorzystywane między innymi jako główne komponenty inteligentnych botów, komunikujących się z ludźmi w możliwie naturalny dla człowieka sposób.

## Intencje

Rozpoznawanie intencji jest szczególnym przypadkiem klasyfikacji tekstu. System ma za zadanie przypisać, krótkiemu fragmentowi tekstu (max kilka zdań) etykietę z określonego wcześniej zbioru , oznaczającą intencje wypowiedzi. Przykładowo stwierdzeniu „chcę zrobić przelew w wysokości 100zł” można przypisać intencję elixir\_session. Poprzez wykrywanie intencji bot, może sterować rozmową i odpowiednio reagować na wypowiedzi użytkownika.

## SLOTY/ENCJE (SYSTEMY NER)

Named-entity recognition jest zagadnieniem klasyfikacji tekstu na poziomie pojedynczych wyrazów. Na podstawie kontekstu, struktury wypowiedzi system wydobywa konkretne informacje (nazywa encje).&#x20;

`Chcę zrobić przelew jutro w wysokości 100zł. `

System NER umożliwia pozyskanie przez bota informacji potrzebnych do realizacji wcześniej zaprogramowanych celów. Przykładowo bot musi zebrać dane do przelewu. Są tu wykorzystywane zarówno metody ML jak i klasyfikatory regułowe.

## NLU PIPELINE W CA

![](<../.gitbook/assets/CA diagram.PNG>)
