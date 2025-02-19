# 🎮 Tic-Tac-Toe en SFML



## 📝 Descripción

Este es un juego de Tic-Tac-Toe desarrollado en C++ utilizando la biblioteca SFML. Implementa una interfaz gráfica intuitiva y mecánicas de juego fluidas, permitiendo la interacción mediante teclado.


## 🚀 Habilidades Destacadas

- ✅ Programación en C++.

- ✅ Uso de SFML para gráficos y eventos.

- ✅ Arquitectura modular con lambda functions.

- ✅ Manejo de eventos y detección de colisiones.

- ✅ Desarrollo en Visual Studio 2022.

- ✅ Creación de una experiencia interactiva en 2D.


## 🎮 Características

- 🏁 Dibujado de la cuadrícula y las marcas (X y O) mediante SFML.

- 🎯 Control del cursor con teclas WASD.

- ✍️ Selección de casillas con la tecla Espacio.

- 🔄 Reinicio del juego con la tecla Esc.

- 🏆 Detección de victoria con línea resaltada.

## 🛠 Requisitos

Para compilar y ejecutar el juego, necesitas:

- ⚙️ SFML 2.6 instalado en tu sistema.

- 🖥 Visual Studio 2022 o compilador C++ compatible.

## 📥 Instalación y Ejecución

### 1️⃣ Clonar el Repositorio
```sh
git clone https://github.com/tuusuario/tic-tac-toe-sfml.git
cd tic-tac-toe-sfml
```
### 2️⃣ Compilar el Proyecto (G++)
```sh
g++ main.cpp -o TicTacToe -lsfml-graphics -lsfml-window -lsfml-system
```
### 3️⃣ Ejecutar el Juego
```sh
./TicTacToe
```
## 🎮 Controles

| Acción                     | Tecla   |
|:---------------------------|--------:|
| ⬅️ Mover cursor izquierda  | A       |
| ➡️ Mover cursor derecha    | D       |
| ⬆️ Mover cursor arriba     | W       |
| ⬇️ Mover cursor abajo      | S       |
| ❌ Seleccionar casilla     | Espacio |
| 🔄 Reiniciar juego        | Esc     |

## 🖥️ Fragmentos de Código Destacados

🔹 Dibujado de la Cuadrícula
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

📌 Este fragmento usa una función lambda para dibujar la cuadrícula del juego dinámicamente.

🔹 Manejo del Cursor y Entrada de Teclado
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

📌 Se utiliza la detección de eventos de SFML para permitir el control del cursor y la selección de casillas.

🔹 Detección de Victoria
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

📌 El juego detecta si un jugador ha ganado comprobando filas y columnas con el mismo símbolo.

## 📸 Capturas de Pantalla

![image](https://github.com/user-attachments/assets/fefe0674-f47e-4b03-8795-282efcd7ba4a)

## 🔧 Posibles Mejoras

- 🎨 **Interfaz más atractiva**: Agregar animaciones y efectos visuales para mejorar la experiencia del usuario.
- 🤖 **Inteligencia Artificial**: Implementar un modo para jugar contra la computadora con diferentes niveles de dificultad.
- 🌍 **Modo Multijugador en Línea**: Integrar conexión en red para jugar contra otros jugadores a través de Internet.
- 📱 **Versión Móvil**: Adaptar el juego para dispositivos móviles con controles táctiles.
- 🔊 **Efectos de Sonido**: Añadir sonidos al seleccionar casillas o ganar una partida para hacer la experiencia más inmersiva.
- 📊 **Sistema de Puntuación**: Guardar estadísticas de victorias y derrotas de cada jugador.

## 📜 Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.
