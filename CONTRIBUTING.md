# Contributing to Urban Ride

Thank you for your interest in contributing to Urban Ride! This document provides guidelines and instructions for contributing to the project.

## 📚 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Branch Naming Convention](#branch-naming-convention)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Pull Request Process](#pull-request-process)
- [PR Template](#pr-template)
- [Coding Standards](#coding-standards)
- [Testing](#testing)
- [Documentation](#documentation)
- [Questions?](#questions)

## 🎯 Code of Conduct

Please be respectful and constructive in your interactions. We're committed to providing a welcoming and inspiring community for all.

## 🚀 Getting Started

### 1. Fork the Repository

Click the "Fork" button at the top right of the repository page.

### 2. Clone Your Fork

```bash
git clone https://github.com/your-username/urban-ride.git
cd urban-ride
```

### 3. Set Upstream Remote

```bash
git remote add upstream https://github.com/original-org/urban-ride.git
git fetch upstream
```

### 4. Create a Branch

```bash
git checkout -b feat/your-feature-name
```

## 🔄 Development Workflow

1. **Sync with upstream**: Always start with the latest code from the main branch
2. **Create a feature branch**: Use the branch naming convention
3. **Make changes**: Follow coding standards and write tests
4. **Commit**: Use conventional commit messages
5. **Push**: Push to your fork
6. **Create PR**: Submit a pull request with proper documentation

## 🌿 Branch Naming Convention

We follow a structured branch naming convention to maintain clarity:

```
<type>/<short-description>
```

### Branch Types

| Type | Description |
|------|-------------|
| `feat` | New feature implementation |
| `fix` | Bug fix |
| `hotfix` | Critical production bug fix |
| `docs` | Documentation changes |
| `style` | Code style changes (formatting, semicolons, etc.) |
| `refactor` | Code refactoring without functionality changes |
| `test` | Adding or updating tests |
| `chore` | Maintenance tasks, dependencies |
| `perf` | Performance improvements |
| `ci` | CI/CD configuration changes |
| `build` | Build system changes |

### Examples

```bash
# Good
feat/user-authentication
fix/login-error-handling
docs/update-readme
refactor/auth-service-structure
test/add-auth-tests
chore/update-dependencies
hotfix/critical-payment-bug

# Bad
feature-1
fix-stuff
my-branch
update
```

### Branch Name Rules

- Use lowercase letters and hyphens only
- Keep it concise (max 50 characters)
- Be descriptive but not verbose
- No underscores or special characters (except hyphens)

## 📝 Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification for clear and meaningful commit messages.

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types

| Type | Description |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Changes that don't affect the code meaning (formatting, etc.) |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `perf` | Performance improvement |
| `test` | Adding missing tests or correcting existing tests |
| `chore` | Changes to the build process or auxiliary tools |
| `ci` | CI configuration changes |
| `build` | Build system or external dependencies |

### Scope

The scope should indicate the service or area affected:

- `auth` - Authentication service
- `location` - Location service
- `payment` - Payment-rating service
- `trip` - Trip-manager service
- `web` - Web frontend
- `deps` - Dependencies
- `config` - Configuration files

### Subject

- Use imperative, present tense: "change" not "changed" nor "changes"
- Don't capitalize the first letter
- No period (.) at the end
- Maximum 72 characters

### Body (Optional)

- Use imperative, present tense
- Include motivation for change and contrast with previous behavior
- Wrap at 72 characters

### Footer (Optional)

- Reference issues and pull requests
- Use `BREAKING CHANGE:` for breaking changes

### Examples

```bash
# Simple commit
feat(auth): add JWT token refresh endpoint

# Commit with body
fix(trip): resolve driver matching race condition

Fixed issue where multiple drivers could be assigned to the same trip
due to async state update delay.

# Commit with footer
refactor(location): optimize geospatial queries

Updated Redis geohash implementation for better performance

Closes #123

# Breaking change
feat(payment): migrate to Stripe API v2

BREAKING CHANGE: Payment API response format changed from v1 to v2

# Multiple scopes
chore(deps): update Node.js packages

Updated express, mongoose, and related dependencies
```

### Committing

```bash
# Stage changes
git add .

# Commit with message
git commit -m "feat(auth): implement OAuth2 login flow"

# Or use interactive commit
git commit
```

## 🔄 Pull Request Process

### Before Creating a PR

1. **Update your branch**: Rebase or merge latest main branch
2. **Run tests**: Ensure all tests pass
3. **Lint code**: Run linter and fix issues
4. **Update documentation**: Update README, docs, etc. if needed
5. **Review your code**: Self-review before submitting

### Creating a PR

1. Go to your fork on GitHub
2. Click "Pull Request"
3. Select base branch (usually `main`)
4. Fill out the PR template completely
5. Link related issues
6. Submit for review

### PR Review Process

1. **Automated checks**: CI/CD pipeline must pass
2. **Code review**: At least one maintainer approval required
3. **Address feedback**: Make requested changes promptly
4. **Approval**: Once approved, PR will be merged

### PR Merge Policy

- Squash and merge for feature branches
- Rebase and merge for simple fixes
- Maintainers will merge approved PRs

## 📋 PR Template

When creating a pull request, please use the following template:

```markdown
## Description
<!-- Describe your changes in detail -->

## Related Issue
<!-- Link to the issue this PR addresses -->
Fixes #(issue)

## Type of Change
<!-- Mark the appropriate option with an [x] -->

- [ ] feat: New feature
- [ ] fix: Bug fix
- [ ] docs: Documentation update
- [ ] style: Code style/formatting
- [ ] refactor: Code refactoring
- [ ] perf: Performance improvement
- [ ] test: Test addition/update
- [ ] chore: Maintenance/dependencies
- [ ] ci: CI/CD changes
- [ ] build: Build system changes

## Services Affected
<!-- Mark all that apply -->

- [ ] auth
- [ ] location
- [ ] payment-rating
- [ ] trip-manager
- [ ] web
- [ ] other: _____

## Testing
<!-- Describe the tests you ran -->

- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed

Test evidence:
<!-- Screenshots, logs, or test results -->

## Checklist
<!-- Mark completed items with an [x] -->

- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix/feature works
- [ ] All tests pass locally
- [ ] Any dependent changes are merged and published

## Screenshots/Recordings (if applicable)
<!-- Add screenshots or recordings to help explain your changes -->

## Additional Context
<!-- Add any other context about the PR here -->

## Breaking Changes (if applicable)
<!-- List any breaking changes and migration instructions -->

---

**Note**: Please ensure your PR is focused on a single feature or fix. Split unrelated changes into separate PRs.
```

## 💻 Coding Standards

### General Guidelines

- Write clean, readable, and maintainable code
- Follow DRY (Don't Repeat Yourself) principle
- Keep functions small and focused
- Use meaningful variable and function names
- Add comments for complex logic (not obvious code)

### Language-Specific Standards

#### Node.js/JavaScript/TypeScript

- Use ES6+ features where appropriate
- Prefer `const` over `let`, avoid `var`
- Use async/await for asynchronous code
- Follow Airbnb Style Guide or StandardJS
- Use TypeScript for type safety

```javascript
// Good
const getUserById = async (userId) => {
  try {
    const user = await User.findById(userId);
    return user;
  } catch (error) {
    logger.error('Failed to fetch user:', error);
    throw error;
  }
};

// Bad
var getUserById = function(userId) {
  User.findById(userId).then(user => {
    return user;
  });
};
```

### File Organization

```
service-name/
├── src/
│   ├── controllers/
│   ├── services/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── utils/
│   └── index.js
├── tests/
├── docs/
└── package.json
```

## 🧪 Testing

### Test Requirements

- Write tests for all new features
- Maintain minimum 80% code coverage
- Include unit, integration, and E2E tests where applicable

### Running Tests

```bash
# Run all tests
npm test

# Run with coverage
npm run test:coverage

# Run specific test file
npm test -- tests/unit/auth.test.js

# Run in watch mode
npm run test:watch
```

### Writing Tests

```javascript
// Example test structure
describe('AuthService', () => {
  describe('login', () => {
    it('should return token on valid credentials', async () => {
      // Arrange
      const credentials = { email: 'test@example.com', password: 'password123' };

      // Act
      const result = await authService.login(credentials);

      // Assert
      expect(result).toHaveProperty('token');
      expect(result.token).toBeDefined();
    });

    it('should throw error on invalid credentials', async () => {
      // Arrange
      const credentials = { email: 'test@example.com', password: 'wrong' };

      // Act & Assert
      await expect(authService.login(credentials)).rejects.toThrow('Invalid credentials');
    });
  });
});
```

## 📖 Documentation

### Documentation Standards

- Update README for significant changes
- Add inline comments for complex logic
- Maintain API documentation
- Update changelog for releases

### Documentation Locations

- **Service README**: `apps/services/<service>/README.md`
- **API Docs**: `apps/services/<service>/docs/api.md`
- **Architecture**: `docs/architecture/`
- **Main README**: `README.md`

## ❓ Questions?

If you have questions or need help:

1. Check existing issues and documentation
2. Create a new issue with your question
3. Reach out to maintainers

### Contact

- **Issues**: [GitHub Issues](https://github.com/your-org/urban-ride/issues)
- **Discussions**: [GitHub Discussions](https://github.com/your-org/urban-ride/discussions)
- **Email**: dev@urbanride.com

## 🎉 Thank You!

Your contributions make Urban Ride better for everyone. We appreciate your time and effort!

---

**Happy Contributing! 🚀**
