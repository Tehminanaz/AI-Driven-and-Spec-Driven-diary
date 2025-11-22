# The AI-Driven Architect

**Author:** Silvio Savarese  
**Role:** Executive VP & Chief Scientist of AI Research

This repository contains the source code and content for the book **"The AI-Driven Architect: Building Software at the Speed of Thought with Spec-Driven Development"**.

## 📖 About the Book

This book is a practical guide for Senior Engineers and Architects to master **AI-Driven Development (AIDD)** and **Spec-Driven Development (SDD)**. It teaches how to harness AI as a collaborative partner to build enterprise-grade systems.

## 🚀 Getting Started

### Prerequisites
- Node.js >= 18.0
- npm or yarn

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/silviosavarese/ai-driven-architect.git
    cd ai-driven-architect
    ```

2.  Install dependencies:
    ```bash
    npm install
    ```

3.  Start the local development server:
    ```bash
    npm start
    ```
    The site will open at `http://localhost:3000/ai-driven-architect/`.

## 🛠️ Build & Deployment

This project is built with [Docusaurus](https://docusaurus.io/) and deployed to **GitHub Pages**.

### Manual Build
To build the static site:
```bash
npm run build
```
The output will be in the `build` directory.

### Automatic Deployment
This repository is configured with GitHub Actions to automatically deploy to GitHub Pages on every push to the `main` branch.
See `.github/workflows/deploy.yml` for details.

## 📂 Project Structure

- `/docs` - The markdown content for the book chapters.
- `/src` - Custom React components and pages (Landing page).
- `/docusaurus.config.js` - Site configuration.
- `/sidebars.js` - Navigation structure.

## 📄 License

MIT
