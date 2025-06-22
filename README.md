# parquediversiones
##Descripción

Cada visitante es un hilo (`Thread`) que intenta subirse a una atracción. Cada atracción tiene una capacidad máxima. Si la atracción está llena, el visitante espera un tiempo y luego intenta nuevamente, ya sea en la misma o en otra atracción.

Se utiliza `tryLock()` para permitir intentos de acceso con tiempo limitado, lo que simula una experiencia más realista de "esperar turno" o "ir a otra atracción".

#Estructura del Código

- `Atraccion`: Clase que representa una atracción con capacidad máxima y control de acceso usando `ReentrantLock`.
- `Visitante`: Hilo que representa un visitante que intenta subirse a las atracciones.
- `ParqueAtracciones`: Clase principal con el método `main` que inicia la simulación.


- **`ReentrantLock` + `tryLock()`**: simula tiempo de espera y evita que los hilos se bloqueen indefinidamente.
- **Capacidad limitada**: Cada atracción tiene un contador  para asegurar que no se exceda el límite.
- **Intentos limitados por visitante**: Cada visitante intenta subir hasta 5 veces antes de rendirse.
- **Simulación realista**: (`Thread.sleep()`) para simular el tiempo de espera o disfrute en la atracción.
