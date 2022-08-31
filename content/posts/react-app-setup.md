---
title: "React app ts using Vite"
date: 2022-08-29T05:29:25+05:30
categories: ["Text dump"]
---

## Setup for react app with typescript and tailwind for css

Initialise react app
```
  npm create vite@latest
```
Install dependencies
```
  npm i
```
Initialize git
```
  git init
  git add .
  git commit -m "Initial commit for vite react ts app"
```

Initialize tailwind
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Configure templates in tailwind config

```
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

Add tailwind directive to src/index.css
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Use this to debug css
```
* {
  outline: 1px solid red;
}
```

