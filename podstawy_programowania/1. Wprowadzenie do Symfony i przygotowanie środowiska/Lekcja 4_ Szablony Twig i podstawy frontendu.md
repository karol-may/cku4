# Lekcja 4: Szablony Twig i podstawy frontendu

## 🎯 Cel lekcji:
- Wykorzystanie Twig do generowania widoków.
- Tworzenie głównego szablonu.

## 📚 Materiały dydaktyczne:
- Dokumentacja Twig: [https://twig.symfony.com/](https://twig.symfony.com/)

---

## 1️⃣ Instalacja Twig
```sh
composer require twig
```

---

## 2️⃣ Tworzenie szablonu `base.html.twig`
Plik `templates/base.html.twig`:

```twig
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}Kalendarz Nauczyciela{% endblock %}</title>
</head>
<body>
    <header>
        <h1>{% block header %}Nagłówek strony{% endblock %}</h1>
    </header>
    <main>
        {% block content %}{% endblock %}
    </main>
</body>
</html>
```

---

## 🏆 Zadanie praktyczne:
1. Stwórz widok `schedule.html.twig` i rozszerz `base.html.twig`.  
2. Dodaj nagłówek `"Mój kalendarz"`.  

---

## 📌 Praca własna:
✅ Stwórz prosty styl CSS i dołącz go do szablonu.  

---

To koniec czwartej lekcji! 🎯🚀
