## Skalowanie kodu kreskowego na etykiecie przesyłki eCommerce Poczty Polskiej
To rozszerzenie pozwala na zwiększenie rozmiaru kodu kreskowego na etykiecie przesyłek eCommerce (Allegro Mini Przesyłka i Allegro Przesyłka polecona). Domyślnie linie w kodzie są bardzo gęsto rozmieszczone i do tego ułożone w poprzek a nie wzdłuż ścieżki przesuwu papieru w drukarce termicznej, co powoduje jego zlewanie na wydrukach w niektórych modelach drukarek i problemy z odczytem kodu przez skanery na poczcie.

Osobiście nie mam potrzeby korzystania z tego rozwiązania gdyż na swoich aukcjach nie oferuję tych metod dostawy, jednak zdaję sobie sprawę że niektórym może się to przydać gdyż zgłaszali takie zapotrzebowanie na forum Allegro Gadane. 

Jest to rozszerzenie do przeglądarki Chrome. Wszystkie rozszerzenia testuję tylko dla systemu Windows 10 i najnowszej wersji przeglądarki.

**Instrukcja instalacji:**
1. Pobierz rozszerzenie "scale_pp_barcode.zip" z listy plików widocznej powyżej i rozpakuj je tam gdzie zamierzasz je trzymać.
2. Kliknij ikonę menu rozszerzeń w prawym górnym rogu okna przeglądarki (ikona puzzla)
![chrome_extensions_menu_icon](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/82a60cb8-8cce-4c7c-9cbb-4c3f9f485dad)
lub z menu przeglądarki wybierz "Rozszerzenia - Zarządzaj rozszerzeniami".
3. Włącz "Tryb dewelopera" w prawym górnym rogu okna przeglądarki
![chrome_enabled_developer_mode](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/0d2ab302-ea06-478f-9e40-1980a9603591)

4. Kliknij przycisk "Załaduj rozpakowane"<br/>
![chrome_extensions_load_unpacked_button](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/a304d5ee-0d54-46ca-8acf-ed4b2ec3cf43)

5. Wybierz folder z uprzednio pobranym i rozpakowanym rozszerzeniem.
6. Z menu przeglądarki wybierz "Ustawienia - Pobrane pliki" i zapamiętaj lub zaznacz i skopiuj lokalizację. Zrób to w tym miejscu ponieważ nazwa folderu wyświetlana w oknie "Mój komputer" nie musi być taka sama jak rzeczywista nazwa folderu na dysku, np. folder może wyświetlać się jako "Pobrane", ale jego rzeczywista nazwa to "Downloads"<br/>
![chrome_settings_download_path](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/40806f1b-4660-44d1-b5fa-31f6f47da837)

7. Aby rozszerzenie mogło widzieć pliki pobranych etykiet wymagane jest utworzenie tzw. dowiązania symbolicznego (to coś podobnego do skrótu). W tym celu otwórz wiersz polecenia (wciśnij klawisze <kbd>Win</kbd> + <kbd>R</kbd> wpisz <code>cmd</code>, kliknij OK lub wciśnij Enter albo kliknij Menu Start, wpisz <code>cmd</code> lub <code>wiersz polecenia</code>, kliknij uruchom lub wciśnij Enter). Następnie wpisz (zachowując znaki cudzysłowiu):<br/><br/>
<samp>mklink /D "ścieżka folderu rozszerzenia\downloads" "lokalizacja pobieranych plików"</samp><br/><br/>
![cmd_create_symlink](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/0838dc23-a001-4b89-acac-81f0553ccbbe)<br/>

8. System potwierdzi utworzenie dowiązania symbolicznego<br/>
![cmd_create_symlink_result](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/48525d6b-87ca-4295-808d-d2724f154c40)<br/>
Gdy wejdziesz teraz do folderu "downloads" znajdującego się w folderze rozszerzenia, powinieneś zobaczyć zawartość folderu do którego przeglądarka domyślnie pobiera pliki.

To już wszystko. Etykiety które będą przetwarzane przez to rozszerzenie będą sygnalizowane przez zielony przycisk "Pobierz etykiety" (przy pobieraniu na stronie po zamówieniu przesyłki), "Etykiety" (w oknie Szczegóły przesyłki na stronie Sprzedaż - Obsługa zamówień - Zamówione przesyłki), "Pobierz etykietę" (na liście na stronie Sprzedaż - Obsługa zamówień - Zamówienia)<br/>
![download_label_button_highlighted](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/8d0b206b-df5b-4e4e-a904-c17c4b12301f)

Etykiety są przetwarzane na bieżąco w momencie pobierania. Obsługiwane są tylko pliki zawierające jedną etykietę, tak więc nie zaznaczaj grupowo etykiet do pobrania w jednym pliku. Jeśli potrzebujesz pobrać nieprzetworzoną etykietę, tymczasowo wyłącz rozszerzenie i odśwież stronę.

Przy pierwszym pobieraniu przeglądarka zapyta jeszcze o pozwolenie na pobieranie wielu plików (jest to spowodowane tym że rozszerzenie od razu po pobraniu etykiety przerabia ją, usuwa pobraną etykietę i zapisuje gotowy plik pod tą samą nazwą). Należy kliknąć "Zezwalaj"<br/>
![multiple_downloads_prompt](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/ec8fbc25-531b-49ca-a1da-482472160e67)<br/>

Przykładowy wygląd przetworzonej etykiety<br/>
![sample_label_result](https://github.com/tomsyty/Scale-PP-barcode/assets/41838854/0d68725e-25da-4f77-9c8b-e633966a5bcf)<br/>

Rozszerzenie możesz sprawdzić w serwisie testowym [Allegro Sandbox](https://developer.allegro.pl/tutorials/informacje-podstawowe-b21569boAI1#srodowisko-testowe).
***
Jeżeli napotkasz jakieś błędy w trakcie działania aplikacji, masz jakieś pytania, sugestie, problemy z obsługą, daj znać w sekcji "Discussions".
Jeżeli podoba Ci się moja praca i chcesz aby była dalej rozwijana, możesz wesprzeć mnie dotacją na dowolną kwotę przez PayPal (nie ma potrzeby posiadania konta PayPal): [przekaż donację](https://www.paypal.com/donate/?hosted_button_id=GVU3UC2ZY85SN&locale.x=pl_PL)
