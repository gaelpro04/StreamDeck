# Programmable 4x4 Macro Keypad

A desktop application built in Java and JavaFX that serves as the configuration and control software for a custom-built programmable 4×4 macro keypad. The app communicates in real time with the hardware via serial communication, allowing users to configure and execute macros through a graphical interface.

![Macro Keypad screenshot 1](./public/movieLens1.png)
![Macro Keypad screenshot 2](./public/movieLens1.png)

## Features

- Interactive 4×4 visual representation of the keypad
- Dynamic macro configuration per key through a GUI
- Real-time serial communication with the external device
- Background service via Windows System Tray — app keeps running after the window is closed
- Dark-themed responsive interface built with JavaFX
- Modular MVC-inspired architecture separating UI, business logic, and communication layers

## Tech Stack

- Java
- JavaFX (UI framework)
- Java AWT (System Tray integration)
- jSerialComm (serial communication library)
- Object-Oriented Programming
- Multithreading / Concurrent Programming

## Architecture

JavaFX Interface
↓
Application Logic (Macro Management, Action Dispatcher, Validation)
↓
Communication Layer (Serial Port Manager, Packet Processing)
↓
External Device (ESP32-S3 Microcontroller)

A dedicated background thread continuously listens to the serial port while the JavaFX Application Thread handles rendering. UI updates from the background thread are safely dispatched using `Platform.runLater()` to avoid thread-safety issues.
