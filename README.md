Kapsle

Zestaw pięciu małych gier w jednym pliku HTML, zrobiony z myślą o iPhonie i o kontrolerze Triki z Żabki. Gry działają samym palcem na ekranie, a po połączeniu prawdziwego Triki przez Bluetooth możesz nimi sterować ruchem kapsla.

Cała aplikacja to jeden plik: kapsle.html. Nie ma instalacji, serwera, kont ani bibliotek do pobrania. Jedyny zasób zewnętrzny to czcionka Baloo 2 z Google Fonts. Gdy się nie wczyta, strona użyje czcionki systemowej.

Uwaga o stanie projektu. Kod powstał na podstawie publicznej dokumentacji protokołu Triki i nie był sprawdzany z prawdziwym kontrolerem w ręku. Gry na dotyk są prostsze i bardziej przewidywalne. Obsługę Triki traktuj jako wersję do wypróbowania i dostrojenia. Rzeczy, których nie jestem pewien, są w tym pliku opisane osobno (sekcja „Co może nie zadziałać").

Spis treści

	1.	Co to jest
	2.	Gry
	3.	Szybki start na iPhonie
	4.	Łączenie z prawdziwym Triki
	5.	Jak sterowanie ruchem działa w grach
	6.	Przycisk na Triki
	7.	Hosting: jak udostępnić stronę
	8.	Rozwiązywanie problemów
	9.	Co może nie zadziałać
	10.	Budowa kodu i dostrajanie
	11.	Notatki o protokole Triki
	12.	Źródła i podziękowania
	13.	Znaki towarowe i nota prawna

Co to jest

Kapsle to zestaw prostych gier w stylu „pstryknij kapsel", inspirowany Triki, czyli kontrolerem w kształcie kapsla sprzedawanym w sklepach Żabka. Triki jest małym kontrolerem ruchu na Bluetooth Low Energy. Ma żyroskop i akcelerometr i oryginalnie współpracuje z aplikacją Żappka.

Ten projekt jest niezależny. Nie używa kodu, grafik ani zasobów Żabki, a samo połączenie z kontrolerem opiera się na protokole opisanym publicznie przez społeczność (patrz Źródła).

Co potrafi aplikacja:

	•	pięć gier, każda grywalna palcem na ekranie,
	•	sterowanie ruchem prawdziwego Triki przez Web Bluetooth,
	•	zapis rekordów na telefonie (w pamięci przeglądarki),
	•	jasny i ciemny motyw, zależnie od ustawień telefonu,
	•	działanie jak aplikacja po dodaniu do ekranu początkowego.

Gry

Pstryk

Pstrykasz kapsel w tarczę. Masz 5 rzutów, a za każdy dostajesz do 100 punktów, zależnie od tego, jak blisko środka zatrzyma się kapsel.

	•	Palcem: połóż palec na kapslu na dole ekranu i pstryknij w stronę tarczy. Siła i kierunek wynikają z szybkości i kierunku ruchu palca tuż przed puszczeniem.
	•	Z Triki: obracasz kontrolerem, żeby wycelować (na ekranie widać przerywaną linię celowania), i stukasz nim, żeby wystrzelić. Siła stuknięcia przekłada się na siłę rzutu.

Kapsel odbija się od ścian i stopniowo zwalnia. Punkty liczą się, gdy całkiem się zatrzyma.

Stop w zieleni

Po pasku jeździ znacznik. Masz go zatrzymać w zielonej strefie. Gra ma 8 rund, a z każdą rundą znacznik jedzie szybciej i strefa robi się węższa.

	•	Palcem: dotknij ekranu w dowolnym miejscu.
	•	Z Triki: szarpnij lub stuknij kontrolerem.

Punkty zależą od tego, jak blisko środka strefy zatrzymasz znacznik. Trafienie w strefę daje od około 70 do 100 punktów, a pudło mniej.

Szybkie tapy

Ile razy zdążysz stuknąć kapsel w 10 sekund? Czas startuje od pierwszego stuknięcia.

	•	Palcem: stukasz w duży kapsel na ekranie.
	•	Z Triki: każde szarpnięcie lub stuknięcie kontrolera liczy się jako jedno stuknięcie. Między dwoma zliczeniami jest minimalna przerwa około 90 milisekund, żeby jedno szarpnięcie nie liczyło się wiele razy.

Łap muchy

Kapsel z oczkami (to żabka) łapie spadające muchy przez 20 sekund. Muchy lecą coraz szybciej.

	•	Palcem: przesuwaj palcem po ekranie, a żabka podąża za nim w poziomie.
	•	Z Triki: obracaj kontroler w płaszczyźnie stołu. Obrót w jedną stronę jedzie w lewo, w drugą w prawo. Jeśli jest odwrotnie, użyj przycisku Odwróć obrót w menu.

Wir

Kręć kapslem jak najdłużej przez 10 sekund. Wynik to liczba pełnych obrotów (z dokładnością do jednej dziesiątej).

	•	Palcem: krąż palcem wokół środka ekranu.
	•	Z Triki: obracaj kontroler płasko na stole. Bardzo wolne ruchy poniżej około 25 stopni na sekundę są ignorowane, żeby szum czujnika nie nabijał wyniku.

Szybki start na iPhonie

Najprostsza droga bez kontrolera:

	1.	Otwórz stronę z grą w Safari.
	2.	Kliknij Udostępnij, potem Dodaj do ekranu początkowego.
	3.	Gotowe. Ikona otwiera grę jak zwykłą aplikację.

Gry działają wtedy samym dotykiem. Safari na iPhonie nie obsługuje jednak Web Bluetooth, więc do połączenia z Triki potrzebujesz innej przeglądarki (patrz następna sekcja).

Łączenie z prawdziwym Triki

Czego potrzebujesz

	•	iPhone z darmową aplikacją Bluefy (przeglądarka z obsługą Web Bluetooth) z App Store.
	•	Stronę z grą pod adresem https (Web Bluetooth wymaga bezpiecznego kontekstu). Zobacz Hosting.
	•	Kontroler Triki z naładowaną baterią.

Kroki

	1.	Zamknij Żappkę i wyłącz w niej Triki. Kontroler łączy się z jednym urządzeniem naraz. Jeśli jest sparowany z inną aplikacją, strona go nie zobaczy.
	2.	Otwórz stronę z grą w aplikacji Bluefy.
	3.	W menu kliknij Połącz Triki i wybierz kontroler z listy. Kontroler reklamuje się jako „Triki" lub „TRIKI" z numerem seryjnym. Jeśli lista jest pusta, naciśnij fizyczny przycisk na kapslu, żeby go „obudzić" (program TRIKI Control opisuje takie naciśnięcie jako krok przy parowaniu).
	4.	Po połączeniu połóż Triki nieruchomo na stole. Strona potrzebuje chwili bezruchu, żeby ustawić „zero" i skalibrować żyroskop. Gdy się uda, w menu zobaczysz na żywo skręt, przechył i siłę ruchu.
	5.	Wybierz grę i graj.

Po rozłączeniu (np. kontroler się uśpił) wystarczy kliknąć Połącz Triki jeszcze raz.

Przyciski w panelu Triki

Przycisk	Co robi
Połącz Triki	otwiera okno wyboru urządzenia Bluetooth i łączy się z kontrolerem
Wyzeruj	ustawia nową pozycję „zero". Połóż Triki nieruchomo, a potem kliknij
Odwróć obrót	odwraca kierunek skrętu (gdy lewo i prawo są zamienione)
Naucz przycisk	uczy stronę rozpoznawać fizyczny przycisk na kapslu (patrz Przycisk)

Pod przyciskami widać linię stanu (skręt, przechył, siła) i drugą, diagnostyczną linię z ostatnim nietypowym pakietem Bluetooth.

Jak sterowanie ruchem działa w grach

Triki ma żyroskop (jak szybko się obraca) i akcelerometr (w którą stronę ciągnie grawitacja i czy ktoś nim szarpnął), ale nie ma kompasu. Okrągły kapsel nie ma też zaznaczonego „przodu". Dlatego nie da się z niego zrobić zwykłego dżojstika, w którym „w lewo" zawsze znaczy lewo na ekranie.

Aplikacja używa więc ruchów, które nie zależą od tego, jak kapsel leży:

	•	Skręt (twist): jak szybko i w którą stronę obracasz kapslem wokół osi pionowej. Strona liczy go względem kierunku grawitacji z chwili kalibracji. Używają go Pstryk (celowanie), Łap muchy i Wir.
	•	Stuknięcie lub szarpnięcie (tap): nagła zmiana wielkości przyspieszenia (odchylenie od 1 g powyżej około 1,2 g). Używają go Stop w zieleni, Szybkie tapy i strzał w Pstryku.
	•	Przechył (tilt): o ile kapsel odchylił się od pozycji „zero". Wartość jest wyliczana i pokazywana w menu, ale żadna z gier jej na razie nie używa.
	•	Odwrócenie (flip): wykrywane, gdy kapsel leży do góry nogami. Też jeszcze bez zastosowania w grach.

Co robi program, żeby ruch był płynny

	•	Prosi Triki o strumień danych z częstotliwością około 208 próbek na sekundę.
	•	Wygładza skręt prostym filtrem, żeby nie drgał, ale reagował szybko.
	•	Gdy kontroler jest nieruchomy, na bieżąco uczy się niewielkiego stałego błędu żyroskopu (biasu) i go odejmuje. Dzięki temu celowanie w Pstryku nie ucieka samo.
	•	Pomija pierwsze około 40 próbek po starcie. Dokumentacja Triki mówi, że na początku strumienia dane bywają zaszumione.
	•	Dane przychodzą seriami. Kod przetwarza każdą próbkę z serii, a nie tylko ostatnią.

Przycisk na Triki

Na płytce Triki jest fizyczny przycisk. W publicznej dokumentacji nie znalazłem jednak opisu, jak jego naciśnięcie jest zgłaszane przez Bluetooth. Dlatego aplikacja ma tryb uczenia przycisku:

	1.	Połącz Triki.
	2.	Kliknij Naucz przycisk.
	3.	W ciągu 8 sekund naciśnij przycisk na kapslu.
	4.	Jeśli kontroler wyśle jakiś pakiet inny niż dane ruchu, strona zapamięta jego pierwsze dwa bajty jako „podpis przycisku". Zobaczysz ten pakiet w linii diagnostycznej w szesnastkowej postaci.
	5.	Od tej pory pakiet z tym podpisem zadziała jak stuknięcie (o średniej sile), np. wystrzeli kapsel w Pstryku.

Jeśli w ciągu 8 sekund nic nie przyjdzie, strona pokaże komunikat, że przycisku nie wykryła. Może to znaczyć, że kontroler w tym trybie strumieniowania po prostu nie wysyła naciśnięcia przycisku.

Wskazówka: jeśli w linii diagnostycznej pojawiają się pakiety bez dotykania przycisku (np. okresowe), strona mogła zapamiętać taki pakiet zamiast przycisku. Wtedy powtórz naukę i naciśnij przycisk od razu po kliknięciu Naucz przycisk. Przepisz też zawartość linii diagnostycznej, jeśli chcesz dostroić kod.

Hosting: jak udostępnić stronę

Web Bluetooth działa tylko na stronach pod adresem https. Masz kilka możliwości.

Link z Claude

Gra została opublikowana jako artefakt Claude. Taki link jest domyślnie prywatny. Zmiana ustawień udostępniania nie jest możliwa w aplikacji Claude na iOS i Androida. Trzeba to zrobić w przeglądarce na claude.ai: otwórz artefakt, kliknij Udostępnij i ustaw dostęp przez link. Źródła nie są zgodne co do tego, czy osoba bez konta Claude otworzy taki link, więc w Bluefy może się pojawić prośba o logowanie.

GitHub Pages (najpewniejsza droga)

	1.	Załóż darmowe konto na GitHubie.
	2.	Utwórz nowe, publiczne repozytorium.
	3.	Wgraj do niego plik kapsle.html pod nazwą index.html.
	4.	W ustawieniach repozytorium włącz Pages (gałąź main, katalog główny).
	5.	Po chwili strona będzie pod adresem w rodzaju https://twoja-nazwa.github.io/nazwa-repo/. Ten adres otwórz w Bluefy.

Inne darmowe hostingi

Podobnie działają usługi, w których przeciągasz plik HTML i dostajesz adres https (np. Netlify Drop, Cloudflare Pages). Niektóre wymagają konta, a część jest kłopotliwa na telefonie.

Własny komputer

Do testów możesz uruchomić na komputerze prosty serwer (np. python3 -m http.server) i wejść na jego adres z telefonu w tej samej sieci. Web Bluetooth wymaga https, ale localhost jest traktowany jako bezpieczny tylko na samym komputerze, więc dla telefonu to zwykle nie wystarczy.

Rozwiązywanie problemów

„Ta przeglądarka nie obsługuje Bluetooth."
Otwierasz stronę w Safari albo w przeglądarce bez Web Bluetooth. Otwórz ten sam adres w aplikacji Bluefy.

Bluefy pokazuje błąd o zablokowanym Bluetooth lub braku uprawnień.
Strona hostowana w ramce innej witryny może mieć ograniczone uprawnienia. Najpewniejsze rozwiązanie to umieszczenie pliku na własnym hostingu (np. GitHub Pages) i otwarcie go bezpośrednio.

Kontrolera nie ma na liście.
Zamknij Żappkę i wyłącz w niej Triki. Naciśnij przycisk na kapslu. Upewnij się, że bateria nie jest wyczerpana. Spróbuj odłączyć się w ustawieniach Bluetooth iPhone'a, jeśli kontroler został tam sparowany.

Połączyło się, ale nic się nie rusza.
Połóż Triki nieruchomo na stole na kilka sekund. Strona ustawia „zero" dopiero w chwili bezruchu. Do tego czasu w menu widać komunikat o położeniu kontrolera.

Obrót działa w złą stronę.
Kliknij Odwróć obrót.

Celowanie w Pstryku „ucieka".
Kliknij Wyzeruj i położ Triki nieruchomo. Kierunek po obrocie jest liczony z całkowania żyroskopu, więc po dłuższym graniu może się lekko rozjechać.

Stuknięcia liczą się za rzadko albo za często.
Próg stuknięcia (odchylenie od 1 g o więcej niż 1,2 g) i minimalna przerwa (90 ms) są zapisane w kodzie. Patrz Dostrajanie.

Rekordy zniknęły.
Rekordy są w pamięci przeglądarki (localStorage). Czyszczenie danych witryny albo zmiana przeglądarki (Safari na Bluefy) oznacza osobne rekordy.

Co może nie zadziałać

Te rzeczy są oparte na dokumentacji i zdrowym rozsądku, ale nie zostały sprawdzone na prawdziwym urządzeniu:

	•	Czy Bluefy pozwala na Web Bluetooth ze strony otwartej z adresu artefaktu Claude (możliwe ograniczenia uprawnień).
	•	Czy kontroler poprawnie reaguje na polecenie startu strumienia 208 Hz (w dokumentacji opisano trzy częstotliwości, w tym tę).
	•	Czy odczyt orientacji i skrętu zgadza się z rzeczywistością na Twoim egzemplarzu (skala czujników została wzięta z opisów układu LSM6DSL).
	•	Czy fizyczny przycisk w ogóle wysyła pakiet podczas strumieniowania danych.
	•	Czy progi stuknięcia i siła rzutu w Pstryku są dobrze dobrane. To wartości początkowe, które mogą wymagać dostrojenia.

Budowa kodu i dostrajanie

Wszystko jest w jednym pliku: styl, układ i skrypt. Najważniejsze elementy skryptu:

Element	Do czego służy
play(), home(), done()	przełączanie widoków i ekran wyniku
saveBest(), renderBest()	zapis i wyświetlanie rekordów
pstryk(), stopG(), tapG(), muchy(), wir()	pięć gier
mkCanvas()	wspólne przygotowanie płótna dla gier rysowanych
TK	stan kontrolera: skręt, kąt, przechył, bias, odwrócenie, podpis przycisku
onFrames()	dekodowanie próbek ruchu z Triki
press()	wspólne wywołanie „stuknięcia" (dla szarpnięcia i przycisku)
other(), learnBtn()	obsługa nietypowych pakietów i uczenie przycisku
connectTriki()	łączenie z kontrolerem i start strumienia
jerkCb	funkcja, którą aktualnie uruchomiona gra ustawia jako reakcję na stuknięcie

Wartości, które warto zmieniać

	•	Próg stuknięcia: w onFrames() warunek if(dev>1.2)press(dev). Mniejsza liczba oznacza czulsze stuknięcie.
	•	Minimalna przerwa między stuknięciami: w press() wartość 90 (milisekundy).
	•	Siła rzutu w Pstryku: w jerkCb w funkcji pstryk() wyrażenie Math.min(24,8+s*3.5). Zwiększ współczynnik, żeby rzucać mocniej.
	•	Tłumienie kapsla w Pstryku: wartość .955 w Math.pow(.955,dt). Bliżej 1 oznacza dłuższy ślizg.
	•	Czułość żabki w Łap muchy: wyrażenie TK.twist/90*W*.6*dt.
	•	Martwa strefa w Wirze: wartość 25 (stopni na sekundę).
	•	Czas gier: 20 sekund w Łap muchy, 10 sekund w Wirze i Szybkich tapach, 8 rund w Stop w zieleni, 5 rzutów w Pstryku.
	•	Kolory: zmienne CSS na początku pliku (--cap, --cap2, --gold, --bg i inne), osobno dla jasnego i ciemnego motywu.

Dodawanie własnej gry

	1.	Dodaj nazwę do obiektu NAMES.
	2.	Dodaj funkcję gry i wpisz ją do mapy w play().
	3.	Dodaj kartę w menu (wzoruj się na istniejących) z elementem <em id="b-nazwa"> na rekord.
	4.	W grze ustaw jerkCb, jeśli chcesz reagować na stuknięcie, i czytaj TK.twist (stopnie na sekundę) lub TK.ang (skumulowany kąt w radianach), jeśli chcesz sterować obrotem.
	5.	Na koniec wywołaj done(wynik, 'jednostka'). Funkcja zapisze rekord i pokaże ekran wyniku.

Notatki o protokole Triki

Poniższe informacje pochodzą z publicznych notatek społeczności (patrz niżej). Opisują model CAP001 z numeru serii dostępnej w sklepach i mogą się różnić w innych wersjach oprogramowania.

Sprzęt (według opisów rozbiórek): układ Bluetooth Nordic nRF52810, czujnik ruchu LSM6DSL (żyroskop i akcelerometr), zewnętrzna pamięć flash, dioda LED i przycisk. Brak magnetometru, czyli brak kompasu.

Reklamowanie się: nazwa „Triki" lub „TRIKI" z numerem seryjnym.

Usługa: w stylu Nordic UART Service (NUS).

Usługa NUS:   6e400001-b5a3-f393-e0a9-e50e24dcca9e
RX (zapis):   6e400002-b5a3-f393-e0a9-e50e24dcca9e   polecenia do kontrolera
TX (notify):  6e400003-b5a3-f393-e0a9-e50e24dcca9e   dane z kontrolera
Rejestr/LED:  6e400004-b5a3-f393-e0a9-e50e24dcca9e   zapis 01 / 00 steruje diodą

Start strumienia ruchu: zapis na RX ośmiu bajtów. Środkowe dwa bajty (w kolejności little-endian) to prosząca o częstotliwość wartość, a ostatni bajt to wybór wewnętrznego profilu.

20 10 00 D0 07 D0 00 03   około 208 Hz (używane tutaj)
20 10 00 D0 07 68 00 03   około 104 Hz
20 10 00 D0 07 34 00 03   około 53 Hz

Nie ma polecenia zatrzymania. Strumień kończy się przy rozłączeniu.

Format ramki ruchu: 14 bajtów, w kolejności:

Bajty	Zawartość
0–1	nagłówek 22 00
2–7	żyroskop X, Y, Z (trzy liczby int16, little-endian)
8–13	akcelerometr X, Y, Z (trzy liczby int16, little-endian)

Skale: żyroskop podziel przez około 14,286, żeby dostać stopnie na sekundę. Akcelerometr podziel przez 2048, żeby dostać g. Kontroler leżący płasko pokazuje około 1 g w osi pionowej.

Zachowanie: dane przychodzą seriami, z przerwami sięgającymi czasem około 100 ms, a czasem kilku sekund (np. gdy palec zasłania antenę). Pierwsze próbki po starcie bywają zaszumione. Kod pomija pierwsze 40.

Źródła i podziękowania

Protokół i zachowanie kontrolera opisali (niezależnie od producenta) m.in.:

	•	Flopsstuff/triki – notatki o sprzęcie, mapa GATT, polecenie startu strumienia, format ramki 14 bajtów i klient Web Bluetooth (github.com/Flopsstuff/triki). Współautorzy podani w repozytorium: Piwencjusz (zdjęcia płytki, zrzut pamięci), tsuki (analiza sprzętu i oprogramowania), AND-Y0 (opis protokołu).
	•	koksny/TRIKI-Control – aplikacja na Windows i Androida zamieniająca Triki w kontroler, wraz z opisem protokołu, częstotliwości strumienia i pomysłem sterowania ruchami niezależnymi od kierunku (github.com/koksny/TRIKI-Control).
	•	woofter-wolf/triki-library-python – biblioteka Python z obsługą m.in. przycisku, baterii i diody (github.com/woofter-wolf/triki-library-python).
	•	Wątek elektroda.com o rozbiórce i inżynierii wstecznej Triki (autor: jmalko).

Dziękuję tym osobom za otwarte udokumentowanie urządzenia. Ewentualne błędy w tej aplikacji są moje.

Znaki towarowe i nota prawna

„Triki" i „Żabka" są znakami towarowymi Żabka Polska sp. z o.o. „HOPX" jest znakiem towarowym Caps Apps sp. z o.o. Producentem kontrolera jest Caps Apps (HOPX), a dystrybutorem Żabka.

Kapsle to niezależny projekt hobbystyczny. Nie jest powiązany, sponsorowany ani wspierany przez Żabkę, Caps Apps ani ich partnerów. Nie zawiera ich oprogramowania, grafik ani innych zasobów. Połączenie z kontrolerem opiera się wyłącznie na publicznie opisanym, standardowym Bluetooth Low Energy.

Używasz kontrolera na własną odpowiedzialność. Aplikacja nie zmienia oprogramowania kontrolera. Zapisuje do niego tylko polecenie startu strumienia danych. Przed wgrywaniem własnych modyfikacji sprzętu lub oprogramowania Triki zapoznaj się z ryzykiem utraty gwarancji lub uszkodzenia urządzenia (ten projekt tego nie robi).

Kod aplikacji możesz dowolnie zmieniać i rozpowszechniać na własny użytek.
