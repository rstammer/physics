# Modern Theoretical Physics: From Classical Mechanics to Quantum Field Theory

## What is the purpose of this repo?

This repo is like a "Wiki" for understanding theoretical physics with a strong emphasis on explaining the precise related
mathematical topics. I want to use it to recall certain questions that occurr and share this later with others
for learning purposes. It contains explanation texts for certain questions as well as technical pages with visualizations,
formulas and proofs or proof artefacts.

* Building a path from Classical Mechanics through Quantum Mechanics to Quantum Field Theory
* Making theoretical physics understandable for mathematicians and undergraduate students
* Explanation of specific formulas
* Answering questions
* Understanding modern concepts for particle physics, the fundamental powers and making these concepts precise

## Some first questions and topics

* Is QFT based on Riemannian Geometry? If yes, how is it modeled?
* What is an Langrangian?
* Schrödinger equation
* How does the Heisenberg uncertainty relation to do with Matrix algebras and the Lie product?
* How does QFT different from raw Quantum mechanics?
* Explanation of particle types and keeping an overview
* Explanaton of how each particle types relates to the mathematical objects

## Technical stack

* Bridgetown (Ruby)
* LaTeX via JS (KaTeX)

## Development

### Prerequisites

- Ruby >= 3.2
- Node.js >= 20
- Bundler (`gem install bundler`)

### Installation

```bash
bundle install
npm install
```

### Running the development server

```bash
bin/bridgetown start
```

This starts:
- Puma web server at http://localhost:4000
- esbuild for frontend asset bundling with live reload

### Building for production

```bash
bin/bridgetown deploy
```

Output is generated in the `output/` directory.

### Adding content

- **Questions (Q&A)**: Add Markdown files to `src/_questions/`
- **Articles**: Add Markdown files to `src/_posts/` with date prefix (e.g., `2026-01-01-title.md`)

### LaTeX support

Use KaTeX for math rendering:
- Block math: `<span class="math-display">\int_0^\infty e^{-x^2} dx</span>`
- Inline math: `<span class="math-inline">\alpha + \beta</span>`

See [PROJECT.md](PROJECT.md) for more Bridgetown-specific documentation.

## Deployment (GitHub Pages)

The site automatically deploys to GitHub Pages when you push to `main`.

### Setup (one-time)

1. Create a GitHub repository and push this code
2. Go to **Settings → Pages**
3. Under "Build and deployment", select **GitHub Actions**
4. Push to `main` — the site will build and deploy automatically

Your site will be available at `https://USERNAME.github.io/REPO_NAME`
