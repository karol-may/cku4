# Lekcja 1: Wprowadzenie do Symfony i filozofia frameworka

## 🎯 Cel lekcji:
- Poznanie architektury Symfony i filozofii frameworka.
- Zrozumienie wzorca MVC i struktury katalogów Symfony.
- Wstęp do projektu: **System do zarządzania kalendarzem nauczyciela korepetycji**.

## 📚 Materiały dydaktyczne:
- Oficjalna dokumentacja Symfony: [https://symfony.com/doc/current/index.html](https://symfony.com/doc/current/index.html)
- Symfony CLI

---

## 1️⃣ Czym jest Symfony?
Symfony to nowoczesny framework PHP oparty na wzorcu MVC (**Model-View-Controller**). Zapewnia wysoką wydajność i elastyczność.

**Zalety Symfony:**
✅ Struktura MVC  
✅ Wbudowane mechanizmy routingu i kontrolerów  
✅ Doctrine ORM do obsługi baz danych  
✅ Wbudowany system szablonów Twig  

---

## 2️⃣ Struktura katalogów w Symfony
Po instalacji Symfony tworzy następujące katalogi:

📂 **`src/`** – główny katalog aplikacji  
📂 **`config/`** – pliki konfiguracyjne  
📂 **`templates/`** – szablony Twig  
📂 **`public/`** – katalog publiczny aplikacji  
📂 **`var/`** – cache i logi  

---

## 3️⃣ Instalacja Symfony i rozpoczęcie projektu

### **Krok 1: Instalacja Symfony CLI**
```sh
curl -sS https://get.symfony.com/cli/installer | bash
export PATH="$HOME/.symfony/bin:$PATH"
```

### **Krok 2: Tworzenie nowego projektu**
```sh
symfony new teacher-calendar --full
cd teacher-calendar
symfony serve
```

Po wejściu na `http://127.0.0.1:8000/` powinna się wyświetlić strona powitalna Symfony.

---

## 🏆 Zadanie praktyczne:
1. Zainstaluj Symfony i uruchom serwer deweloperski.  
2. Zapoznaj się ze strukturą katalogów projektu.  

---

## 📌 Praca własna:
✅ Stwórz katalog `src/Controller/` i zapisz tam pierwszy kontroler `HomeController.php`.  
✅ Przejdź do następnej lekcji, gdzie zaczniemy tworzyć **routing i kontrolery**.  

---

To koniec pierwszej lekcji! 🎯🚀
