# Contributing to Hearing Aid Software Application

Thank you for your interest in contributing to this project! This document provides guidelines for contributing to the Hearing Aid Software Application.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Pull Request Process](#pull-request-process)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)

## 🤝 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors, regardless of experience level, gender, gender identity, sexual orientation, disability, appearance, body size, race, ethnicity, age, religion, or nationality.

### Expected Behavior

- Be respectful and considerate
- Use welcoming and inclusive language
- Accept constructive criticism gracefully
- Focus on what's best for the community
- Show empathy towards other community members

### Unacceptable Behavior

- Harassment, trolling, or discriminatory comments
- Publishing others' private information
- Unprofessional or inappropriate conduct
- Any behavior that violates the dignity of others

## 🎯 How Can I Contribute?

### 1. Reporting Bugs

Before creating bug reports, please check the [existing issues](https://github.com/Rxhulmxhxto29/Hearing_Aid_Software_application/issues) to avoid duplicates.

**Bug Report Template:**
```markdown
**Description:**
[Clear description of the bug]

**Steps to Reproduce:**
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

**Expected Behavior:**
[What you expected to happen]

**Actual Behavior:**
[What actually happened]

**Environment:**
- Device: [e.g., Samsung Galaxy S21]
- Android Version: [e.g., Android 12]
- App Version: [e.g., 1.0]

**Screenshots:**
[If applicable, add screenshots]

**Additional Context:**
[Any other relevant information]
```

### 2. Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues.

**Enhancement Template:**
```markdown
**Feature Description:**
[Clear description of the enhancement]

**Problem Statement:**
[What problem does this solve?]

**Proposed Solution:**
[How would this feature work?]

**Alternatives Considered:**
[What other solutions did you consider?]

**Use Cases:**
[When would this feature be useful?]

**Additional Context:**
[Mockups, examples, or references]
```

### 3. Contributing Code

We welcome code contributions! Here are the areas where you can help:

- **Bug Fixes**: Fix reported bugs
- **New Features**: Implement requested features
- **Performance**: Optimize audio processing or UI
- **Documentation**: Improve docs and comments
- **Tests**: Add unit or integration tests
- **UI/UX**: Enhance user interface
- **Localization**: Add translations

## 🛠️ Development Setup

### Prerequisites

- Android Studio Arctic Fox (2020.3.1) or later
- JDK 11 or higher
- Android SDK (API 21-36)
- Git

### Setup Steps

1. **Fork the Repository**
   ```bash
   # Click the "Fork" button on GitHub
   ```

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/Hearing_Aid_Software_application.git
   cd Hearing_Aid_Software_application
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/Rxhulmxhxto29/Hearing_Aid_Software_application.git
   ```

4. **Open in Android Studio**
   - Launch Android Studio
   - Select `File > Open`
   - Navigate to the cloned directory
   - Wait for Gradle sync to complete

5. **Build the Project**
   ```bash
   ./gradlew assembleDebug
   ```

6. **Run Tests**
   ```bash
   ./gradlew test
   ./gradlew connectedAndroidTest
   ```

## 📝 Coding Standards

### Kotlin Style Guide

Follow the [Official Kotlin Coding Conventions](https://kotlinlang.org/docs/coding-conventions.html)

**Key Points:**
- Use 4 spaces for indentation (no tabs)
- Maximum line length: 120 characters
- Use meaningful variable and function names
- Prefer `val` over `var` when possible
- Use descriptive names instead of abbreviations

### Code Structure

```kotlin
// Good: Descriptive names and proper formatting
class AudioProcessor {
    private var sampleRate: Int = 48000
    
    fun processSample(sample: Short): Short {
        // Process audio sample
        return amplify(sample)
    }
    
    private fun amplify(sample: Short): Short {
        return (sample * amplificationGain).toInt().toShort()
    }
}

// Bad: Unclear names and poor formatting
class AP{
private var sr:Int=48000
fun ps(s:Short):Short{
return (s*g).toInt().toShort()}}
```

### Documentation

- Add KDoc comments for all public classes, functions, and properties
- Use inline comments to explain complex logic
- Keep comments up-to-date with code changes

```kotlin
/**
 * Applies a biquad filter to an audio sample
 * 
 * @param sample The input audio sample
 * @param frequency The filter center frequency in Hz
 * @param gain The filter gain in dB
 * @param q The filter Q factor
 * @return The filtered audio sample
 */
fun applyBiquadFilter(sample: Float, frequency: Float, gain: Float, q: Float): Float {
    // Implementation
}
```

### Testing

- Write unit tests for new features
- Maintain test coverage above 70%
- Use descriptive test names

```kotlin
@Test
fun `test biquad filter applies correct gain at center frequency`() {
    // Arrange
    val filter = BiquadFilter(frequency = 1000f, gain = 6f, q = 1.0f)
    val inputSample = 0.5f
    
    // Act
    val outputSample = filter.process(inputSample)
    
    // Assert
    assertTrue(outputSample > inputSample)
}
```

## 🔄 Pull Request Process

### 1. Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 2. Make Your Changes

- Write clean, documented code
- Follow coding standards
- Add tests for new features
- Update documentation if needed

### 3. Commit Your Changes

Use clear, descriptive commit messages:

```bash
# Good commit messages
git commit -m "Add noise gate threshold adjustment feature"
git commit -m "Fix memory leak in AudioEngine cleanup"
git commit -m "Update README with installation instructions"

# Bad commit messages
git commit -m "Fix stuff"
git commit -m "Changes"
git commit -m "WIP"
```

**Commit Message Format:**
```
<type>: <short description>

<longer description if needed>

<footer with issue references>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### 4. Keep Your Branch Updated

```bash
git fetch upstream
git rebase upstream/main
```

### 5. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 6. Create Pull Request

1. Go to your fork on GitHub
2. Click "New Pull Request"
3. Select your feature branch
4. Fill in the PR template:

```markdown
## Description
[Clear description of changes]

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests pass
- [ ] Manual testing completed
- [ ] No new warnings

## Related Issues
Closes #[issue number]

## Screenshots
[If applicable]

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Comments added for complex code
- [ ] Documentation updated
- [ ] No new warnings generated
- [ ] Tests added/updated
```

### 7. Code Review Process

- Maintainers will review your PR
- Address any requested changes
- Once approved, your PR will be merged

## 🐛 Reporting Bugs

### Before Submitting

1. Check the [FAQ](README.md#-support)
2. Search [existing issues](https://github.com/Rxhulmxhxto29/Hearing_Aid_Software_application/issues)
3. Ensure you're using the latest version

### Bug Report Guidelines

- Use a clear, descriptive title
- Provide detailed steps to reproduce
- Include expected vs actual behavior
- Add screenshots/recordings if helpful
- Specify your environment (device, OS version)

## 💡 Suggesting Enhancements

### Before Submitting

1. Check if the feature already exists
2. Search [existing enhancement requests](https://github.com/Rxhulmxhxto29/Hearing_Aid_Software_application/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
3. Consider if it fits the project scope

### Enhancement Guidelines

- Describe the problem clearly
- Explain your proposed solution
- Discuss alternative solutions
- Provide use cases and examples

## 📚 Additional Resources

- [Android Development Best Practices](https://developer.android.com/topic/architecture)
- [Kotlin Style Guide](https://kotlinlang.org/docs/coding-conventions.html)
- [Git Commit Best Practices](https://chris.beams.io/posts/git-commit/)
- [Audio Processing Resources](README.md#-documentation)

## 🏆 Recognition

Contributors will be acknowledged in:
- README.md Contributors section
- Release notes
- Project documentation

Thank you for contributing to making this hearing aid application better! 🎧

---

**Questions?** Open an issue or contact the maintainers.

**Happy Coding!** 🚀
