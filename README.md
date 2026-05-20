# Testy automatyczne UI — Python + Playwright (pytest-playwright)

---

## Spis treści

1. [Wymagania](#wymagania)
2. [Instalacja](#instalacja)
3. [Uruchamianie testów](#uruchamianie-testów)
4. [Proponowana struktura katalogów](#proponowana-struktura-katalogów)
5. [Zadania (5)](#zadania-5)
   - [Zadanie 1: Add/Remove Elements](#zadanie-1-addremove-elements--dodawanie-i-usuwanie-elementów)
   - [Zadanie 2: Logowanie](#zadanie-2-logowanie--pozytywny-i-negatywny-scenariusz)
   - [Zadanie 3: Dynamic Loading](#zadanie-3-dynamic-loading--waits-zamiast-sleep)
   - [Zadanie 4: File Upload](#zadanie-4-file-upload--upload-i-walidacja)
   - [Zadanie 5: Alerts](#zadanie-5-alerts--obsługa-alertconfirmprompt)

---

## Wymagania

- Python **3.10+** (rekomendowane 3.11+)
- `pip`
- Dostęp do Internetu (testy używają publicznych stron demo)

---

## Instalacja

```bash
python -m pip install --upgrade pip
pip install pytest pytest-playwright
playwright install
```

---

## Uruchamianie testów

Uruchomienie wszystkich testów:

```bash
pytest -q
```

Przydatne parametry:

```bash
pytest --headed
pytest --headed --slowmo 200
pytest --tracing on
pytest --video on
pytest --screenshot only-on-failure
pytest --browser-channel chrome  
```

---

## Proponowana struktura katalogów

Minimalna struktura — jeden plik = jedno zadanie:

```
ui_tests/
  test_01_add_remove_elements.py
  test_02_login.py
  test_03_dynamic_loading.py
  test_04_file_upload.py
  test_05_alerts.py
```

---

## Zadania (5)

### Zadanie 1: Add/Remove Elements — dodawanie i usuwanie elementów

**Strona:** https://the-internet.herokuapp.com/add_remove_elements/

**Kryteria zaliczenia:**
1. Kliknij **Add Element** 3 razy.
2. Zweryfikuj, że są 3 przyciski **Delete**.
3. Usuń 1 element i sprawdź, że zostały 2.
4. Usuń pozostałe i potwierdź, że nie ma żadnych **Delete**.

---

### Zadanie 2: Logowanie — pozytywny i negatywny scenariusz

**Strona:** https://the-internet.herokuapp.com/login

**Dane poprawne (na stronie):**
- username: `tomsmith`
- password: `SuperSecretPassword!`

**Kryteria zaliczenia:**
1. Dla błędnych danych pojawia się błąd.
2. Dla poprawnych danych pojawia się sukces.
3. Po wylogowaniu wraca ekran logowania.

---

### Zadanie 3: Dynamic Loading — waits zamiast sleep

**Strona:** https://the-internet.herokuapp.com/dynamic_loading/1

**Kryteria zaliczenia:**
1. Kliknij Start.
2. Poczekaj aż pojawi się tekst `Hello World!` bez `sleep`.
3. Zweryfikuj widoczność i treść.

---

### Zadanie 4: File Upload — upload i walidacja

**Strona:** https://the-internet.herokuapp.com/upload

**Kryteria zaliczenia:**
1. Wgraj plik (np. `example.txt`).
2. Kliknij Upload.
3. Zweryfikuj, że strona pokazuje nazwę pliku.

---

### Zadanie 5: Alerts — obsługa alert/confirm/prompt

**Strona:** https://the-internet.herokuapp.com/javascript_alerts

**Kryteria zaliczenia:**
1. Obsłuż JS Alert (accept).
2. Obsłuż JS Confirm (dismiss) i zweryfikuj wynik.
3. Obsłuż JS Prompt (wpisz tekst), zaakceptuj i zweryfikuj wynik.
