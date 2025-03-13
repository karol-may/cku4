
# Lekcja X: Tworzenie encji Calendar, StudentCalendar i TeacherCalendar

## 🎯 Cel lekcji:
- Zaprojektowanie modelu **kalendarza nauczyciela** i **kalendarza ucznia** w Symfony.
- Implementacja encji `Calendar`, `StudentCalendar`, `TeacherCalendar`.
- Obsługa właściwości `days[]` jako interfejs oraz relacji `Lesson[]`.

## 📚 Materiały dydaktyczne:
- Dokumentacja Doctrine ORM: [https://www.doctrine-project.org/](https://www.doctrine-project.org/)
- Symfony Doctrine Relationships: [https://symfony.com/doc/current/doctrine/associations.html](https://symfony.com/doc/current/doctrine/associations.html)

---

# 1️⃣ Tworzenie encji `Calendar`

### **1.1 Definiowanie encji `Calendar`**
```php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;
use Doctrine\Common\Collections\ArrayCollection;
use Doctrine\Common\Collections\Collection;

#[ORM\Entity]
class Calendar {
    
    #[ORM\Id]
    #[ORM\GeneratedValue]
    #[ORM\Column(type: "integer")]
    private int $id;

    #[ORM\OneToMany(targetEntity: Lesson::class, mappedBy: "calendar", cascade: ["persist", "remove"])]
    private Collection $lessons;

    #[ORM\OneToMany(targetEntity: CalendarDay::class, mappedBy: "calendar", cascade: ["persist", "remove"])]
    private Collection $days;

    public function __construct() {
        $this->lessons = new ArrayCollection();
        $this->days = new ArrayCollection();
    }

    public function getId(): int {
        return $this->id;
    }

    public function getLessons(): Collection {
        return $this->lessons;
    }

    public function getDays(): Collection {
        return $this->days;
    }

    public function addLesson(Lesson $lesson): void {
        if (!$this->lessons->contains($lesson)) {
            $this->lessons->add($lesson);
            $lesson->setCalendar($this);
        }
    }

    public function addDay(CalendarDay $day): void {
        if (!$this->days->contains($day)) {
            $this->days->add($day);
            $day->setCalendar($this);
        }
    }
}
```

---

# 2️⃣ Tworzenie encji `CalendarDay`

Dni mogą być wolne lub dostępne – definiujemy encję `CalendarDay`.

```php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
class CalendarDay {

    #[ORM\Id]
    #[ORM\GeneratedValue]
    #[ORM\Column(type: "integer")]
    private int $id;

    #[ORM\ManyToOne(targetEntity: Calendar::class, inversedBy: "days")]
    private Calendar $calendar;

    #[ORM\Column(type: "date")]
    private \DateTimeInterface $date;

    #[ORM\Column(type: "boolean")]
    private bool $available;

    public function __construct(\DateTimeInterface $date, bool $available) {
        $this->date = $date;
        $this->available = $available;
    }

    public function getId(): int {
        return $this->id;
    }

    public function getDate(): \DateTimeInterface {
        return $this->date;
    }

    public function isAvailable(): bool {
        return $this->available;
    }

    public function setCalendar(Calendar $calendar): void {
        $this->calendar = $calendar;
    }
}
```

---

# 3️⃣ Tworzenie encji `Lesson`

Każdy kalendarz posiada lekcje – dodajemy encję `Lesson`.

```php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
class Lesson {

    #[ORM\Id]
    #[ORM\GeneratedValue]
    #[ORM\Column(type: "integer")]
    private int $id;

    #[ORM\ManyToOne(targetEntity: Calendar::class, inversedBy: "lessons")]
    private Calendar $calendar;

    #[ORM\Column(type: "string", length: 255)]
    private string $title;

    #[ORM\Column(type: "datetime")]
    private \DateTimeInterface $lessonDate;

    public function __construct(string $title, \DateTimeInterface $lessonDate) {
        $this->title = $title;
        $this->lessonDate = $lessonDate;
    }

    public function getId(): int {
        return $this->id;
    }

    public function getTitle(): string {
        return $this->title;
    }

    public function getLessonDate(): \DateTimeInterface {
        return $this->lessonDate;
    }

    public function setCalendar(Calendar $calendar): void {
        $this->calendar = $calendar;
    }
}
```

---

# 4️⃣ Tworzenie `StudentCalendar` i `TeacherCalendar`

Kalendarz nauczyciela i ucznia dziedziczą po `Calendar`.

```php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
class TeacherCalendar extends Calendar {

    #[ORM\OneToOne(targetEntity: Teacher::class)]
    #[ORM\JoinColumn(nullable: false)]
    private Teacher $teacher;

    public function setTeacher(Teacher $teacher): void {
        $this->teacher = $teacher;
    }

    public function getTeacher(): Teacher {
        return $this->teacher;
    }
}
```

```php
namespace App\Entity;

use Doctrine\ORM\Mapping as ORM;

#[ORM\Entity]
class StudentCalendar extends Calendar {

    #[ORM\OneToOne(targetEntity: Student::class)]
    #[ORM\JoinColumn(nullable: false)]
    private Student $student;

    public function setStudent(Student $student): void {
        $this->student = $student;
    }

    public function getStudent(): Student {
        return $this->student;
    }
}
```

---

# 5️⃣ Generowanie migracji i aktualizacja bazy danych

Po stworzeniu encji należy wykonać migracje:

```sh
php bin/console make:migration
php bin/console doctrine:migrations:migrate
```

---

# 🏆 Zadanie praktyczne:

1. Stwórz encję `Teacher` i `Student`, powiąż je z `TeacherCalendar` i `StudentCalendar`.  
2. Przetestuj dodawanie dni dostępnych i lekcji do kalendarza nauczyciela.  
3. Dodaj metodę `getAvailableDays()` do `Calendar`, zwracającą tylko dni dostępne.  

---

# 📌 Praca własna:

✅ Rozszerz `Lesson` o pole `student`, które będzie powiązane z `Student`.  
✅ Dodaj metodę `getLessonsForDate(DateTimeInterface $date)` w `Calendar`, zwracającą lekcje dla danego dnia.  

---

To koniec tej lekcji! 🎯🚀
