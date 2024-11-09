# EOL Converter

A simple Python utility for converting end-of-line (EOL) characters in files to the appropriate format for your operating system. This is especially useful when working with `.sh` scripts or other files created on Windows that need to be compatible with Unix/Linux systems.

## Why Use EOL Converter?

When `.sh` files are created on Windows, they typically use `\r\n` line endings. If transferred directly to a Unix/Linux environment, these scripts may encounter errors because Unix-based systems expect `\n` line endings. This tool automates the process of converting EOL characters, ensuring compatibility across operating systems.

## Common Error: Container Command Not Found

If you see an error like:

```plaintext
docker: Error response from daemon: Container command '/start.sh' not found or does not exist.
```
This may indicate that the .sh script has incorrect EOL characters for the environment. Windows-style line endings (\r\n) can make the script unreadable in Unix/Linux-based containers, causing this error. Running this EOL Converter on the script before using it in Docker should resolve the issue.

## Features

- Detects the current operating system and automatically applies the correct EOL character.
- Ensures scripts and files are compatible across Windows, Unix, Linux, and MacOS.
- Simple and easy-to-use interface.

## Requirements

- Python 3.x

## Usage

1. **Clone the repository**:
    ```bash
    git clone https://github.com/NotYuSheng/eol-converter.git
    cd eol-converter
    ```

2. **Run the Script**:
    Run the Python script, and it will prompt you to enter the path of the `.sh` file or any other text file that requires EOL conversion.
    ```bash
    python convert_eol.py
    ```
    After running, enter the path to your file:
    ```plaintext
    Enter the path to the .sh file to convert EOL characters: /path/to/your-script.sh
    ```

3. **File Conversion**:
    The script reads the file, replaces the existing EOL characters with the correct format for your OS, and writes it back. It will confirm completion with a message.

## Example

To convert a file called `example-script.sh` located in the same directory:
```plaintext
Enter the path to the .sh file to convert EOL characters: example-script.sh
```
After running, you’ll see:
```
Converted EOL characters in example-script.sh to '\n'
```

## Limitations

This script assumes standard operating system EOL characters:
- Windows: `\r\n`
- Unix/Linux/MacOS: `\n`

If the script is run on unsupported operating systems, it will raise an `OSError`.

## License

This project is licensed under the MIT License.
