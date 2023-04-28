# 🚀 Web App

Welcome to the Web App project! It's a work-in-progress web application with a backend built using [Actix.rs](https://actix.rs/) and a frontend built using [Next.js](https://nextjs.org/) with TypeScript.

⚠️ **Please note**: This project is still under development, and many features may not work as expected. Feel free to explore the codebase, provide feedback, or contribute to the project. We appreciate your patience!

## 📚 Table of Contents

- [🌟 Features](#-features)
- [🔧 Prerequisites](#-prerequisites)
- [💻 Installation](#-installation)
- [🚀 Running the App](#-running-the-app)
- [📜 License](#-license)


## 🌟 Features

- Backend using Actix.rs
- Frontend using Next.js with TypeScript
- Docker and Docker Compose for containerization
- Kubernetes for orchestration
- GitHub Actions for CI/CD
- pnpm for package management
- Pre-commit hooks for code formatting and linting

## 🔧 Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (latest stable version)
- [Node.js](https://nodejs.org/en/download/) (LTS version)
- [pnpm](https://pnpm.io/installation) (latest version)
- [Docker](https://www.docker.com/get-started) (latest version)
- [Docker Compose](https://docs.docker.com/compose/install/) (latest version)
- [Kubernetes](https://kubernetes.io/docs/tasks/tools/) (optional, for deployment)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) (optional, for deployment)

## 💻 Installation

1. Clone the repository:



```bash
git clone https://github.com/yourusername/web_app.git
cd web_app
```

2. Install backend dependencies:
```bash
cd backend
cargo build
```

3. Install frontend dependencies:
```bash
cd frontend
pnpm install
cd ..
```

## 🚀 Running the App

1. Start the backend and frontend using Docker Compose:
```bash
docker-compose up
```

2. Access the frontend in your browser at [http://localhost:3000](http://localhost:3000).

3. To stop the services, run:

```bash
docker-compose down
```

## 📜 License

This project is licensed under the [MIT License](LICENSE.md).