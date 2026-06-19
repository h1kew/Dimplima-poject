<p align="center">
  <a href="#-українська">🇺🇦 Українська</a> •
  <a href="#-english">🇬🇧 English</a>
</p>

---

<a id="-українська"></a>
## 🇺🇦 Українська

# Інтелектуальна підсистема моніторингу QoS телекомунікаційної мережі

Цей репозиторій містить вихідний код для бакалаврської кваліфікаційної роботи. Проєкт являє собою комплексну систему для моніторингу показників якості обслуговування (Quality of Service) мережі.

Система складається з двох основних модулів:
- **Клієнтська частина (Frontend):** React, Redux Toolkit та TypeScript. Відповідає за візуалізацію даних та дашборд.
- **Серверна частина (ML Backend):** Python (Flask). Відповідає за обробку метрик та прогнозування за допомогою машинного навчання (Random Forest).

### ✨ Що демонструє система
- **Загальний дашборд** — поточний стан усіх вузлів мережі: затримка, втрата пакетів, активні вузли.
- **NOC-режим** — деталізований перегляд конкретного вузла під час аварії (для розслідування інциденту).
- **ML-прогнозування** — модуль на основі Random Forest прогнозує затримку мережі на 30 секунд наперед.
- **Журнал аварійних подій** — автоматична фіксація критичних і попереджувальних подій.

### 🛠 Технологічний стек
| Частина | Технології |
|---|---|
| **Frontend** | React, TypeScript, Redux Toolkit, Recharts, Node.js (npm) |
| **Backend** | Python, Flask, scikit-learn (Random Forest) |

---

### 📥 Попередні вимоги (що потрібно встановити)

Перш ніж запускати проєкт, переконайтеся, що на вашому комп'ютері встановлено наступні інструменти:

1. **Python (версія 3.8 або новіша)**
   - Завантажити: [python.org/downloads](https://www.python.org/downloads/)
   - ⚠️ **Важливо:** під час встановлення на Windows обов'язково поставте галочку біля **«Add python.exe to PATH»** на першому екрані інсталятора. Без цього система не розпізнає команду `python` у терміналі.

2. **Node.js (рекомендовано версію LTS)**
   - Завантажити: [nodejs.org](https://nodejs.org/)
   - Разом із Node.js автоматично встановиться пакетний менеджер **npm**, обов'язковий для встановлення залежностей і запуску клієнтської частини на React.

3. **Редактор коду (рекомендовано Visual Studio Code)**
   - Завантажити: [code.visualstudio.com](https://code.visualstudio.com/)
   - Потрібен для зручної навігації файлами проєкту та одночасної роботи з кількома терміналами.

---

### 🚀 Інструкція із запуску (локальне середовище)

Для повноцінної роботи системи потрібно відкрити **два окремих вікна термінала** (одне для бекенду, інше для фронтенду). Обидва термінали мають бути відкриті в кореневій папці проєкту.

#### Крок 1: Налаштування та запуск ML-сервера (Термінал 1)

1. Відкрийте перший термінал у корені проєкту.
2. Встановіть Python-залежності бекенду:
   ```bash
   pip install -r ml_backend/requirements.txt
   ```
3. **Обов'язковий крок перед першим запуском** — згенеруйте модель машинного навчання. Скрипт проаналізує дані та створить файл `model.pkl`, без якого сервер не запуститься:
   ```bash
   python ml_backend/train_model.py
   ```
4. Запустіть сам сервер:
   ```bash
   python ml_backend/server.py
   ```
   ⚠️ Залиште цей термінал відкритим — сервер має працювати у фоні. Логи та можливі помилки записуються у файли `server.stdout.log` та `server.stderr.log`.

#### Крок 2: Запуск клієнтського додатка (Термінал 2)

1. Відкрийте нову вкладку термінала (або нове вікно), **не зупиняючи** Python-сервер з попереднього кроку.
2. Встановіть npm-пакети React-додатка (виконується лише один раз):
   ```bash
   npm install
   ```
3. Запустіть проєкт у режимі розробки:
   ```bash
   npm start
   ```

Після цього проєкт скомпілюється, і в браузері автоматично відкриється головний дашборд (зазвичай [http://localhost:3000](http://localhost:3000)). Оскільки ML-сервер уже працює в першому терміналі, показники мережі завантажаться, а статус підключення світитиметься як активний.

---
---

<a id="-english"></a>
## 🇬🇧 English

# Intelligent QoS Monitoring Subsystem for a Telecommunications Network

This repository contains the source code for a bachelor's qualification thesis. The project is a comprehensive system for monitoring network Quality of Service (QoS) metrics.

The system consists of two main modules:
- **Frontend:** React, Redux Toolkit, and TypeScript. Responsible for data visualization and the dashboard.
- **Backend (ML Backend):** Python (Flask). Responsible for processing metrics and forecasting via machine learning (Random Forest).

### ✨ What the system demonstrates
- **General dashboard** — current state of all network nodes: latency, packet loss, active nodes.
- **NOC mode** — a detailed, single-node view used to investigate an active incident.
- **ML forecasting** — a Random Forest module predicts network latency 30 seconds ahead.
- **Incident log** — automatic recording of critical and warning-level events.

### 🛠 Tech Stack
| Part | Technologies |
|---|---|
| **Frontend** | React, TypeScript, Redux Toolkit, Recharts, Node.js (npm) |
| **Backend** | Python, Flask, scikit-learn (Random Forest) |

---

### 📥 Prerequisites (what to install)

Before running the project, make sure the following tools are installed on your computer:

1. **Python (version 3.8 or newer)**
   - Download: [python.org/downloads](https://www.python.org/downloads/)
   - ⚠️ **Important:** on Windows, make sure to check **"Add python.exe to PATH"** on the first screen of the installer. Without this, the `python` command won't be recognized in the terminal.

2. **Node.js (LTS version recommended)**
   - Download: [nodejs.org](https://nodejs.org/)
   - The **npm** package manager is installed automatically with Node.js and is required to install dependencies and run the React frontend.

3. **Code editor (Visual Studio Code recommended)**
   - Download: [code.visualstudio.com](https://code.visualstudio.com/)
   - Useful for navigating the project files and working with multiple terminals at once.

---

### 🚀 Setup & Run Instructions (local environment)

To run the full system, you'll need **two separate terminal windows** (one for the backend, one for the frontend). Both terminals must be opened in the project's root folder.

#### Step 1: Set up and start the ML server (Terminal 1)

1. Open the first terminal in the project root.
2. Install the backend's Python dependencies:
   ```bash
   pip install -r ml_backend/requirements.txt
   ```
3. **Required before the first run** — generate the machine learning model. This script analyzes the data and creates a `model.pkl` file, without which the server won't start:
   ```bash
   python ml_backend/train_model.py
   ```
4. Start the server itself:
   ```bash
   python ml_backend/server.py
   ```
   ⚠️ Leave this terminal open — the server needs to keep running in the background. Logs and any errors are written to `server.stdout.log` and `server.stderr.log`.

#### Step 2: Start the client app (Terminal 2)

1. Open a new terminal tab (or window) **without stopping** the Python server from the previous step.
2. Install the React app's npm packages (only needed once):
   ```bash
   npm install
   ```
3. Start the project in development mode:
   ```bash
   npm start
   ```

After this, the project will compile and your browser will automatically open the main dashboard (usually at [http://localhost:3000](http://localhost:3000)). Since the ML server is already running in the first terminal, network metrics will load successfully and the connection status will show as active.
