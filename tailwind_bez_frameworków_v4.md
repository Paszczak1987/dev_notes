### ✅ **Tailwind 4 - Podstawowa konfiguracja projektu (bez frameworków)**

#### **1. Inicjalizacja projektu**

```bash
npm init -y
```
---

#### **2. Instalacja Tailwind i narzędzi**

```bash
npm install tailwindcss @tailwindcss/cli
```
---

#### **3. Konfiguracja**

##### 3.1. Utwórz pliki `src/output.css` oraz `src/input.css` z importem:

```css
@import "tailwindcss";
```

##### 3.2. Dodaj skrypt w `package.json`:

```json
"scripts": {
  "watch": "npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch",
  "build": "npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css"
}
```

---

#### **4. Uruchom kompilator Tailwind:**

```bash
npm run watch
```
📌 Jeśli masz urządzenie dotykowe dodaj w input.css:
```input.css
@custom-variant hover (&:hover);
```

---

#### **5. W pliku `index.html` podłącz CSS:**

```html
<link href="./src/output.css" rel="stylesheet" />
```
