# Lekcja 5: Obsługa formularzy i walidacja

## 🎯 Cel lekcji:
- Tworzenie formularzy w Symfony.
- Obsługa żądań POST i walidacja danych.

## 📚 Materiały dydaktyczne:
- Symfony Forms: [https://symfony.com/doc/current/forms.html](https://symfony.com/doc/current/forms.html)

---

## 1️⃣ Instalacja komponentu formularzy
```sh
composer require symfony/form symfony/validator
```

---

## 2️⃣ Tworzenie formularza `LessonType.php`
```php
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolver;
use Symfony\Component\Form\Extension\Core\Type\TextType;

class LessonType extends AbstractType {
    public function buildForm(FormBuilderInterface $builder, array $options) {
        $builder->add('title', TextType::class, [
            'label' => 'Tytuł lekcji'
        ]);
    }
}
```

---

## 🏆 Zadanie praktyczne:
1. Dodaj do formularza pole `date` (`DateType`).  
2. Stwórz metodę `handleForm()` w `ScheduleController`, aby obsłużyć żądanie POST.  

---

## 📌 Praca własna:
✅ Dodaj pole `teacherName` do formularza.  

---

To koniec piątej lekcji! 🎯🚀
