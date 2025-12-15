# 🍕 Pizza Delivery - Tracking en Tiempo Real

Ejemplo de sistema de pedidos de pizza con tracking en tiempo real utilizando **[Relay Gateway](https://github.com/Coderic/Relay)**.

![HTML](https://img.shields.io/badge/HTML5-E34F26?logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript)
![Relay](https://img.shields.io/badge/Relay-Gateway-blueviolet)

## 📖 Sobre este Ejemplo

Este ejemplo funcional demuestra cómo construir un sistema de pedidos de pizza con tracking en tiempo real, sincronizando estados entre múltiples vistas (cliente y cocina). Este ejemplo muestra:

- 🍕 **Vista Cliente** - Selecciona pizzas del menú y realiza pedidos
- 👨‍🍳 **Vista Cocina** - Gestiona los pedidos y actualiza estados
- ⚡ **Tracking en tiempo real** - Observa el progreso de tu pedido en tiempo real
- 📊 **Estados del pedido**:
  1. 📝 **Recibido** - Pedido registrado
  2. 👨‍🍳 **Preparando** - En la cocina
  3. 🔥 **Horneando** - En el horno
  4. ✅ **Listo** - Esperando repartidor
  5. 🛵 **En Camino** - El repartidor va hacia ti
  6. 🎉 **Entregado** - ¡Buen provecho!

Este ejemplo pertenece a la colección de ejemplos de **[Relay Gateway](https://github.com/Coderic/Relay)**, un gateway de comunicación en tiempo real diseñado para ser inmutable y agnóstico.

## 🚀 Inicio Rápido

### Prerrequisitos

- Un navegador web moderno
- Relay Gateway ejecutándose (ver [documentación de Relay](https://relay.coderic.net))

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/Coderic/pizza-delivery.git
cd pizza-delivery
```

No se requiere instalación de dependencias, este ejemplo usa CDN para las librerías.

### Configuración

Abre `index.html` en tu navegador o sirve los archivos con un servidor HTTP simple:

```bash
# Con Python
python3 -m http.server 8000

# Con Node.js (http-server)
npx http-server -p 8000

# Con PHP
php -S localhost:8000
```

El ejemplo se conecta automáticamente a `http://demo.relay.coderic.net` (endpoint público de Relay para pruebas).

Para usar Relay localmente, modifica el archivo `conector.js`:

```javascript
const relay = new RelayConector('http://localhost:5000');
```

Y ejecuta Relay:

```bash
# Opción 1: Con npx (recomendado para pruebas)
npx @coderic/relay

# Opción 2: Con Docker Compose
docker compose up -d
```

## 🎯 Uso

1. **Abrir dos pestañas** del navegador:
   - **Pestaña 1**: Vista Cliente (🛒 Cliente)
   - **Pestaña 2**: Vista Cocina (👨‍🍳 Cocina)
2. **En la vista Cliente**: Selecciona una pizza del menú y realiza un pedido
3. **En la vista Cocina**: Observa cómo aparece el nuevo pedido y actualiza su estado
4. **En la vista Cliente**: Observa cómo el tracking se actualiza en tiempo real según la cocina cambia el estado

## 🔗 Enlaces

- 📦 [Repositorio](https://github.com/Coderic/pizza-delivery)
- 🐛 [Issues](https://github.com/Coderic/pizza-delivery/issues)
- 🌐 [Demo en línea](https://coderic.org/pizza-delivery/)
- 📚 [Documentación de Relay](https://relay.coderic.net)
- ⚡ [Relay Gateway](https://github.com/Coderic/Relay)

## 🛠️ Tecnologías

- **HTML5** - Estructura de la aplicación
- **JavaScript (ES6+)** - Lógica de la aplicación
- **Socket.io** - Comunicación WebSocket (via CDN)
- **Relay Gateway** - Gateway de comunicación en tiempo real
- **RelayConector** - Cliente JavaScript para conectar con Relay

## 📝 Licencia

MIT
