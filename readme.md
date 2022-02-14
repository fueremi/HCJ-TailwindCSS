# Tailwind CSS

by @sandhikagalih | Youtube WPU

## What ?

A **Utility-first** CSS Framework that packed with classes. Rapidly build modern websites **without ever leaving your HTML**.

## Who ?

Adam Wathan

## When ?

1 November 2017

## Why ?

_Best practices_ don't actually work. CSS Utility Classes and "Separation of Concerns".

### Separation of concerns

- Structure
- Presentation
- Behaviour

### Phase of build Tailwinds

- Phase 1 : Semantic CSS

  Markup yang saya buat tidak sesuai dengan stylingnya, tapi CSS saya sangat tergantung dengan markup style saya. Mungkin perhatian yang harus dipisahkan ternyata tidak bisa dipisahkan.

- Phase 2 : _Decoupling_ styles from structure

  BEM: Blocks, Elements, Modifier

  - Blocks : Element2 yang secara entitas berdiri sendiri dan memiliki makna sendiri
  - Element : Bagian dari block yang ga punya arti sendiri dan secara semantic terikat dengan block
  - Modifier : Untuk memodifikasi element

  Kemudian saya dihadapi dilemma. Ada components yang secara visual sama, tetapi semanticnya tidak sesuai. Sehingga harus dibuat ulang tapi jadi ga bagus (duplikasi).

  Solusinya membuat komponen yang tidak bergantung pada konten. Akan tetapi kehilangan kemampuan separation of concerns. Adam mengatakan, ada 2 cara menulis HTML & CSS:

  - Separation of Concerns (CSS bergantung HTML)
    - HTML restyleable, CSS not reusable
  - Mixing of Concerns (HTML bergantung CSS)
    - HMTL not restyleable, CSS reusable

  Adam memilih **reusablilty**

- Phase 3: Komponen CSS yang tidak bergantung pada konten

  Semakin banyak yang dilakukan komponen atau semakin spesifik fungsi dari komponen, semakin susah reusablility.

- Phase 4: Content-agnostic CSS components + utility classes

  Semakin banyak komponen akan tetap semakin susah untuk reusability.

- Phase 5: Utility-first Class

  Karena sudah tidak menganut Seperation of Concerns jadi tidak pengaruh.

  Adam: **"You should still create components but built them using utility first"** nama kemampuannya (@apply)

## Utility-First vs Component-First

### Component-first

1 element dianggap sebagai 1 komponen yang **memiliki banyak style**

### Utility-first

Di dalam html terdari dari **banyak class style**(Class-Utility)

## FAQ

### Jadi kayak inline CSS ?

Keliatannya memang seperti inline CSS, interactivity tidak bisa di inline css (lebih flexibel).

### Apa bedanya dengan Bootstrap ?

#### Vanilla CSS

- [+] Kendali penuh
- [+] Code CSS lebih optimal\*
- [-] Buat semuanya dari awal
- [-] Pembuatan lebih lama

#### Bootstrap

- UI Framework, ga hanya punya utility-class, tetapi component-class
- [+] Pembuatan sangat cepat
- [+] Sangat ramah untuk pemula
- [+] Komponen siap untuk digunakan
- [-] Tidak ada kendali
- [-] Banyak code CSS tidak terpakai
- [-] Website terlihat mirip

#### Tailwind

- Utility-first frameworks, sebenarnya ada component-class (berbayar)
- [+] Pembuatan lebih cepat\*
- [+] Mengikuti _best practices_
- [+] Code CSS optimal
- [-] Code HTML menjadi _jelek_
- [-] Harus paham CSS

### Jadi ga semantic ?

## Utilities

- Preflight
- Layout
- Flexbox & Grid
- Spacing & Sizing
- Typography
- Background & Borders
- Effect & Filters
- Transition, Transformation & Animation
- Tables

## Features

### Interactivity

- Pseudo-classes: hover, focus, active, first, last, ...
- Pseudo-element: before, after, placeholder, file, selection, ...

### Responsive Design

- Breakpoints: sm, md, lg, xl

### Dark mode

- Darkmode

### Reusability

### Custom Styles

### Functions & Directives

## Pre-Requisite

- HTML
- CSS
- Bootstrap\*
- CSS Pre-processor
- NPM

## Software Requirements

- Web Browser: Google Chrome
- Code Editor: Visual Studio Code
- VSCode Extension: Tailwind CSS IntelliSense
- Package Manager: NPM

## Installation

1. Install taildwindcss, postcss, autoprefixer

   ```bash
    npm i -D tailwindcss postcss autoprefixer
   ```

1. Instansiasi taildwind

   ```bash
    npx tailwindcss init
   ```

1. Configure file that need to watch by tailwind

   ```js
   module.exports = {
     content: ["./public/**/*.{html,js}"],
     theme: {
       extend: {},
     },
     plugins: [],
   };
   ```

1. Create css file that contain tailwind directive

   ```css
   @tailwind base; /* Reset CSS */
   @tailwind components; /* Membuat container dan grid system */
   @tailwind utilities; /* Memanggil utility-class */
   ```

1. Run command to start taildwind

   ```bash
    npx tailwindcss -i ./src/css/input.css -o ./public/css/style.css --watch
   ```

1. To minified the **FINAL** css file.

   ```bash
   npx tailwindcss -o ./public/css/final.css --minify
   ```

   _Don't forget to change css file on index.html_

## Usage using CDN

[-] ~~Intellisense tidak berjalan jika menggunakan CDN~~ Intellisense bisa digunakan dengan membuat file tailwind.config.js

## Utilities Class Need To Look Up

### Custom values

Kamu dapat menambahkan class baru\* sendiri (Jika value sering digunakan)

```js
tailwind.config = {
  theme: {
    extend: {
      spacing: {
        19: "4.75rem",
      },
      fontFamily: {
        inter: ["Inter"],
      },
      colors: {
        fueremi: "#bada55",
      },
    },
  },
};
```

### Arbitrary values

Kamu dapat memasukkan nilai pada suatu theme. (Jika value hanya sesekali digunakan)

```html
<div class="bg-[url('location-image/image.png')]"></div>

<div class="m-[13px]"></div>
```

### Gradient

Kamu bisa membuat gradient untuk element maupun text dengan sangat mudah

```html
<div class="bg-gradient-r from-slate-500 to-emerald-300"></div>

<h1
  class="bg-gradient-tr from-indigo-200 to-teal-400 bg-clip-text text-transparent"
>
  Tailwind CSS
</h1>
```

_Don't forget to transparent the text_

### Backdrop Blur

Kamu bisa membuat glassmorphism css
