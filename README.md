
# Encrypted Client-Bug-Server System (Enhanced Version)

This project implements a secure, restartable, and extensible socket-based communication system using Python.

## 📦 Components

- `client_enhanced.py`: Sends commands using JSON, handles RSA encryption, logging, and graceful restart.
- `bug_enhanced.py`: Acts as a secure proxy (middleware), decrypts and re-encrypts all traffic, logs data.
- `legacy_application_enhanced.py`: Final recipient server handling structured commands with logging and restart control.
- `config_enhanced.ini`: Central config for ports and IPs.

## 🔐 Features

- **RSA Encryption**: All messages between Client → Bug → Legacy are encrypted.
- **Digital Signature Ready**: Structure supports future digital signature validation.
- **JSON Messaging**: All communication is now structured (e.g. `{"command": "own"}`).
- **Structured Command Routing**: Handled by Bug and Legacy based on JSON input.
- **Logging**: All systems log to their respective log files (client_log.txt, bug_log.txt, legacy_log.txt).
- **Restart Control**: After `ext` command, system prompts for restart at both Client and Server sides.
- **Socket Reuse**: Prevents port reuse errors via `SO_REUSEADDR`.
- **Error Handling**: Graceful fallback on disconnects or malformed data.
