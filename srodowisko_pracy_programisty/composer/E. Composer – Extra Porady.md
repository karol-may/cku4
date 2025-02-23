# Composer – Extra Porady

## 1. Instalacja konkretnej wersji pakietu
Jeśli musisz użyć konkretnej wersji pakietu, np. `2.8.0`, możesz to zrobić tak:
```sh
composer require symfony/console:2.8.0
```
Możesz też określić zakres wersji:
```sh
composer require symfony/console:^2.8
```
✅ `^2.8` oznacza **dowolną wersję od 2.8 do <3.0**  
✅ `~2.8` oznacza **dowolną wersję od 2.8 do <2.9**

---

## 2. Usuwanie nieużywanych zależności (Garbage Collector)
Jeśli usuniesz jakąś bibliotekę ręcznie z `composer.json`, ale jej pliki nadal będą w `vendor/`, możesz je posprzątać:
```sh
composer install --optimize-autoloader --no-dev
composer dump-autoload --optimize
```
To poprawi wydajność, zmniejszy rozmiar paczek i usunie zbędne pliki.

---

## 3. Instalowanie pakietów w trybie "dev"
Niektóre pakiety są potrzebne tylko podczas developmentu, np. PHPUnit:
```sh
composer require --dev phpunit/phpunit
```
Pakiety oznaczone jako `--dev` nie będą instalowane w środowisku produkcyjnym, jeśli użyjesz:
```sh
composer install --no-dev
```
Dzięki temu środowisko produkcyjne pozostaje **lżejsze i szybsze**.

---

## 4. Optymalizacja autoloadingu dla dużych projektów
W dużych projektach Composer może ładować pliki szybciej, jeśli użyjesz:
```sh
composer dump-autoload --optimize
```
Dzięki temu zamiast dynamicznego przeszukiwania `vendor/`, Composer wygeneruje zoptymalizowaną mapę klas.

---

## 5. Composer w środowisku produkcyjnym
Jeśli wdrażasz projekt na serwer produkcyjny, użyj:
```sh
composer install --no-dev --optimize-autoloader
```
To **usunie zbędne paczki dev** i **przyspieszy ładowanie klas**.

