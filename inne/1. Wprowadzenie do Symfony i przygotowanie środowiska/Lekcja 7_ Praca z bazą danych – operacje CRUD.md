# Lekcja 7: Praca z bazą danych – operacje CRUD

## 🎯 Cel lekcji:
- Tworzenie operacji **CRUD** (Create, Read, Update, Delete).
- Praca z **Doctrine Repository**.

## 📚 Materiały dydaktyczne:
- Symfony Doctrine: [https://symfony.com/doc/current/doctrine.html](https://symfony.com/doc/current/doctrine.html)

---

## 1️⃣ Tworzenie `LessonRepository.php`
```php
use Doctrine\ORM\EntityRepository;

class LessonRepository extends EntityRepository {
    public function findUpcomingLessons() {
        return $this->createQueryBuilder('l')
            ->where('l.date > :now')
            ->setParameter('now', new \DateTime())
            ->getQuery()
            ->getResult();
    }
}
```

---

## 🏆 Zadanie praktyczne:
1. Stwórz kontroler `LessonController` do zarządzania lekcjami.  
2. Dodaj akcję `list()`, która pobierze i wyświetli wszystkie zajęcia.  

---

## 📌 Praca własna:
✅ Dodaj funkcję `edit()` do edycji lekcji.  

---

To koniec siódmej lekcji! 🎯🚀
