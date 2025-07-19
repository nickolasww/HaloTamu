# HaloTamu 🎉

**HaloTamu** adalah proyek berbasis React, TypeScript, dan Vite yang menyediakan fondasi ringan untuk membangun aplikasi web modern dengan dukungan Hot Module Replacement (HMR), konfigurasi ESLint yang kuat, serta dukungan dark mode dan integrasi Tailwind CSS.

---

## 🚀 Teknologi yang Digunakan

- ⚛️ [React](https://reactjs.org/)
- ⚡ [Vite](https://vitejs.dev/)
- 🟦 [TypeScript](https://www.typescriptlang.org/)
- 🎨 [Tailwind CSS](https://tailwindcss.com/)
- 🧹 [ESLint](https://eslint.org/) dengan konfigurasi type-aware
- 🌙 Dark/Light/System Mode (preferensi tema UI)
- 🔍 [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x)
- 🧠 [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom)

---

## 🛠️ Setup & Instalasi

1. **Clone repositori**
   ```bash
   git clone https://github.com/nickolasww/HaloTamu.git
   cd HaloTamu
2. **Install dependencies**
  npm install
3. **Jalankan development server**
  npm run dev

## ⚙️ Konfigurasi ESLint Type-Aware
Untuk linting berbasis TypeScript dengan dukungan penuh:
``bash
// eslint.config.js
import tseslint from 'typescript-eslint'
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config([
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      ...tseslint.configs.recommendedTypeChecked,
      // atau gunakan strictTypeChecked
      // ...tseslint.configs.strictTypeChecked,
      ...tseslint.configs.stylisticTypeChecked,
      reactX.configs['recommended-typescript'],
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
    },
  },
])
