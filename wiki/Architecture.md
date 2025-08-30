# Architecture Overview

This document provides an overview of the ascii-cats architecture, explaining how the different components work together.

## System Architecture

ascii-cats follows a simple, modular architecture that separates data, core functionality, and user interfaces.

```
┌─────────────┐     ┌───────────────┐     ┌──────────────┐
│             │     │               │     │              │
│  cats.json  │────▶│   index.js    │────▶│    cmd.js    │
│  (Data)     │     │   (Core)      │     │    (CLI)     │
│             │     │               │     │              │
└─────────────┘     └───────────────┘     └──────────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │              │
                    │   test.js    │
                    │   (Tests)    │
                    │              │
                    └──────────────┘
```

### Components

1. **Data Layer (cats.json)**
   - Contains all ASCII cat art as JSON data
   - Each cat is stored as an array of strings (lines)
   - Cats are indexed by name for easy lookup

2. **Core Library (index.js)**
   - Loads and processes the cat data
   - Provides the main API for accessing cats
   - Handles random selection and specific cat retrieval
   - Exposes list of available cat names

3. **Command Line Interface (cmd.js)**
   - Provides a user-friendly CLI
   - Parses command-line arguments using yargs
   - Formats and displays cats to the terminal
   - Offers help and cat listing functionality

4. **Tests (test.js)**
   - Ensures library functionality works as expected
   - Validates random cat selection
   - Verifies specific cat retrieval
   - Confirms cat name listing

## Data Flow

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  ┌─────────┐     ┌─────────────┐     ┌────────────────┐  │
│  │         │     │             │     │                │  │
│  │ Request │────▶│ Process Cat │────▶│ Return ASCII  │  │
│  │         │     │ Selection   │     │ Art String    │  │
│  └─────────┘     └─────────────┘     └────────────────┘  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

1. **Request**: User requests a cat (random or specific)
2. **Process**: Library loads data and selects appropriate cat
3. **Return**: ASCII art is returned as a formatted string

## Library vs CLI Flow

```
┌─────────────────┐
│                 │
│  Library Usage  │
│                 │
└────────┬────────┘
         │
         ▼
┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │
│  require('..') │────▶│  asciiCats()    │
│                 │     │                 │
└─────────────────┘     └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │                 │
                        │  ASCII String   │
                        │                 │
                        └─────────────────┘

┌─────────────────┐
│                 │
│   CLI Usage     │
│                 │
└────────┬────────┘
         │
         ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │     │                 │
│  asciiCats cmd  │────▶│  Parse Args     │────▶│  Process Cat    │
│                 │     │                 │     │                 │
└─────────────────┘     └─────────────────┘     └────────┬────────┘
                                                         │
                                                         ▼
                                                ┌─────────────────┐
                                                │                 │
                                                │  Print to STDOUT│
                                                │                 │
                                                └─────────────────┘
```

## Implementation Details

### Cat Data Structure

Each cat in the `cats.json` file is represented as an array of strings, where each string is a line of the ASCII art:

```json
{
  "tubby": [
    "  /\\ ___ /\\",
    " (  o   o  )",
    "  \\  >#<  /",
    "  /       \\",
    " /         \\       ^",
    "|           |     //",
    " \\         /    //",
    "  ///  ///   --"
  ]
}
```

### Processing

The core library processes these arrays by joining them with newline characters to create a single, properly formatted string:

```javascript
catNames.forEach(function (name) {
  cats[name] = cats[name].join('\n')
})
```

### Selection Logic

When a user requests a random cat, the library uses a simple random selection algorithm:

```javascript
cat = cat || catNames[~~(Math.random() * catNames.length)]
```

This selects a random index from the available cat names and retrieves the corresponding cat.

## Design Decisions

1. **Simplicity**: The architecture prioritizes simplicity and ease of use over complex features
2. **Modularity**: Clear separation between data, core functionality, and interfaces
3. **Minimal Dependencies**: Only one runtime dependency (yargs) to keep the package lightweight
4. **Standard Compliance**: Follows JavaScript Standard Style for code consistency
5. **Test Coverage**: Basic test coverage to ensure functionality works as expected

