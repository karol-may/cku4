# Lekcja 9: Praca z sesjami i cookies

## 🎯 Cel lekcji:
- Użycie sesji i cookies do przechowywania danych użytkownika.

## 📚 Materiały dydaktyczne:
- Symfony Sessions: [https://symfony.com/doc/current/session.html](https://symfony.com/doc/current/session.html)

---

## 1️⃣ Użycie sesji w Symfony
```php
$session = $request->getSession();
$session->set('last_visit', new \DateTime());
```

---

## 🏆 Zadanie praktyczne:
1. Stwórz sesję `teacher_name`, która przechowa nazwę nauczyciela.  
2. Wyświetl zapisane dane w widoku.  

---

## 📌 Praca własna:
✅ Użyj cookies do przechowania preferowanego widoku kalendarza.  

---

To koniec dziewiątej lekcji! 🎯🚀
