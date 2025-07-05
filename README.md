# React + TypeScript + Vite Counter 🚀

> **Practice project** created with help from **GitHub Copilot (AI)**.  
> The goal is to serve as a starting point to **experiment with CI/CD pipelines**, especially in **GitLab** (and GitHub). Not production-ready — purely for learning purposes.

---

## ✨ Tech Stack

| Tool            | Purpose                                 |
|-----------------|-----------------------------------------|
| **React**       | Frontend UI framework                   |
| **TypeScript**  | Static typing over JavaScript           |
| **Vite**        | Lightning-fast dev server + bundler     |
| **ESLint**      | Code quality and consistency            |
| **GitHub / GitLab CI** | CI/CD automation for build & test |

---

## 🗂️ Project Structure

```
counter/
├── cicd/                  # Extra tools/scripts for CI (e.g., Python)
├── node_modules/
├── public/                # Static assets
├── src/
│   ├── assets/
│   ├── App.tsx            # Main component with counter
│   ├── main.tsx           # Entry point
│   └── ...other components
├── .github/
│   └── workflows/         # GitHub Actions workflows
├── .gitlab-ci.yml         # CI pipeline for GitLab (to be added)
├── .eslintrc.cjs
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
└── ...
```

> **Next step**: create `.gitlab-ci.yml` based on the GitHub Actions workflow to run the same CI pipeline in GitLab.

---

## 🚀 Main Functionality

- Simple page displaying Vite + React logos
- Interactive counter using `useState`
- Basic styling, easy to customize

![Counter demo](https://user-images.githubusercontent.com/000000/placeholder.gif)

---

## 🛠️ Available Scripts

| Command             | Description                         |
|---------------------|-------------------------------------|
| `npm run dev`       | Start local dev server (HMR)        |
| `npm run build`     | Create production-ready build       |
| `npm run preview`   | Preview production build locally    |
| `npm run lint`      | Run ESLint for code quality         |
| `npm run test`      | Run tests (if defined)              |

---

## 🚦 GitHub Actions CI Workflow

Here’s what `.github/workflows/ci.yml` does:

```yaml
name: CI Workflow
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 20
      - run: npm ci
      - run: npm run test
      - run: npm run build
```

### What do these optional Copilot-suggested steps do?

```yaml
# Preview build for e2e or manual checks
# - name: Preview build
#   run: npm run preview & sleep 30
```

Starts the production build preview server in the background and waits 30s. Useful for **E2E testing** or **manual visual checks** during the pipeline.

```yaml
# - name: Set up Python
#   uses: actions/setup-python@v3
#   with:
#     python-version: '3.9'
# - name: Install Python dependencies
#   run: pip install -r ../../cicd/requirements.txt
# - name: Run Python tests
#   run: pytest
```

Sets up Python 3.9, installs dependencies from `cicd/requirements.txt`, and runs `pytest`. Only useful if your repo includes Python scripts (not needed for this React app).

```yaml
# - name: Run code
#   run: |
#    npm run dev
#    sleep 120
```

Starts the local dev server (`npm run dev`) and waits 2 minutes. This is for **local development only**, and **not recommended in CI**. Use `npm run build` and optionally `npm run preview` instead.

---

## 🧩 Linting & Best Practices

Includes a modern ESLint config based on:

- `eslint:recommended`
- `@typescript-eslint/recommended`
- React 18 best practices

Customize `.eslintrc.cjs` to your needs (e.g., Prettier, import sorting).

---

## 📦 Requirements

- **Node.js ≥ 20**
- **npm ≥ 9** (or Yarn / pnpm)

---

## 🏗️ Quick Start

```bash
git clone https://github.com/aperezmari/contador.git
cd contador
npm install
npm run dev
```

Visit <http://localhost:5173> to view the app.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

