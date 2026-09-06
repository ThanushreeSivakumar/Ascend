# Contributing to Ascend

Thanks for your interest in improving Ascend! This doc covers how to get set up and how to submit changes.

## Getting Started

1. Fork the repository and clone your fork:
   ```bash
   git clone https://github.com/<your-username>/Ascend.git
   cd Ascend
   ```
2. Follow the setup steps in [`README.md`](./README.md) to get the frontend and backend running locally.
3. Create a branch for your change:
   ```bash
   git checkout -b feature/short-description
   ```

## Making Changes

- Keep pull requests focused — one feature or fix per PR is easier to review than a bundle of unrelated changes.
- Follow existing code style and naming conventions in the file you're editing.
- If you're adding a new dependency, explain why in the PR description.
- Update relevant docs (`README.md`, `ARCHITECTURE.md`) if your change affects setup steps or system design.

## Commit Messages

Use clear, descriptive commit messages:
```
git commit -m "Add domain-based filtering to opportunity feed"
```

## Submitting a Pull Request

1. Push your branch:
   ```bash
   git push origin feature/short-description
   ```
2. Open a PR against `main` and describe:
   - What the change does
   - Why it's needed
   - How you tested it (manual steps, screenshots, etc. — no test suite exists yet)
3. Link any related issue.

## Reporting Bugs / Requesting Features

Open an [issue](https://github.com/Thanushree-Sivakumar/Ascend/issues) with:
- A clear title
- Steps to reproduce (for bugs) or the problem you're trying to solve (for features)
- Any relevant screenshots or logs

## Code of Conduct

Be respectful and constructive. This is an early-stage, learning-focused project — questions and small contributions are just as welcome as big ones.
