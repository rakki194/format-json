# format-json

## Overview

format-json is a simple and efficient tool for formatting JSON files. It recursively scans directories for files with the `.json` extension and automatically re-formats them to be more readable with proper indentation.

This tool is built using Rust and leverages asynchronous processing through Tokio. It utilizes several Rust crates to accomplish its tasks:

- **xio**: Provides a convenient function to walk through directories.
- **dset**: Contains the core JSON formatting logic.
- **serde_json**: Used for parsing and printing JSON.
- **walkdir**: For recursively traversing directories.
- **tokio**: Provides the asynchronous runtime.
- **anyhow**: Simplifies error handling.
- **tempfile** (dev-dependency): Facilitates testing by handling temporary files.

## Features

- **Recursive Directory Traversal**: Finds all JSON files in the specified directory and its subdirectories.
- **Automatic JSON Formatting**: Reformats JSON files to use a standardized, pretty-print style.
- **Asynchronous Execution**: Uses Tokio to handle file processing concurrently, improving performance.
- **Command-Line Interface**: Accepts an optional directory path. Defaults to the current working directory if none is provided.
- **Built-in Testing**: Contains tests to ensure functionality and correct formatting of JSON files.

## Installation

To build format-json, ensure you have Rust and Cargo installed. Then, clone the repository and run:

```bash
cargo build --release
```

This will compile the project in release mode.

## Usage

You can run format-json either via Cargo or by using the compiled binary.

### Running with Cargo

To format JSON files in the current directory:

```bash
cargo run
```

To specify a different directory, provide the path as an argument:

```bash
cargo run -- /path/to/directory
```

### Running the Compiled Binary

After building the project, the binary will be located in `target/release`. Run it using:

```bash
./target/release/format-json /path/to/directory
```

If no directory is provided, the tool will default to using the current working directory.

## Testing

Run the tests with:

```bash
cargo test
```

The tests include a sample JSON file formatting test to ensure the tool produces the expected output.

## Code Structure

- **Cargo.toml**: Contains package metadata and dependency information.
- **src/main.rs**: Implements the main logic, including recursive directory traversal and JSON formatting.

The project leverages helper crates (`xio` and `dset`) for core functionalities, ensuring modular and maintainable code.

## Contributing

Contributions are welcome! Please feel free to open issues or submit pull requests if you have suggestions or improvements.

## License

This project is licensed under [Insert License Here] (modify this section based on your chosen license).

## Author

Balazs Horvath

## Acknowledgements

Thanks to the authors of the Rust crates that make this project possible!
