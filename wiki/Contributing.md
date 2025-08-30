# Contributing Guide

Thank you for your interest in contributing to ascii-cats! This document provides guidelines and instructions for contributing to the project.

## Ways to Contribute

There are several ways you can contribute to ascii-cats:

1. **Add new ASCII cats**: The most common contribution is adding new cat designs
2. **Improve documentation**: Help make the docs clearer and more comprehensive
3. **Fix bugs**: Address issues in the codebase
4. **Add features**: Implement new functionality
5. **Report issues**: Report bugs or suggest improvements

## Adding a New Cat

The most popular way to contribute is by adding a new ASCII cat to the collection. Here's how:

### Step 1: Fork the Repository

1. Visit the [ascii-cats repository](https://github.com/altx-labs/ascii-cats)
2. Click the "Fork" button in the top-right corner
3. Clone your forked repository to your local machine:
   ```bash
   git clone https://github.com/YOUR-USERNAME/ascii-cats.git
   cd ascii-cats
   ```

### Step 2: Create a New Branch

Create a branch for your changes:

```bash
git checkout -b add-new-cat-name
```

### Step 3: Add Your Cat

Open the `cats.json` file and add your new cat:

```json
{
  "existing-cat": [
    "line 1",
    "line 2"
  ],
  
  "your-new-cat": [
    "  /\\___/\\",
    " /       \\",
    "| o     o |",
    " \\_  ∧  _/",
    "   | | |",
    "  (__|__)"
  ]
}
```

Guidelines for cat design:

1. Choose a descriptive, unique name for your cat
2. Make sure each line is properly escaped (especially backslashes)
3. Keep the design reasonably sized (typically under 25 lines)
4. Test that your cat displays correctly in a terminal

### Step 4: Test Your Changes

Run the tests to make sure everything works:

```bash
npm test
```

Also, test your new cat manually:

```bash
node cmd.js your-new-cat
```

### Step 5: Commit and Push

Commit your changes with a descriptive message:

```bash
git add cats.json
git commit -m "feat: add your-new-cat design"
git push origin add-new-cat-name
```

### Step 6: Create a Pull Request

1. Go to your fork on GitHub
2. Click "New Pull Request"
3. Select your branch and provide a description of your changes
4. Submit the pull request

## Code Style

This project follows the JavaScript Standard Style. Please ensure your code adheres to this style:

```bash
npm test
```

This will run both the tests and the style checker.

## Development Setup

To set up the project for development:

```bash
# Clone the repository
git clone https://github.com/altx-labs/ascii-cats.git
cd ascii-cats

# Install dependencies
npm install

# Run tests
npm test
```

## Project Structure

- `index.js`: Main library code
- `cmd.js`: CLI interface
- `cats.json`: Data file containing all cat designs
- `test.js`: Test suite
- `package.json`: Project metadata and dependencies

## Pull Request Process

1. Update the README.md if needed with details of changes
2. Update the tests if you've added functionality
3. Make sure all tests pass
4. Your PR will be reviewed by maintainers
5. Once approved, your PR will be merged

## Cat Design Tips

### ASCII Art Resources

If you're new to ASCII art, these resources might help:

- [ASCII Art Generator](http://patorjk.com/software/taag/)
- [ASCII Art Archive](https://www.asciiart.eu/)
- [Text to ASCII Art Generator](http://patorjk.com/software/taag/)

### Design Guidelines

1. **Readability**: Make sure your cat is recognizable
2. **Size**: Keep it reasonably sized (typically under 25 lines)
3. **Characters**: Use ASCII characters that work across different terminals
4. **Escaping**: Remember to escape special characters, especially backslashes

### Testing Your Design

Before submitting, test your cat in different terminal environments if possible:

- Standard terminal/command prompt
- Different color schemes
- Different terminal sizes

## License

By contributing to ascii-cats, you agree that your contributions will be licensed under the project's MIT License.

