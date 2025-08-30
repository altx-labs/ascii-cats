# API Reference

This document provides detailed information about the ascii-cats JavaScript API.

## Installation

```bash
npm install ascii-cats
```

## Importing

```javascript
// CommonJS
const asciiCats = require('ascii-cats');

// ES Modules (if using a transpiler)
import asciiCats from 'ascii-cats';
```

## API Methods

### `asciiCats([catName])`

The main function that returns ASCII cat art.

#### Parameters

- `catName` (String, optional): The name of the specific cat to retrieve. If omitted, returns a random cat.

#### Returns

- (String): ASCII art of the requested cat, with lines joined by newline characters.

#### Examples

```javascript
// Get a random cat
const randomCat = asciiCats();
console.log(randomCat);

// Get a specific cat
const nyanCat = asciiCats('nyan');
console.log(nyanCat);
```

### `asciiCats.catNames`

A property that contains an array of all available cat names.

#### Returns

- (Array): An array of strings representing all available cat names.

#### Example

```javascript
// Get all available cat names
const allCatNames = asciiCats.catNames;
console.log(allCatNames);
// ['grumpy', 'approaching', 'tubby', ...]
```

## Error Handling

The library does not throw errors for invalid cat names. If a non-existent cat name is provided, the function will return `undefined`.

```javascript
// Request a non-existent cat
const nonExistentCat = asciiCats('not-a-real-cat');
console.log(nonExistentCat); // undefined
```

## Performance Considerations

The library loads all cat data when it's first required. This means:

1. There's a small upfront cost when the module is first loaded
2. Subsequent calls are very fast as they're just accessing in-memory data
3. The memory footprint is proportional to the number and size of cats in the JSON file

## Browser Compatibility

While primarily designed for Node.js, the library can work in browser environments if bundled with tools like Webpack, Browserify, or Parcel. No browser-specific APIs are used.

## TypeScript

While the library doesn't include TypeScript definitions natively, you can define them yourself:

```typescript
declare module 'ascii-cats' {
  function asciiCats(catName?: string): string | undefined;
  namespace asciiCats {
    const catNames: string[];
  }
  export = asciiCats;
}
```

## Examples

### Basic Usage

```javascript
const asciiCats = require('ascii-cats');

// Display a random cat
console.log(asciiCats());

// Display a specific cat
console.log(asciiCats('nyan'));
```

### Listing All Cats

```javascript
const asciiCats = require('ascii-cats');

console.log('Available cats:');
asciiCats.catNames.forEach(name => {
  console.log(`- ${name}`);
});
```

### Creating a Cat Selector

```javascript
const asciiCats = require('ascii-cats');
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

console.log('Available cats:');
asciiCats.catNames.forEach((name, index) => {
  console.log(`${index + 1}. ${name}`);
});

rl.question('Select a cat by number: ', (answer) => {
  const index = parseInt(answer, 10) - 1;
  if (index >= 0 && index < asciiCats.catNames.length) {
    const catName = asciiCats.catNames[index];
    console.log(`\nYou selected: ${catName}\n`);
    console.log(asciiCats(catName));
  } else {
    console.log('Invalid selection, showing a random cat instead:');
    console.log(asciiCats());
  }
  rl.close();
});
```

