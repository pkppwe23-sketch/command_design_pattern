# Command Design Pattern in C++

A simple C++ implementation of the **Command Design Pattern** using a remote controller that operates a light and a fan. Each button toggles its assigned device ON and OFF, demonstrating command execution and undo behavior.

## Features

- Command interface with `execute()` and `undo()`
- Concrete commands for a light and a fan
- Remote controller acting as the invoker
- Four configurable buttons
- Toggle behavior: first press executes the command; the next press undoes it
- Message shown when a button has no command assigned

## Design Pattern Roles

| Role | Class | Responsibility |
|---|---|---|
| Command | `Command` | Defines `execute()` and `undo()` |
| Receiver | `Light`, `Fan` | Performs the actual device operations |
| Concrete Command | `LightCommand`, `FanCommand` | Connects a command to a receiver |
| Invoker | `RemoteController` | Assigns commands to buttons and triggers them |

## How It Works

1. Create a light and a fan.
2. Assign `LightCommand` to button 0 and `FanCommand` to button 1.
3. Pressing an assigned button executes its command when the button is OFF.
4. Pressing it again invokes `undo()`, turning the device OFF.
5. Pressing an unassigned button displays a message.

## Compile and Run

Requires a C++ compiler such as g++.

```bash
g++ main.cpp -o command_pattern
./command_pattern
```

On Windows, run the generated executable with:

```powershell
.\command_pattern.exe
```

## Sample Output

```text
--- Toggling Light Button 0 ---
Light is ON
Light is OFF
--- Toggling Fan Button 1 ---
Fan is ON
Fan is OFF
--- Pressing Unassigned Button 2 ---
No command assigned at button 2
```

## Concepts Demonstrated

- Behavioral design patterns
- Polymorphism through an abstract command interface
- Loose coupling between the invoker and receivers
- Undo behavior for device operations

## Repository Structure

```text
command_design_pattern/
├── main.cpp
└── README.md
```
