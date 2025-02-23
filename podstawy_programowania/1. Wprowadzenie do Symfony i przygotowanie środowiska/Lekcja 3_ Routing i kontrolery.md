# Lekcja 3: Routing i kontrolery

## 🎯 Cel lekcji:
- Tworzenie pierwszych kontrolerów w Symfony.
- Definiowanie tras (`Route`).
- Przekazywanie parametrów w URL.

## 📚 Materiały dydaktyczne:
- Symfony Routing: [https://symfony.com/doc/current/routing.html](https://symfony.com/doc/current/routing.html)

---

## 1️⃣ Tworzenie kontrolera w Symfony
```sh
php bin/console make:controller HomeController
```

Plik zostanie utworzony w `src/Controller/HomeController.php`:

```php
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Routing\Annotation\Route;
use Symfony\Component\HttpFoundation\Response;

class HomeController extends AbstractController {
    #[Route('/', name: 'home')]
    public function index(): Response {
        return new Response('<h1>Witaj w Symfony!</h1>');
    }
}
```

---

## 🏆 Zadanie praktyczne:
1. Stwórz `ScheduleController.php`, który będzie odpowiadał za kalendarz nauczyciela.  
2. Dodaj trasę `/schedule` zwracającą tekst `"Twój kalendarz zajęć"`.  

---

## 📌 Praca własna:
✅ Dodaj trasę `/schedule/{date}`, która przyjmie parametr daty i zwróci `"Twój plan na {date}"`.  

---

To koniec trzeciej lekcji! 🎯🚀
