# 🎮 Tic-Tac-Toe SFML

## 📝 Description

This is a Tic-Tac-Toe game developed in C++ using the SFML library. It implements an intuitive graphical interface and fluid gameplay mechanics, allowing keyboard interaction.

## 🚀 Highlighted Skills

- ✅ C++ programming.

- ✅ Use of SFML for graphics and events.

- ✅ Modular architecture with lambda functions.

- ✅ Event handling and collision detection.

- ✅ Development in Visual Studio 2022.

- ✅ Creation of an interactive 2D experience.

## 🎮 Features

- 🏁 Drawing the grid and tick marks (X and O) using SFML.

- 🎯 Cursor control with WASD keys.

- ✍️ Selecting boxes with the Spacebar.

- 🔄 Restart the game with the Esc key.

- 🏆 Win detection with highlighted line.

## 🛠 Requirements

To compile and run the game, you need:

- ⚙️ SFML 2.6 installed on your system.

- 🖥 Visual Studio 2022 or a compatible C++ compiler.

## 📥 Installation and Running

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/tuusuario/tic-tac-toe-sfml.git
cd tic-tac-toe-sfml
```
### 2️⃣ Compile the Project (G++)
```sh
g++ main.cpp -o TicTacToe -lsfml-graphics -lsfml-window -lsfml-system
```
### 3️⃣ Run the Game
```sh
./TicTacToe
```
## 🎮 Controls

| Action                     | Key   |
|:---------------------------|--------:|
| ⬅️ Move cursor left       | A       |
| ➡️ Move cursor right      | D       |
| ⬆️ Move cursor up         | W       |
| ⬇️ Move cursor down       | S       |
| ❌ Select box             |SpaceBar |
| 🔄 Restart game           | Esc     |

## 🖥️ Featured Code Snippets

🔹 Grid Drawing
```sh
// Función lambda para dibujar la cuadrícula
auto DrawGrid = [&](float space, float width, float position_x, float position_y) {
    line.setSize({ space * 3, width });
    line.setOrigin(line.getLocalBounds().width / 2, line.getLocalBounds().height / 2);
    line.setFillColor(sf::Color(128, 128, 128));
    
    // Líneas horizontales
    line.setRotation(0.f);
    line.setPosition({ position_x, position_y - space/2 });
    window.draw(line);
    line.setPosition({ position_x, position_y + space / 2 });
    window.draw(line);
    
    // Líneas verticales
    line.setRotation(90.f);
    line.setPosition({ position_x - space / 2, position_y });
    window.draw(line);
    line.setPosition({ position_x + space / 2, position_y });
    window.draw(line);
};
```

📌 This snippet uses a lambda function to dynamically draw the game grid.

🔹 Cursor Handling and Keyboard Input
```sh
// Evento de teclado para mover el cursor
if ((event.key.scancode == sf::Keyboard::Scancode::A) and (cursor_x > 0)) cursor_x--;
else if ((event.key.scancode == sf::Keyboard::Scancode::D) and (cursor_x < 2)) cursor_x++;
else if ((event.key.scancode == sf::Keyboard::Scancode::W) and (cursor_y > 0)) cursor_y--;
else if ((event.key.scancode == sf::Keyboard::Scancode::S) and (cursor_y < 2)) cursor_y++;

// Selección de casilla con espacio
if ((event.key.scancode == sf::Keyboard::Scancode::Space) and (state[cursor_y][cursor_x] == ' ')) {
    state[cursor_y][cursor_x] = is_X_turn ? 'X' : 'O';
    is_X_turn = not is_X_turn;
}
```

📌 SFML event detection is used to enable cursor control and checkbox selection.

🔹 Victory Detection
```sh
// Comprobación de líneas horizontales y verticales
for (int i = 0; i < 3; i++) {
    if ((state[i][0] != ' ') and (state[i][0] == state[i][1]) and (state[i][1] == state[i][2])) {
        winner = state[i][0];
    }
    if ((state[0][i] != ' ') and (state[0][i] == state[1][i]) and (state[1][i] == state[2][i])) {
        winner = state[0][i];
    }
}
```

📌 The game detects if a player has won by checking rows and columns with the same symbol.

## 📸 Screenshots

![image](https://github.com/user-attachments/assets/fefe0674-f47e-4b03-8795-282efcd7ba4a)

## 🔧 Possible Improvements

- 🎨 **More Attractive Interface**: Add animations and visual effects to improve the user experience.
- 🤖 **Artificial Intelligence**: Implement a mode to play against the computer with different difficulty levels.
- 🌍 **Online Multiplayer Mode**: Integrate a network connection to play against other players over the internet.
- 📱 **Mobile Version**: Adapt the game for mobile devices with touch controls.
- 🔊 **Sound Effects**: Add sounds when selecting squares or winning a match to make the experience more immersive.
- 📊 **Scoring System**: Save win and loss statistics for each player.

## 📜 License

This project is licensed under the MIT License. See the LICENSE file for details.
