Creating a new React project with Tailwind CSS on a Linux machine is straightforward. Here’s a step-by-step guide:

---

## 1. Install Node.js and npm (if not installed)

First, make sure you have Node.js and npm installed. You can check by running:

```bash
node -v
npm -v
```

If they’re not installed, install Node.js via your package manager or use NodeSource:

```bash
# Example for Ubuntu/Debian:
sudo apt update
sudo apt install nodejs npm
```

Or better, install Node.js from NodeSource to get the latest version:

```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
```

---

## 2. Create a new React project with Create React App

Run:

```bash
npx create-react-app my-tailwind-app
```

Replace `my-tailwind-app` with your preferred project folder name.

---

## 3. Navigate to your project directory

```bash
cd my-tailwind-app
```

---

## 4. Install Tailwind CSS and its dependencies

```bash
npm install -D tailwindcss postcss autoprefixer
```

Then initialize Tailwind CSS configuration:

```bash
npx tailwindcss init -p
```

This creates two config files:

* `tailwind.config.js`
* `postcss.config.js`

---

## 5. Configure Tailwind to remove unused styles in production

Edit `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

This tells Tailwind to scan all your React files for class names.

---

## 6. Add Tailwind directives to your CSS

Open `src/index.css` and replace its contents with:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## 7. Start the React development server

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser, and Tailwind CSS will be working with your React app.

---

## Quick summary:

```bash
npx create-react-app my-tailwind-app
cd my-tailwind-app
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
# edit tailwind.config.js to add content path
# replace src/index.css with Tailwind directives
npm start
```

---

