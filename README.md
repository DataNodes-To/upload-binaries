# DataNodes Upload - Compiled Binaries

Pre-compiled binaries for all major platforms. No dependencies required.

> **Looking for source code?** See the [upload-sdk](https://github.com/DataNodes-To/upload-sdk) repository.

## Available Binaries

### Go (Recommended - Fastest & Smallest)

| Platform | Architecture | Filename | Size |
|----------|--------------|----------|------|
| Linux | x64 | `datanodes-upload-linux-amd64` | 6.2 MB |
| Linux | ARM64 | `datanodes-upload-linux-arm64` | 5.4 MB |
| macOS | Intel | `datanodes-upload-macos-amd64` | 5.9 MB |
| macOS | Apple Silicon | `datanodes-upload-macos-arm64` | 5.5 MB |
| Windows | x64 | `datanodes-upload-windows-amd64.exe` | 5.9 MB |

### Node.js

| Platform | Architecture | Filename | Size |
|----------|--------------|----------|------|
| Linux | x64 | `datanodes-upload-node-linux-x64` | 72 MB |
| Linux | ARM64 | `datanodes-upload-node-linux-arm64` | 43 MB |
| macOS | Intel | `datanodes-upload-node-macos-x64` | 71 MB |
| macOS | Apple Silicon | `datanodes-upload-node-macos-arm64` | 45 MB |
| Windows | x64 | `datanodes-upload-node-win-x64.exe` | 55 MB |

### Python

| Platform | Architecture | Filename | Size |
|----------|--------------|----------|------|
| Linux | x64 | `datanodes-upload-python-linux-amd64` | 9.9 MB |

> **Note:** Python binaries can only be compiled for the current platform. For macOS/Windows Python binaries, run PyInstaller on those platforms.

### Scripts (Require Interpreter)

These cannot be compiled to binaries and require their respective interpreters:

| Language | File | Requirements |
|----------|------|--------------|
| Bash | `datanodes-upload.sh` | bash, curl, jq, bc |
| PHP | `datanodes-upload.php` | PHP 7.4+ with curl |
| PowerShell | `datanodes-upload.ps1` | PowerShell 5.1+ |

## Usage

### Linux / macOS

```bash
# Make executable
chmod +x datanodes-upload-linux-amd64

# Run
./datanodes-upload-linux-amd64 myfile.zip YOUR_API_KEY
```

### Windows

```cmd
datanodes-upload-windows-amd64.exe myfile.zip YOUR_API_KEY
```

## Options

```
-t, --threads N     Parallel upload threads (default: 10)
-r, --retries N     Max retries per chunk (default: 3)
-f, --folder ID     Destination folder ID (default: 0)
-d, --directory     Upload all files from directory
-R, --recursive     Include subdirectories (with -d)
-h, --help          Show help message
```

## Examples

```bash
# Upload single file
./datanodes-upload-linux-amd64 myfile.zip YOUR_API_KEY

# Upload with 20 threads to folder 123
./datanodes-upload-linux-amd64 -t 20 -f 123 myfile.zip YOUR_API_KEY

# Upload folder recursively
./datanodes-upload-linux-amd64 -d /path/to/folder -R YOUR_API_KEY
```

## Which Binary Should I Use?

| Priority | Binary | Why |
|----------|--------|-----|
| 1st | **Go** | Fastest (885 MB/s), smallest (6 MB), all platforms |
| 2nd | Python | Good speed (930 MB/s), medium size (10 MB), Linux only |
| 3rd | Node.js | Good speed (~590 MB/s), larger size (43-72 MB), all platforms |
