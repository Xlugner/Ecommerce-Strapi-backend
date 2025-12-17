# Backend Ecommerce con Strapi

Backend potente y flexible para la tienda online, construido con Strapi v5. Proporciona una API RESTful completa para gestionar productos, categorías, pedidos y más.

## 🚀 Características

- 🛍️ Gestión completa de productos y categorías
- 🔐 Autenticación JWT integrada
- 📦 API RESTful con documentación automática
- 🎨 Panel de administración personalizable
- 🌍 Soporte multilingüe (español por defecto)
- 🛠️ Fácil de extender con plugins personalizados
- 🚀 Listo para producción

## 🛠️ Requisitos

- Node.js >= 18.0.0
- npm >= 8.0.0
- SQLite (por defecto) o base de datos compatible (PostgreSQL, MySQL, etc.)

## 🚀 Instalación

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/Xlugner/Ecommerce-Strapi-backend.git
   cd Ecommerce-Strapi-backend
   ```

2. Instalar dependencias:
   ```bash
   npm install
   ```

3. Configurar variables de entorno:
   ```bash
   cp .env.example .env
   ```
   Editar el archivo `.env` con tus configuraciones

4. Iniciar el servidor de desarrollo:
   ```bash
   npm run develop
   ```

El panel de administración estará disponible en: [http://localhost:1337/admin](http://localhost:1337/admin)

## 🏗️ Estructura del proyecto

```text
src/
├── api/                  # Endpoints de la API
│   ├── category/        # Modelo de categorías
│   ├── order/           # Modelo de pedidos
│   ├── product/         # Modelo de productos
│   └── ...
├── components/          # Componentes reutilizables
├── extensions/          # Extensiones personalizadas
└── admin/               # Personalización del panel de administración
```

## 🔧 Variables de entorno

Crea un archivo `.env` en la raíz del proyecto:

```env
# Configuración básica
HOST=0.0.0.0
PORT=1337
NODE_ENV=development

# Base de datos (SQLite por defecto)
DATABASE_CLIENT=sqlite
DATABASE_FILENAME=.tmp/data.db

# Seguridad
APP_KEYS=your-app-keys
API_TOKEN_SALT=your-api-token-salt
ADMIN_JWT_SECRET=your-admin-jwt-secret
TRANSFER_TOKEN_SALT=your-transfer-token-salt

# URLs
APP_URL=http://localhost:1337
ADMIN_URL=/dashboard
```

## 🚀 Comandos útiles

| Comando                | Acción                                      |
|------------------------|--------------------------------------------|
| `npm run develop`     | Inicia el servidor en modo desarrollo      |
| `npm run start`       | Inicia el servidor en producción          |
| `npm run build`       | Construye el proyecto para producción     |
| `npm run strapi`      | Ejecuta comandos de la CLI de Strapi      |
| `npm run generate:key`| Genera claves de seguridad               |

## 🛠️ Modelos de datos

### Producto
- `name` (Texto, requerido)
- `description` (Texto largo)
- `price` (Decimal, requerido)
- `stock` (Entero)
- `images` (Media, múltiple)
- `category` (Relación con Categoría)
- `isFeatured` (Booleano)

### Categoría
- `name` (Texto, requerido)
- `description` (Texto largo)
- `slug` (Texto único, generado automáticamente)

### Pedido
- `user` (Relación con Usuario)
- `products` (JSON con productos y cantidades)
- `total` (Decimal)
- `status` (Texto: 'pendiente', 'procesando', 'enviado', 'entregado')
- `shippingAddress` (JSON con dirección de envío)

## 🔄 API Endpoints

### Autenticación
- `POST /api/auth/local` - Iniciar sesión
- `POST /api/auth/local/register` - Registrarse
- `GET /api/users/me` - Obtener perfil de usuario

### Productos
- `GET /api/products` - Listar productos
- `GET /api/products/:id` - Obtener producto por ID
- `GET /api/products?filters[category][slug][$eq]=categoria` - Filtrar por categoría

### Categorías
- `GET /api/categories` - Listar categorías
- `GET /api/categories/:id` - Obtener categoría por ID

## 🔒 Permisos

Asegúrate de configurar los permisos correctamente en el panel de administración de Strapi (`/admin/settings/users-permissions/roles`).

## 🚀 Despliegue

### Opciones recomendadas:

1. **Railway**
   - [![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template?template=strapi)

2. **Heroku**
   ```bash
   heroku create
   git push heroku main
   ```

3. **VPS tradicional**
   - Instalar Node.js, Nginx, PM2
   - Configurar base de datos PostgreSQL
   - Configurar dominio y certificados SSL

## 🛠️ Desarrollo

### Crear un nuevo modelo
```bash
npm run strapi generate:api product
```

### Crear un nuevo controlador
```bash
npm run strapi generate:controller product
```

### Crear un nuevo servicio
```bash
npm run strapi generate:service product
```

## 🤝 Contribución

1. Haz un fork del proyecto
2. Crea una rama para tu feature (`git checkout -b feature/amazing-feature`)
3. Haz commit de tus cambios (`git commit -m 'Add some amazing feature'`)
4. Haz push a la rama (`git push origin feature/amazing-feature`)
5. Abre un Pull Request

## 📄 Licencia

Distribuido bajo la licencia MIT. Ver `LICENSE` para más información.

## ✉️ Contacto

Tu Nombre - [@tuusuario](https://t.me/Rzoux) - email@ejemplo.com

Enlace al proyecto: [https://github.com/Xlugner/Ecommerce-Strapi-backend](https://github.com/Xlugner/Ecommerce-Strapi-backend)

---

Hecho con ❤️ por Xlugner
