# Lekcja 8: Debugowanie i narzędzia dla dewelopera

## 🎯 Cel lekcji:
- Praca z Symfony Profiler.
- Debugowanie i logowanie błędów.

## 📚 Materiały dydaktyczne:
- Symfony Debug: [https://symfony.com/doc/current/profiler.html](https://symfony.com/doc/current/profiler.html)

---

## 1️⃣ Włączanie debugowania
```php
dump($variable);
```

---

## 2️⃣ Symfony Profiler (`_profiler`)
Przejdź pod `http://127.0.0.1:8000/_profiler/`, aby analizować błędy.

---

## 🏆 Zadanie praktyczne:
1. Dodaj logger (`Monolog`) do projektu.  
2. Loguj każdą nową lekcję w bazie (`logger->info("Nowa lekcja: " . $lesson->getTitle());`).  

---

## 📌 Praca własna:
✅ Włącz obsługę wyjątków i stronę błędów w Symfony (`error_controller`).  

---

To koniec ósmej lekcji! 🎯🚀
