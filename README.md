# 🐱 ascii-cats

> ASCII cats all up in your Node.js and command line!

[![NPM](https://nodei.co/npm/ascii-cats.png)](https://nodei.co/npm/ascii-cats/)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](https://github.com/feross/standard)
[![Build Status](https://secure.travis-ci.org/wiiiimm/ascii-cats.png)](http://travis-ci.org/wiiiimm/ascii-cats)

A lightweight, fun library that provides a collection of ASCII art cats for your terminal or Node.js applications. Perfect for adding some feline charm to your command line tools or just having fun with ASCII art.

## 📦 Installation

### As a library

```bash
npm install ascii-cats
```

### As a CLI tool

```bash
npm install -g ascii-cats
```

## 🚀 Usage

### Library Usage

```javascript
const asciiCats = require('ascii-cats');

// Get a random cat
console.log(asciiCats());

// Get a specific cat by name
console.log(asciiCats('nyan'));

// Get a list of all available cat names
console.log(asciiCats.catNames);
```

### CLI Usage

```bash
# Display a random cat
asciiCats

# Display a specific cat
asciiCats nyan

# List all available cat names
asciiCats --cats
```

## 🖼️ Examples

### Random Cat
```
asciiCats()

  /\ ___ /\
 (  o   o  )
  \  >#<  /
  /       \
 /         \       ^
|           |     //
 \         /    //
  ///  ///   --
```

### Nyan Cat
```
asciiCats('nyan')

  ☆    ☆  ☆
┈┈┈┈ ╭━━━━━━╮  ☆
┈☆ ┈┈┃╳╳╳▕╲▂▂╱▏
┈┈☆ ┈┃╳╳╳▕▏▍▕▍▏
┈┈ ╰━┫╳╳╳▕▏╰┻╯▏
☆ ┈┈┈┃╳╳╳╳╲▂▂╱
   ☆ ╰┳┳━━┳┳╯   ☆
```

## 🐈 Available Cats

The library includes a variety of cats, each with its own unique style:

- `grumpy` - The internet-famous grumpy cat
- `approaching` - A cat approaching you
- `tubby` - A tubby cat
- `confused` - A confused cat
- `playful` - A playful cat
- `thoughtful` - A thoughtful cat
- `delighted` - A delighted cat
- `nyan` - The famous Nyan cat
- `resting` - A resting cat
- `octocat` - GitHub's mascot
- `ready-to-attack` - A cat ready to pounce
- `awake` - A wide-awake cat
- `sleepy` - A sleepy cat
- `got-dat-cat` - A dancing cat
- `hector` - Hector the cat
- `leroy` - Leroy the cat
- `longcat` - The legendary long cat
- `lucky` - A lucky cat
- `sexy` - A fancy cat
- `fish-bowl` - A cat with a fish bowl
- `halloween` - A spooky Halloween cat

And many more! Use `asciiCats --cats` to see the full list.

## 📚 Documentation

For more detailed information, check out our [Wiki](./wiki/README.md) which includes:

- [Architecture Overview](./wiki/Architecture.md)
- [API Reference](./wiki/API-Reference.md)
- [CLI Reference](./wiki/CLI-Reference.md)
- [Contributing Guide](./wiki/Contributing.md)

## 🤝 Contributing

Contributions are welcome! To add a new cat:

1. Fork the repository
2. Add your cat to the `cats.json` file with a clever name
3. Make sure it's properly formatted
4. Submit a pull request

Please ensure your code passes the standard style checks and tests before submitting.

## 📄 License

MIT © [William Li](https://williamli.dev)

