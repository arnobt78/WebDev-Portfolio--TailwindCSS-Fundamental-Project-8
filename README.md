# WebDev Portfolio - TailwindCSS Fundamental Project 8

---

<img width="1000" alt="Screenshot 2025-02-25 at 16 09 38" src="https://github.com/user-attachments/assets/285d8ead-1fd4-4db6-a062-18146946ced3" /><img width="1000" alt="Screenshot 2025-02-25 at 16 09 54" src="https://github.com/user-attachments/assets/dd7e6661-994a-441c-bdba-456ce42a52d6" /><img width="1000" alt="Screenshot 2025-02-25 at 16 10 15" src="https://github.com/user-attachments/assets/ab5a7be3-200a-4ec3-b428-f647463c0a38" /><img width="1000" alt="Screenshot 2025-02-25 at 16 10 47" src="https://github.com/user-attachments/assets/3461eef8-d4a3-4214-af37-b61323a09c69" />

---

## Project Summary

WebDev Portfolio is a modern, responsive personal portfolio website built with **React** and **TailwindCSS**. The goal of this project is to demonstrate fundamental web development concepts, focusing on component-based architecture, utility-first CSS, and modern front-end workflows using Vite.

Designed with both learning and practical use in mind, this portfolio showcases a developer’s professional identity, skills, and projects. It can be reused as a template for your own portfolio or serve as a learning resource for best practices in React and TailwindCSS.

- **Live-Demo:** https://webdev-portfolio-arnob.netlify.app/

---

## Table of Contents

