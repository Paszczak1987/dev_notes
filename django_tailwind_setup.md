# ✅ Tailwind CSS w Django – krok po kroku

### 1. Zainstaluj django-tailwind

W terminalu w katalogu projektu Djano:

```powershell
pip install django-tailwind
```

### 2. Utwórz aplikację Tailwind

W terminalu w katalogu projektu Django:

```powershell
python manage.py tailwind init twoja_nazwa
```

Zastąp `twoja_nazwa` swoją nazwą (np. `mytailwind`), domyślnie można ustawić `theme`.

---

### 3. Dodaj aplikację do `INSTALLED_APPS` i `MIDDLEWARE` w `settings.py`:

```python
INSTALLED_APPS = [
    ...
    'tailwind',
    'twoja_nazwa',
    'django_browser_reload',
]

MIDDLEWARE = [
    ...
    'django_browser_reload.middleware.BrowserReloadMiddleware',
]

```

---

### 4. Skonfiguruj Tailwinda w `settings.py`:

```python
TAILWIND_APP_NAME = 'twoja_nazwa'
```

📌 Upewnij się, że `npm` jest zainstalowany i dostępny w systemie.
Jeśli nie widać `npm` w systemie można dodać ścieżkę:

```python
NPM_BIN_PATH = r'C:\path\do\npm.bat'
```

---

### 5. Utwórz folder `static` w głównym katalogu projektu (jeśli nie istnieje):

```powershell
mkdir static
```

W `settings.py`:

```python
STATIC_URL = '/static/'

STATICFILES_DIRS = [
    BASE_DIR / "static",
]
```

---

### 6. W `base.html` lub innym szablonie dodaj link do stylów:

```html
{% load static %}
<link href="{% static 'css/dist/styles.css' %}" rel="stylesheet" />
```

📌 Pamiętaj o `{% load static %}`.

---

### 7. Uruchom Tailwinda:

```powershell
python manage.py tailwind install
python manage.py tailwind start
```

📌 `tailwind start` będzie nasłuchiwać na zmiany i generować CSS do `twoja_nazwa/static/css/dist/styles.css`.

📌 Jeśli coś nie działa, możesz ręcznie wykonać: `twoja_nazwa/static_src` użyć `npm install`

---

### 8. Uruchom serwer Django w osobnym terminalu:

```powershell
python manage.py runserver
```
