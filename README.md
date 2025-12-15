# 🍕 Pizza Delivery - Tracking en Tiempo Real

Ejemplo de sistema de pedidos de pizza con tracking en tiempo real utilizando [Relay Gateway](https://github.com/NeftaliYagua/Relay).

![Demo](https://img.shields.io/badge/demo-online-green)

## 🚀 Inicio Rápido

### Prerrequisitos

1. Tener Relay Gateway ejecutándose en `http://localhost:5000`

```bash
# Opción 1: Con Docker Compose (recomendado)
cd infraestructura && docker compose up -d

# Opción 2: Directo con npx
npx relay-gateway
```

### Ejecutar el ejemplo

```bash
# Clonar este repositorio
git clone https://github.com/Coderic/relay-ejemplo-pizza-delivery.git
cd relay-ejemplo-pizza-delivery

# Servir los archivos estáticos
npx serve -p 8001
```

Abre http://localhost:8001 en tu navegador.

## 📖 Características

- **Vista Cliente**: Selecciona pizzas y realiza pedidos
- **Vista Cocina**: Gestiona los pedidos y actualiza estados
- **Tracking en tiempo real**: Observa el progreso de tu pedido

### Estados del pedido

1. 📝 **Recibido** - Pedido registrado
2. 👨‍🍳 **Preparando** - En la cocina
3. 🔥 **Horneando** - En el horno
4. ✅ **Listo** - Esperando repartidor
5. 🛵 **En Camino** - El repartidor va hacia ti
6. 🎉 **Entregado** - ¡Buen provecho!

## 💻 Cómo funciona

```javascript
// Conectar a Relay
const relay = new RelayConector('http://localhost:5000');
await relay.conectar();

// Enviar nuevo pedido (cliente)
relay.enviarATodos({
  tipo: 'nuevo_pedido',
  pedidoId: 'ABC123',
  pizza: 'Pepperoni',
  precio: 14.99
});

// Actualizar estado (cocina)
relay.enviarATodos({
  tipo: 'estado_pedido',
  pedidoId: 'ABC123',
  estado: 'preparando'
});

// Escuchar actualizaciones
relay.on('relay', (data) => {
  if (data.tipo === 'estado_pedido') {
    actualizarTracking(data.estado);
  }
});
```

## 📁 Estructura

```
├── index.html      # Interfaz cliente/cocina
├── conector.js     # Cliente Relay para navegador
├── package.json
└── README.md
```

## 🔗 Enlaces

- [Relay Gateway](https://github.com/NeftaliYagua/Relay)
- [Documentación](https://neftaliyagua.github.io/Relay/)
- [Otros ejemplos](https://github.com/Coderic?q=relay-ejemplo)

## 📄 Licencia

MIT © [Coderic](https://github.com/Coderic)

