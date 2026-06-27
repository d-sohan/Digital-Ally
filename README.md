# Digital Ally

Digital Ally (formerly BizBoost) is an advanced AI-powered platform designed to instantly generate professional websites, business newsletters, and analytical dashboards. Built with React, TypeScript, and powered by Google's Gemini 2.5 Flash model, it bridges the gap between business ideas and digital presence.

## 🚀 Features

- **AI Website Generation**: Transform text descriptions into fully responsive, modern landing pages using Tailwind CSS.
- **Dynamic Content Creation**: Automatically generates business newsletters and marketing copy customized for your brand.
- **Smart Dashboard & Analytics**: Get AI-driven insights and translations for business performance metrics.
- **Voice Interaction**:
  - **Speech-to-Text**: Dictate your website requirements and prompts.
  - **Text-to-Speech**: Listen to generated content and insights.
- **Customization**: Choose from curated color palettes and modify generated designs with follow-up prompts.
- **Multi-Language Support**: Interactive interface supporting multiple languages.
- **Live Preview & Code Export**: View changes in real-time and export clean, deployment-ready HTML/CSS code.
- **Privacy Controls**: Versioned consent before remote AI processing, local-only generation, and one-click data deletion.

## 🛠️ Tech Stack

- **Frontend Framework**: [React 19](https://react.dev/)
- **Build Tool**: [Vite](https://vitejs.dev/)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **AI Model**: [Google Gemini 2.5 Flash](https://deepmind.google/technologies/gemini/) via `@google/genai` SDK
- **Environment**: Node.js

## 📦 Installation

### Clone the Repository

```bash
git clone <repository-url>
cd digital-ally
```

### Install Dependencies

```bash
npm install
```

### Configure Environment Variables

Copy the example file:

```bash
cp .env.example .env
```

Update the values:

```env
GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-2.5-flash
SERVER_CLIENT_TOKEN=replace_with_secure_random_token
AI_CONSENT_VERSION=2026-06-21

# Optional Redis Configuration
REDIS_HOST=localhost
REDIS_PORT=6379

# Optional Server Configuration
PORT=5174
DAILY_QUOTA=100
MONTHLY_QUOTA=1000
```

---

## Running the Application

### Start Frontend

```bash
npm run dev
```

Default Vite URL:

```text
http://localhost:5173
```

### Start Backend

```bash
npm run start:server
```

Default API URL:

```text
http://localhost:5174
```

## 📜 Available Scripts

| Script | Description |
|----------|-------------|
| npm run dev | Start Vite development server |
| npm run build | Validate translations and create production build |
| npm run check:translations | Verify translation coverage |
| npm run preview | Preview production build locally |
| npm run start:server | Start Express AI proxy server |

## 🛡️ Privacy

No business details or generated content are persisted by Digital Ally. Users
must choose remote AI processing or local-only templates before using
generation features. See [PRIVACY.md](PRIVACY.md) for the data-flow, retention,
deletion, logging, and deployment policy.

## 📂 Project Structure

```text
digital-ally/
│
├── public/
│   └── privacy.html
│
├── scripts/
│   └── check-translations.mjs
│
├── server/
│   ├── index.js
│   └── ...
│
├── src/
│   ├── components/
│   ├── context/
│   ├── hooks/
│   ├── pages/
│   ├── services/
│   ├── App.tsx
│   ├── constants.ts
│   └── types.ts
│
├── .env.example
├── package.json
├── vite.config.ts
├── tsconfig.json
├── README.md
└── index.tsx
```

## 🧩 Architectural diagram
<img width="8192" height="1783" alt="arch" src="https://github.com/user-attachments/assets/39777d99-e887-4785-9cd3-036b48e1dbea" />

## 🔀 Data flow diagram
<img width="6818" height="8192" alt="DFD-2026-06-06-051046" src="https://github.com/user-attachments/assets/8834b79b-d627-4a70-9c19-5efe69f842e2" />

## 💡 Usage

1.  **Enter Business Details**: Provide your name, business name, and contact info.
2.  **Describe Your Vision**: Use the text area or microphone to describe the website you want (e.g., "A modern coffee shop website with a menu section").
3.  **Select Style**: Choose a color palette that fits your brand identity.
4.  **Generate**: Click "Generate Website" to watch the AI build your site in seconds.
5.  **Refine**: Use the modification prompt to ask for changes (e.g., "Make the hero section darker").

---

## 🐛 Troubleshooting

### Missing GEMINI_API_KEY

Error:

```text
GEMINI_API_KEY not set in server environment
```

Solution:

- Verify `.env` exists.
- Verify `GEMINI_API_KEY` is populated.
- Restart the server.

---

### Redis Connection Errors

Error:

```text
Redis connection error
```

Solution:

- Start Redis locally.
- Verify `REDIS_HOST` and `REDIS_PORT`.
- The application will continue running with reduced quota functionality.

---

### Build Failures

Run:

```bash
npm run check:translations
```

Fix missing translation keys before rebuilding.

---

### Port Already In Use

Change:

```env
PORT=5174
```

or stop the process using the port.

---

## 🚧 Known Limitations

- Requires a valid Gemini API key.
- Voice features depend on browser support.
- Generated content quality depends on prompt quality.
- Redis quota tracking is unavailable when Redis is offline.
- AI features require internet connectivity.
- Browser speech APIs may behave differently across platforms.

---

[![Classify Issues by Difficulty](https://github.com/vallabhatech/Digital-Ally/actions/workflows/classify-difficulty.yml/badge.svg)](https://github.com/vallabhatech/Digital-Ally/actions/workflows/classify-difficulty.yml)

## 🤝 Contributing

We welcome ELUSOC contributors. Please read the contribution guide before opening
issues or pull requests:

- [CONTRIBUTING.md](CONTRIBUTING.md)

## 🔐 Security

Please review the security policy for reporting vulnerabilities:

- [SECURITY.md](SECURITY.md)

## 📄 License

This project is licensed under the MIT License.
