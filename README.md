# project_netflix
# Specyfikacja Projektu: Platforma VOD (Interaktywny Katalog Filmowy)

## 1. Cel Projektu
Stworzenie interaktywnej aplikacji webowej pełniącej rolę multimedialnego katalogu filmów. System ma na celu prezentację biblioteki w nowoczesnej formie wizualnej (wzorowanej na popularnych platformach streamingowych) oraz umożliwienie płynnego zarządzania treścią z poziomu dedykowanego panelu, bez konieczności ingerencji w kod źródłowy strony.

## 2. Funkcjonalności Części Klienckiej (Front-end)
Aplikacja zaoferuje użytkownikowi następujące możliwości:
* **Dynamiczna galeria multimediów:** Wyświetlanie bazy filmów w postaci responsywnej siatki plakatów.
* **Hero Banner i Interfejs:** Nowoczesny ekran ładowania (preloader), interaktywne efekty najechania na plakat (hover effects z przyciskiem Play) oraz wyróżniony najnowszy film na głównym banerze.
* **Karta szczegółów (Modal):** Dedykowane, wyskakujące okno dla każdego filmu, prezentujące tytuł, pełne streszczenie fabuły oraz odtwarzacz.
* **Integracja wideo:** Wbudowany odtwarzacz multimedialny pozwalający na oglądanie zwiastunów bezpośrednio na stronie poprzez osadzone ramki iframe z YouTube (z funkcją autoodtwarzania).
* **Moduł wyszukiwania:** Interaktywna wyszukiwarka pozwalająca na błyskawiczne filtrowanie katalogu po tytułach.
* **Funkcja "Moja Lista":** Możliwość zapisywania ulubionych filmów do własnej listy dzięki wykorzystaniu pamięci przeglądarki (LocalStorage).

## 3. Funkcjonalności Panelu Administratora (Back-end / CMS)
System jest wyposażony w autorski, ukryty moduł zarządzania treścią:
* **Autoryzacja dostępu:** Bezpieczne logowanie do panelu administracyjnego chroniące przed osobami niepowołanymi.
* **Zarządzanie katalogiem (CRUD):** * Interaktywny formularz pozwalający na dodawanie nowych filmów do bazy (tytuł, opis, link do plakatu, link do YouTube).
    * Walidacja wprowadzanych danych.
    * Możliwość szybkiego usuwania wybranych pozycji z katalogu za pomocą jednego kliknięcia.
* **Automatyzacja widoku:** Każda zmiana w panelu administratora (dodanie/usunięcie filmu) automatycznie i natychmiastowo aktualizuje główną stronę katalogu dla odwiedzających.

## 4. Środowisko i Technologie
Projekt został zrealizowany w oparciu o klasyczny stack technologiczny dla aplikacji webowych uruchamianych lokalnie:
* **Warstwa wizualna i interakcja:** HTML5, CSS3, Vanilla JavaScript.
* **Logika serwerowa:** PHP.
* **Magazynowanie danych:** Relacyjna baza danych MySQL.
* **Środowisko uruchomieniowe:** Lokalny serwer XAMPP (Apache + MySQL).
