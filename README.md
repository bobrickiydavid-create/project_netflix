# project_netflix
# Dokumentacja Projektu: Platforma VOD (Klon Netflix)

## 1. Cel projektu
Celem projektu było stworzenie w pełni funkcjonalnej, responsywnej platformy do przeglądania filmów (Video On Demand), inspirowanej interfejsem serwisu Netflix. Aplikacja umożliwia przeglądanie biblioteki filmów, wyszukiwanie tytułów, oglądanie zwiastunów oraz zarządzanie bazą danych z poziomu panelu administratora.

## 2. Wykorzystane technologie
Projekt został zrealizowany z wykorzystaniem następujących technologii:
* **Frontend:** HTML5, CSS3, JavaScript (Vanilla JS).
* **Backend:** PHP (struktura proceduralna).
* **Baza danych:** MySQL (zarządzana przez phpMyAdmin w środowisku XAMPP).
* **Pamięć przeglądarki:** LocalStorage (do przechowywania ulubionych filmów użytkownika).

## 3. Struktura plików w projekcie
Projekt składa się z następujących głównych plików:

* `index.php` - Główna strona aplikacji. Pobiera filmy z bazy danych, wyświetla baner główny oraz siatkę (grid) z plakatami. Zawiera wbudowaną wyszukiwarkę.
* `admin.php` - Zabezpieczony hasłem panel administratora. Umożliwia dodawanie nowych filmów do bazy oraz usuwanie istniejących (operacje CRUD).
* `db.php` - Plik konfiguracyjny odpowiadający za połączenie z bazą danych MySQL (zawiera dane dostępowe).
* `style.css` - Arkusz stylów definiujący wygląd aplikacji, animacje (np. efekt hover na plakatach) oraz responsywność.
* `script.js` - Plik JavaScript odpowiadający za logikę aplikacji po stronie klienta (otwieranie okienek modalnych, odtwarzacz YouTube, zarządzanie "Moją Listą" w LocalStorage).
* `img/` - Folder zawierający lokalnie pobrane plakaty filmowe, co zapewnia niezawodność wyświetlania grafik.

## 4. Główne funkcjonalności aplikacji

### A. Strona główna (Użytkownik)
1. **Dynamiczna siatka filmów:** Filmy są pobierane bezpośrednio z bazy danych i wyświetlane w formie responsywnej siatki plakatów.
2. **Wyszukiwarka:** Pasek wyszukiwania pozwala na filtrowanie filmów po tytule w czasie rzeczywistym (wykorzystuje zapytania SQL z klauzulą `LIKE`).
3. **Odtwarzacz zwiastunów (Modal):** Po kliknięciu w plakat, otwiera się okienko pop-up z osadzonym odtwarzaczem YouTube (iframe), opisem filmu oraz jego tytułem.
4. **Moja Lista (Ulubione):** Użytkownik może dodawać filmy do swojej prywatnej listy. Dane te są zapisywane w pamięci przeglądarki (`localStorage`), dzięki czemu nie znikają po odświeżeniu strony.

### B. Panel Administratora
1. **Logowanie:** Dostęp do panelu jest chroniony stałym hasłem (sesje PHP).
2. **Dodawanie filmów:** Formularz pozwalający na dodanie nowego filmu (wymaga podania tytułu, linku do plakatu, linku do YouTube oraz opisu).
3. **Usuwanie filmów:** Możliwość usunięcia wybranego filmu z bazy danych za pomocą jednego kliknięcia.

## 5. Struktura Bazy Danych
Aplikacja korzysta z bazy danych o nazwie `vod_platform_db`, w której znajduje się jedna główna tabela `movies`.

**Tabela `movies`:**
* `id` (INT, Primary Key, Auto Increment) - Unikalny identyfikator filmu.
* `title` (VARCHAR) - Tytuł filmu.
* `image_url` (VARCHAR) - Ścieżka do pliku z plakatem (np. `img/m1.jpg`).
* `trailer_url` (VARCHAR) - Link do zwiastuna w serwisie YouTube.
* `description` (TEXT) - Krótki opis fabuły filmu.

## 6. Podsumowanie
Projekt jest kompletną aplikacją webową typu Full-Stack. Wykorzystuje asynchroniczne ładowanie treści (wideo) oraz bezpieczne zapytania do bazy danych (Prepared Statements w PHP), co chroni aplikację przed atakami typu SQL Injection.
