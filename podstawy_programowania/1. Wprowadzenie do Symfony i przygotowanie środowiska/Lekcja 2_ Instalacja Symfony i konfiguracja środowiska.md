# Lekcja 2: Instalacja Symfony i konfiguracja środowiska

## 🎯 Cel lekcji:
- Konfiguracja środowiska dla projektu.
- Połączenie Symfony z bazą danych.
- Praca z Symfony Profiler.

## 📚 Materiały dydaktyczne:
- Oficjalna dokumentacja Symfony: [https://symfony.com/doc/current/setup.html](https://symfony.com/doc/current/setup.html)
- Dokumentacja Doctrine ORM: [https://www.doctrine-project.org/](https://www.doctrine-project.org/)

---

## 1️⃣ Konfiguracja `.env`
Plik `.env` zawiera konfigurację projektu, m.in. połączenie z bazą danych:

```ini
DATABASE_URL="mysql://user:password@127.0.0.1:3306/teacher_calendar"
```

---

## 2️⃣ Tworzenie bazy danych
```sh
php bin/console doctrine:database:create
```

---

## 3️⃣ Symfony Profiler – narzędzie do debugowania
Profiler pozwala na analizę żądań HTTP, błędów i zapytań SQL.

Aby go włączyć, przejdź pod `http://127.0.0.1:8000/_profiler/`.

---

## 🏆 Zadanie praktyczne:
1. Skonfiguruj połączenie z bazą danych w `.env`.  
2. Stwórz bazę danych dla projektu.  
3. Uruchom Symfony Profiler i sprawdź jego funkcje.  

---

## 📌 Praca własna:
✅ Przetestuj różne ustawienia Symfony Profiler i zanotuj kluczowe informacje.  
✅ Przejdź do następnej lekcji, gdzie zaczniemy tworzyć **kontrolery i routing**.  

---

To koniec drugiej lekcji! 🎯🚀
