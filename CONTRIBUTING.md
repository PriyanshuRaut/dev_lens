# Contributing to DevLens

Thank you for your interest in contributing to DevLens! This document provides guidelines and instructions for contributing.

## 🚀 How to Fork

1. Click the **Fork** button on the top-right corner of the repository page
2. This creates a copy of the repository under your GitHub account
3. Clone your forked repository locally:

```bash
git clone https://github.com/YOUR_USERNAME/dev_lens.git
cd dev_lens
```

4. Add the original repository as upstream:

```bash
git remote add upstream https://github.com/PriyanshuRaut/dev_lens.git
```

## 🔄 How to Create PR

### 1. Create a Branch

Create a new branch for your changes:

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

### 2. Make Your Changes

- Write clean, readable code
- Follow the existing code style
- Test your changes thoroughly

### 3. Commit Your Changes

```bash
git add .
git commit -m "feat: add new feature"
# or
git commit -m "fix: resolve issue"
```

#### Commit Message Convention

- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation changes
- `style:` - Code style changes (formatting, etc.)
- `refactor:` - Code refactoring
- `test:` - Adding or updating tests

### 4. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 5. Create Pull Request

1. Go to the original repository on GitHub
2. Click **Compare & pull request**
3. Fill in the PR template:
   - **Title**: Clear, concise summary
   - **Description**: Explain what the PR does and why
   - **Related Issues**: Link any related issues (e.g., `Closes #123`)
4. Click **Create pull request**

### 6. Review Process

- Wait for maintainer review
- Address any feedback or requested changes
- Once approved, your PR will be merged!

## 📋 Basic Rules

### Code Style

- Follow Flutter/Dart conventions
- Use meaningful variable and function names
- Add comments for complex logic

### Testing

- Test your changes before submitting
- Ensure existing tests pass
- Add tests for new features when applicable

### Issues

- Search existing issues before creating new ones
- Provide detailed information:
  - Flutter/Dart version
  - Steps to reproduce
  - Expected vs actual behavior
- Screenshots help for UI-related issues

### Communication

- Be respectful and constructive
- Use GitHub issues for bug reports and feature requests
- Use PRs for code contributions

## 🛠 Development Setup

1. **Install Flutter SDK**
   ```bash
   # Follow official Flutter installation guide
   flutter doctor
   ```

2. **Get Dependencies**
   ```bash
   flutter pub get
   ```

3. **Run the App**
   ```bash
   flutter run
   ```

4. **Run Tests**
   ```bash
   flutter test
   ```

5. **Analyze Code**
   ```bash
   flutter analyze
   ```

## 📜 License

By contributing to DevLens, you agree that your contributions will be licensed under the project's license.

---

**Happy Coding! 🚀**
