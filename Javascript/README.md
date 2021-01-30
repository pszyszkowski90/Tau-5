### Czym jest Nightwatch.js?
Nightwatch.js to open-source'owy, oparty na node.js, framework do automatycznego testowania przeglądarek. Został on stworzony w Amsterdamie.
Nightwatch.js ułatwia testowanie end-to-end aplikacji webowych i stron internetowych, wykorzystując W3C Webdriver API (znany również jako Selenium Webdriver) jako Selenium wrapper do interakcji z różnymi przeglądarkami. Pomaga to znacznie ułatwić implementację CI/CD. Jednocześnie, może być używany do wykonywania automatyzacji testów Selenium zarówno dla testów jednostkowych jak i integracyjnych. Ten popularny framework do zautomatyzowanego testowania przeglądarek dostarcza kilka komend i asercji do wykonywania interakcji z elementami sieciowymi.

### Jak działa Nightwatch.js?
Nightwatch.js działa poprzez komunikację z WebDriverami różnych przeglądarek, takich jak ChromeDriver dla Chrome lub GeckoDriver dla Firefox. Komunikacja ta odbywa się poprzez restful HTTP api wykorzystujące protokół HTTP zdefiniowany przez W3C WebDriver API i wywodzący się z protokołu JSONWire.

Nightwatch.js wysyła dwa żądania do serwera WebDriver w celu wykonania jakiejkolwiek interakcji z przeglądarką. Może to być polecenie, asercja lub nawet akcja na obiektach strony aplikacji internetowej.

Pierwszym z nich jest prośba do serwera Selenium o utworzenie sesji z przeglądarką i zlokalizowanie żądanego elementu za pomocą selektora CSS lub XPath obiektu, na którym ma zostać wykonana akcja.
Drugim żądaniem jest wykonanie akcji na elemencie pobranym z poprzedniego żądania.
Wszystkie główne przeglądarki mają klasyczną implementację WebDriver, zwaną sterownikiem, którego Nightwatch.js używa niejawnie do komunikacji z przeglądarką.
### Co sprawia, że Nightwatch.js jest tak popularny?

- In-Built Test Runner - Wbudowany runner testowy wiersza poleceń dla wykonania automatyzacji testów Selenium z retrieverami i ukrytym oczekiwaniem wraz z obsługą Grunt.
- Ulepszone wykonywanie testów - Efektywne wykonywanie przypadków testowych na wiele sposobów - testowanie równoległe, sekwencyjne, w grupach lub przy użyciu tagów.
- Czysta składnia - Prosta, ale potężna składnia pomaga testerowi pisać bardziej wydajne i efektywne przypadki testowe szybko używając Javascript i CSS lub XPath dla selektorów elementów sieciowych.
- Integralność danych - Będąc kompletnym frameworkiem testowym sam w sobie, redukuje zależność od oprogramowania firm trzecich i tym samym poprawia integralność danych.
- Serwer Selenium WebDriver - Możliwość zarządzania Selenium lub różnymi serwerami WebDriver (ChromeDriver, GeckoDriver itp.) w dedykowanym procesie potomnym.
- Ciągła integracja - Może być zintegrowany z systemami budowania, takimi jak Jenkins i zapewnia wbudowane raportowanie Junit XML, które może pomóc w budowaniu i testowaniu oprogramowania w sposób ciągły.
- Wsparcie dla usług w chmurze - Zapewnia możliwość integracji z platformami testowymi opartymi na chmurze takimi jak LambdaTest oraz wsparcie dla testowania Cross Browser z JS i Selenium.
- Model obiektowy strony - Łatwość użycia z modelami obiektowymi strony poprzez wsparcie dla CSS i lokalizatorów XPath czyniąc automatyzację przeglądarki bardziej zarządzalną.
- Łatwość skalowania - Zapewnia łatwość skalowania w zależności od testowanej aplikacji za pomocą niestandardowych asercji i poleceń.

# Instalacja
### 1. Instalacja Nightwatch z NPM

```sh
$ npm install nightwatch --save-dev
```

### 2. Instalacja sterowników przeglądarek:

##### Geckodriver (Firefox):
Geckodriver jest usługą WebDriver używaną do napędzania przeglądarki [Mozilla Firefox](https://www.mozilla.org/en-US/firefox/new/).

```sh
$ npm install geckodriver --save-dev
```

##### Chromedriver (Chrome):
Chromedriver jest usługą WebDriver używaną do napędzania przeglądarki [Google Chrome](https://www.google.com/chrome/).
```sh
$ npm install chromedriver --save-dev
```

lub zainstalować wszystko za pomocą jednej linii:

```sh
$ npm i nightwatch geckodriver chromedriver --save-dev
```

### 3. Uruchom test demonstracyjny:

Nightwatch jest dostarczany z folderem `examples` zawierającym kilka przykładowych testów.

Poniżej zostanie uruchomiony podstawowy test, który otwiera wyszukiwarkę [Ecosia.org](https://ecosia.org), wyszukuje termin "nightwatch" i sprawdza, czy pierwszym wynikiem jest strona Nightwatch.js.

```sh
$ npx nightwatch node_modules/nightwatch/examples/tests/ecosia.js
```

__Użytkownicy systemu Windows__ mogą potrzebować uruchomić `node node_modules/.bin/nightwatch`.


# Przykłady
Przykładowe testy są zawarte w folderze [`examples`](https://github.com/nightwatchjs/nightwatch/tree/master/examples), które demonstrują użycie kilku funkcji Nightwatch. 
Możesz również sprawdzić repo [nightwatch-website-tests](https://github.com/nightwatchjs/nightwatch-website-tests) dla przykładowych testów przeciwko stronie [nightwatchjs.org](https://nightwatchjs.org).

### Testy jednostkowe Nightwatch
Testy dla Nightwatch są napisane przy użyciu [Mocha](http://mochajs.org/).

### 1. Sklonuj projekt
```sh
$ git clone https://github.com/nightwatchjs/nightwatch.git
$ cd nightwatch
$ npm install
```

### 2. Uruchom testy
Aby uruchomić kompletny zestaw testów:

```sh
$ npm test
```

Aby sprawdzić pokrycie testami, uruchom komendę:

```sh
$ npm run mocha-coverage
```
a następnie otwórz wygenerowany plik __coverage/index.html__ w swojej przeglądarce.
