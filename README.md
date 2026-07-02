<div align="center">

# 🔐 PassForge

### Cryptographically secure password generator

**Beautifully crafted, single-file, zero-dependency password generator that runs entirely in your browser.**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/Vanilla_JS-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![No Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)]()

[English](#-english) · [Русский](#-русский)

</div>

---

## 🌐 English

### ✨ Features

**Password Generation**

- Cryptographically secure randomness via `crypto.getRandomValues()`
- Rejection sampling to eliminate modulo bias in random indices
- Adjustable length from 4 to 64 characters
- Four character types: uppercase, lowercase, digits, symbols
- Guaranteed inclusion of at least one character from each selected type
- Fisher-Yates shuffle (on crypto-grade randomness) for unbiased character placement

**Strength Analysis**

- Real-time entropy-based strength calculation
- Brute-force crack time estimation (assuming ~100 billion guesses/sec - GPU speed for fast unsalted hashes; slow hashes like bcrypt/argon2 raise real-world times by orders of magnitude)
- Color-coded animated strength bar (red → orange → purple → green)
- Five strength levels: Very Weak, Weak, Good, Strong, Excellent

**User Experience**

- Bilingual interface (🇷🇺 RU / 🇬🇧 EN) with instant switching and `localStorage` persistence
- Dark / Light theme with smooth transitions; respects system `prefers-color-scheme` on first visit
- One-click copy to clipboard with visual confirmation (shown only on successful copy)
- Session-based password history (last 8 passwords) - slider dragging adds a single entry on release, not one per tick
- Toast notification system
- Keyboard shortcut: `Space` regenerates the password while the generator card is in view
- Shake animation when attempting to deselect the last character type

**Accessibility**

- Respects `prefers-reduced-motion` - animations and smooth scrolling are disabled
- `role="switch"` + `aria-checked` on the theme toggle, `aria-pressed` on option buttons
- `aria-expanded` on FAQ items, live-region toast, visible `:focus-visible` outlines

**Design & Animations**

- Glassmorphism navigation with backdrop blur
- Floating gradient orb background animations
- SVG noise texture overlay
- Staggered entrance animations (fadeUp)
- Scroll-reveal via IntersectionObserver
- Fully responsive - mobile, tablet, desktop

**Content**

- Security tips section with 6 actionable cards
- FAQ accordion with smooth expand/collapse transitions (animated via `grid-template-rows`, so answers of any length are never clipped)

### 🛡️ Privacy

PassForge runs **100% client-side**. No data is ever sent to any server. No cookies, no tracking, no analytics. Generated passwords never leave your device and are never persisted - only your theme and language preferences are stored in `localStorage`.

### 🌍 Live Demo

Try it now without cloning:
→ [https://it2konst.site](https://it2konst.site)

### 🚀 Quick Start

No build tools, no dependencies. Just open the file in any browser:

```bash
git clone https://github.com/it2konst/passforge.git
cd passforge
# macOS: open index.html · Linux: xdg-open index.html · Windows: start index.html
```

Or deploy to any static hosting: GitHub Pages, Netlify, Vercel, Cloudflare Pages - just upload `index.html`.

### 🏗️ Tech Stack

| Technology             | Purpose                                     |
| ---------------------- | ------------------------------------------- |
| HTML5                  | Semantic structure                          |
| CSS3 Custom Properties | Theming system (30+ variables)              |
| Vanilla JavaScript     | All logic, zero dependencies                |
| Web Crypto API         | Cryptographically secure random generation  |
| IntersectionObserver   | Scroll-triggered animations                 |
| localStorage           | Theme & language preference persistence    |

### 📁 Project Structure

```
passforge/
├── index.html    ← entire app in a single file (~2000 lines)
├── README.md
└── LICENSE
```

Yes, that's it. One file of clean, commented code containing HTML structure, CSS styles, and JavaScript logic.

### ⌨️ Keyboard Shortcuts

| Key     | Action                                              |
| ------- | --------------------------------------------------- |
| `Space` | Generate new password (while the generator is in view) |

### 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🇷🇺 Русский

### ✨ Возможности

**Генерация паролей**

- Криптографически стойкая случайность через `crypto.getRandomValues()`
- Rejection sampling для устранения modulo bias при выборе случайных индексов
- Настраиваемая длина от 4 до 64 символов
- Четыре типа символов: заглавные, строчные, цифры, спецсимволы
- Гарантированное включение минимум одного символа каждого выбранного типа
- Перемешивание по алгоритму Фишера-Йетса (на криптостойкой случайности) для равномерного распределения

**Анализ надёжности**

- Расчёт надёжности в реальном времени на основе энтропии
- Оценка времени взлома брутфорсом (при ~100 млрд попыток/сек - скорость GPU для быстрых хэшей без соли; медленные хэши вроде bcrypt/argon2 увеличивают реальное время на порядки)
- Анимированная цветовая шкала (красный → оранжевый → фиолетовый → зелёный)
- Пять уровней: Очень слабый, Слабый, Хороший, Сильный, Отличный

**Пользовательский опыт**

- Двуязычный интерфейс (🇷🇺 RU / 🇬🇧 EN) с мгновенным переключением и сохранением в `localStorage`
- Тёмная / Светлая тема с плавными переходами; при первом визите учитывается системная `prefers-color-scheme`
- Копирование в буфер обмена одним нажатием (подтверждение показывается только при успешном копировании)
- Сессионная история паролей (последние 8) - перетаскивание слайдера добавляет одну запись при отпускании, а не на каждый шаг
- Система toast-уведомлений
- Горячая клавиша: `Пробел` перегенерирует пароль, пока карточка генератора видна на экране
- Shake-анимация при попытке отключить последний тип символов

**Доступность**

- Учитывается `prefers-reduced-motion` - анимации и плавный скролл отключаются
- `role="switch"` + `aria-checked` у переключателя темы, `aria-pressed` у кнопок-опций
- `aria-expanded` в FAQ, live-region для тостов, видимые обводки `:focus-visible`

**Дизайн и анимации**

- Навигация с эффектом glassmorphism и backdrop blur
- Плавающие градиентные orbs на фоне
- SVG noise-текстура для глубины
- Каскадные анимации появления (fadeUp)
- Scroll-reveal через IntersectionObserver
- Полная адаптивность - мобильные, планшеты, десктоп

**Контент**

- Секция советов по безопасности (6 карточек)
- FAQ-аккордеон с плавным раскрытием (анимация через `grid-template-rows` - ответы любой длины не обрезаются)

### 🛡️ Приватность

PassForge работает **на 100% на стороне клиента**. Никакие данные не отправляются на сервер. Без cookies, без трекинга, без аналитики. Сгенерированные пароли никогда не покидают устройство и нигде не сохраняются - в `localStorage` хранятся только выбранные тема и язык.

### 🌍 Живое демо

Попробуйте без клонирования:
→ [https://it2konst.site](https://it2konst.site)

### 🚀 Быстрый старт

Без сборщиков, без зависимостей. Просто откройте файл в любом браузере:

```bash
git clone https://github.com/it2konst/passforge.git
cd passforge
# macOS: open index.html · Linux: xdg-open index.html · Windows: start index.html
```

Или разверните на любом статическом хостинге: GitHub Pages, Netlify, Vercel, Cloudflare Pages - просто загрузите `index.html`.

### 🏗️ Технологии

| Технология             | Назначение                               |
| ---------------------- | ---------------------------------------- |
| HTML5                  | Семантическая структура                  |
| CSS3 Custom Properties | Система тем (30+ переменных)             |
| Vanilla JavaScript     | Вся логика, ноль зависимостей            |
| Web Crypto API         | Криптостойкая генерация случайных чисел  |
| IntersectionObserver   | Анимации при скролле                     |
| localStorage           | Сохранение темы и языка                  |

### 📁 Структура проекта

```
passforge/
├── index.html    ← всё приложение в одном файле (~2000 строк)
├── README.md
└── LICENSE
```

Да, это всё. Один файл чистого прокомментированного кода: HTML-структура, CSS-стили и JavaScript-логика.

### ⌨️ Горячие клавиши

| Клавиша  | Действие                                                |
| -------- | ------------------------------------------------------- |
| `Пробел` | Новый пароль (пока генератор виден на экране)           |

### 🤝 Вклад в проект

Буду рад вашему участию! Порядок действий:

1. Сделайте форк репозитория
2. Создайте ветку (`git checkout -b feature/amazing-feature`)
3. Зафиксируйте изменения (`git commit -m 'feat: add amazing feature'`)
4. Отправьте ветку (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

### 📄 Лицензия

Проект лицензирован под MIT - подробности в файле [LICENSE](LICENSE).

---

<div align="center">

Made with ❤️ and pure vanilla code

**⭐ Star this repo if you find it useful!**

</div>
