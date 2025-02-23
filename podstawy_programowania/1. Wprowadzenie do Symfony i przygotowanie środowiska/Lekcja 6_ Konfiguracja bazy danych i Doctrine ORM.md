# Lekcja 6: Konfiguracja bazy danych i Doctrine ORM

## 🎯 Cel lekcji:
- Tworzenie encji w Symfony.
- Mapowanie obiektowo-relacyjne (ORM).

## 📚 Materiały dydaktyczne:
- Dokumentacja Doctrine ORM: [https://www.doctrine-project.org/](https://www.doctrine-project.org/)

---

## 1️⃣ Tworzenie encji `Lesson.php`
```sh
php bin/console make:entity Lesson
```

W pliku `src/Entity/Lesson.php`:

```php
use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
class Lesson {
    #[ORM\Id, ORM\GeneratedValue, ORM\Column(type: "integer")]
    private int $id;

    #[ORM\Column(type: "string", length: 255)]
    private string $title;
}
```

---

## 🏆 Zadanie praktyczne:
1. Dodaj do encji `Lesson` pole `date` typu `datetime`.  
2. Wygeneruj i załaduj migracje bazy danych (`php bin/console doctrine:migrations:migrate`).  

---

## 📌 Praca własna:
✅ Dodaj encję `Teacher` i powiąż ją relacją `OneToMany` z `Lesson`.  

---

To koniec szóstej lekcji! 🎯🚀