1. [Project Features](#project-features)
2. [Live Demo](#live-demo)
3. [Technology Stack](#technology-stack)
4. [Project Structure](#project-structure)
5. [Setup and Installation](#setup-and-installation)
6. [Component & Data Walkthrough](#component--data-walkthrough)
7. [Functionality & Usage](#functionality--usage)
8. [Useful Tailwind Extensions](#useful-tailwind-extensions)
9. [Assets](#assets)
10. [Examples & Code Snippets](#examples--code-snippets)
11. [Keywords](#keywords)
12. [Conclusion](#conclusion)

---

## Project Features

- **Responsive Design**: Looks great on all screen sizes.
- **Component Architecture**: Modular React components (Navbar, Hero, About, Skills, Projects).
- **Dynamic Data**: Centralized data for navigation, skills, and projects.
- **TailwindCSS Styling**: Utility-first CSS with clean, maintainable classes.
- **Modern Workflow**: Vite for fast development and hot reloading.
- **Reusable Template**: Easily adapt for your own portfolio.

---

## Technology Stack

- **React** (via Vite)
- **TailwindCSS**
- **JavaScript (ES6+)**
- **nanoid** (for unique keys)
- **react-icons** (for scalable icons)

---

## Project Structure

```
.
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── postcss.config.js
├── public/
│   └── vite.svg
├── README.md
├── src/
│   ├── App.jsx
│   ├── assets/
│   │   ├── about.svg
│   │   ├── hero.svg
│   │   └── react.svg
│   ├── components/
│   │   ├── About.jsx
│   │   ├── Hero.jsx
│   │   ├── Navbar.jsx
│   │   ├── Projects.jsx
│   │   ├── ProjectsCard.jsx
│   │   ├── SectionTitle.jsx
│   │   ├── Skills.jsx
│   │   └── SkillsCard.jsx
│   ├── data.jsx
│   ├── index.css
│   └── main.jsx
├── tailwind.config.cjs
└── vite.config.js
```

---

## Setup and Installation

### Prerequisites

- Node.js and npm installed

### 1. Create a Vite + React Project

Follow the [Vite + Tailwind Docs](https://tailwindcss.com/docs/guides/vite):

```sh
npm create vite@latest my-project -- --template react
cd my-project
```

### 2. Install TailwindCSS

```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### 3. Configure TailwindCSS

Edit `tailwind.config.cjs` (or rename from `.js`):

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: { extend: {} },
  plugins: [],
};
```

### 4. Clean Up

- Remove `App.css`
- Clear contents of `index.css` and `App.jsx` to start fresh

### 5. Add Tailwind Directives

In `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 6. Install Additional Dependencies

```sh
npm i nanoid react-icons
```

### 7. Run the Project

```sh
npm run dev
```

---

## Component & Data Walkthrough

### Navbar

Displays navigation links, reads from the `links` array in `data.jsx`.

```jsx
import { links } from "../data";
...
{links.map((link) => (
  <a key={link.id} href={link.href} ...>{link.text}</a>
))}
```

---

### Hero

Main introduction section with developer’s name, title, tagline, and social links.

```jsx
<h1 className="text-7xl font-bold tracking-wider">I'm Arnob</h1>
<p className="mt-4 text-3xl text-slate-700 capitalize tracking-wide">Front-End Developer</p>
```

---

### Skills

Displays tech stack/skills, dynamically from `skills` in `data.jsx`.

```jsx
{skills.map((skill) => <SkillsCard key={skill.id} {...skill} />)}
```

---

### About

Information about the developer, includes an SVG illustration and a short bio.

---

### Projects

Lists individual portfolio projects, each as a card with an image, title, and description.

```jsx
{projects.map((project) => <ProjectsCard key={project.id} {...project} />)}
```

---

### Data File (`src/data.jsx`)

Centralizes all navigation links, skills, and portfolio projects.

```jsx
export const links = [
  { id: nanoid(), href: "#home", text: "home" },
  ...
];

export const skills = [
  {
    id: nanoid(),
    title: "HTML&CSS",
    icon: <FaHtml5 ... />,
    text: "Highly skilled in HTML & CSS..."
  },
  ...
];

export const projects = [
  {
    id: nanoid(),
    img: "...",
    url: "...",
    github: "...",
    title: "first project",
    text: "...",
  },
  ...
];
```

---

## Functionality & Usage

- **Navigation:** Single-page scrolling via navbar links
- **Section Titles:** Each section uses `SectionTitle` for headings
- **Skills/Projects:** Mapped dynamically from data source
- **Styling:** All layout and design uses Tailwind utility classes for rapid development and consistency
- **Assets:** SVGs for illustrations, easily replaceable for personal branding
- **Deployment:** Easily deployable to Netlify, Vercel, or any static hosting provider

---

## Useful Tailwind Extensions

- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Tailwind Fold](https://marketplace.visualstudio.com/items?itemName=stivo.tailwind-fold)

---

## Assets

All SVG illustrations from [Undraw](https://undraw.co/).

---

## Examples & Code Snippets

### Example: Navbar Component

```jsx
import { links } from "../data";

const Navbar = () => (
  <nav className="bg-emerald-100">
    <div className="align-element py-4 flex flex-col sm:flex-row sm:gap-x-16 sm:items-center sm:py-8">
      <h2 className="text-3xl font-bold">
        Web<span className="text-emerald-600">Dev</span>
      </h2>
      <div className="flex gap-x-3">
        {links.map((link) => (
          <a key={link.id} href={link.href} className="capitalize text-lg tracking-wide hover:text-emerald-600 duration-300">
            {link.text}
          </a>
        ))}
      </div>
    </div>
  </nav>
);

export default Navbar;
```

---

### Example: Tailwind Utility Usage

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

### Example: Skill Card Data

```jsx
{
  id: nanoid(),
  title: "React",
  icon: <FaReact className="h-16 w-16 text-emerald-500" />,
  text: "Advanced proficiency in React, developing efficient and interactive front-end applications with a strong emphasis on component-based architecture.",
}
```

---

## Keywords

`React`, `TailwindCSS`, `Portfolio`, `Vite`, `Component-based`, `Frontend`, `Javascript`, `Responsive Design`, `nanoid`, `react-icons`, `Web Developer`, `Single Page Application`, `Undraw`, `Netlify`

---

## Conclusion

This project is an excellent starting point for anyone looking to build their own personal portfolio or learn modern front-end best practices. By combining React’s power and TailwindCSS’s flexibility, you can quickly develop professional and visually appealing web applications. Feel free to fork, experiment, and use this as your own developer portfolio!

---

## More

- [View complete source on GitHub](https://github.com/arnobt78/WebDev-Portfolio--TailwindCSS-Fundamental-Project-8)
- [See live demo](https://webdev-portfolio-arnob.netlify.app/)

---
