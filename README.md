🤖 Telegram Pedido Bot

Bot de Telegram en **Python** que permite a los usuarios realizar pedidos (series, películas, juegos u otros) y a los administradores gestionarlos fácilmente mediante comandos y botones interactivos.
Incluye sistema multilenguaje, soporte privado, administración de usuarios, estadísticas, limpieza automática de pedidos y copias de seguridad.

---

📋 Características principales

- 📝 **Pedidos de usuarios:** los usuarios pueden crear pedidos con descripción y tipo.
- ⚙️ **Panel de administración:** control de pedidos, exportación, backups y mensajes globales.
- 🌐 **Idiomas:** soporte para **Español** e **Inglés**.
- 🧑‍💼 **Gestión de roles:** usuarios, administradores y dueño del bot.
- 💬 **Soporte directo:** los usuarios pueden chatear con los administradores vía `/chatadmin`.
- 🧹 **Mantenimiento automático:** limpieza de pedidos antiguos cada 24 horas.
- 💾 **Base de datos SQLite asíncrona** (usando `aiosqlite`).
- 📤 **Exportación a CSV** y **backups automáticos** de la base de datos.

---

🧠 Tecnologías usadas

- **Python 3.10+**
- [python-telegram-bot](https://python-telegram-bot.org/) `v21.4`
- [aiosqlite](https://pypi.org/project/aiosqlite/)
- [python-dotenv](https://pypi.org/project/python-dotenv/)

---

⚙️ Instalación y configuración

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/tuusuario/telegram-pedido-bot.git
   cd telegram-pedido-bot
   ```

2. **Instalar dependencias**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configurar el bot**
   Edita el archivo [`config.py`](config.py) con tus credenciales de Telegram:

   ```python
   API_ID = 1234567
   API_HASH = "tu_api_hash"
   BOT_TOKEN = "token_del_bot"
   CANAL_USERNAME = "https://t.me/tu_canal"
   GRUPO_USERNAME = "tu_grupo"
   OWNER_ID = 123456789
   ADMIN_GROUP_ID = -100XXXXXXXXXX
   DB_PATH = "bot_pedidos.db"
   ```

4. **Inicializar la base de datos**
   El bot crea automáticamente las tablas necesarias en el primer inicio gracias a `init_db()`.

---

🚀 Ejecución

Para iniciar el bot:

```bash
python main.py
```

El bot usará **long polling** para escuchar los mensajes y comandos de los usuarios.

---

🧑‍💻 Comandos disponibles

👥 Usuarios
| Comando | Descripción |
|----------|--------------|
| `/start` | Inicia el bot y muestra el menú principal |
| `/mispedidos` | Muestra tus pedidos actuales |
| `/chatadmin` | Abre un chat de soporte con los administradores |
| `/cerrar` | Cierra el chat de soporte activo |
| `/idioma` | Cambia el idioma del bot |

🛠 Administradores
| Comando | Descripción |
|----------|--------------|
| `/verpedidos` | Lista los últimos pedidos |
| `/verpedido <TICKET>` | Muestra los detalles de un pedido |
| `/buscopedido <texto>` | Busca pedidos por texto |
| `/eliminarpedido <TICKET>` | Elimina un pedido |
| `/pedidolisto <TICKET>` | Marca un pedido como listo |
| `/stadistics` | Muestra estadísticas del bot |
| `/exportar` | Exporta los pedidos en CSV |
| `/backup` | Crea un backup de la base de datos |
| `/agregaradmin <ID>` | Asigna rol de admin a un usuario |
| `/eliminaradmin <ID>` | Revoca rol de admin |
| `/cerrar <user_id>` | Cierra el soporte con un usuario |

---

🧩 Estructura del proyecto

```
📁 telegram-pedido-bot/
│
├── main.py           # Lógica principal del bot
├── database.py       # Funciones de base de datos (usuarios, pedidos, soporte)
├── config.py         # Configuración del bot y credenciales
├── requirements.txt  # Dependencias del proyecto
└── README.md         # Documentación del proyecto
```

---

🧱 Base de datos

- `usuarios`: información de usuarios, idioma y rol.
- `pedidos`: pedidos con ticket, tipo, descripción, estado, fechas y asignación.
- `soporte`: historial de mensajes entre usuarios y admins.
- `config`: valores de configuración persistentes.

---

🔐 Seguridad

⚠️ **Importante:**
No compartas tu archivo `config.py` con información sensible (tokens, API keys o IDs).
Para uso público en GitHub, reemplaza los valores reales con placeholders.

Ejemplo seguro:
```python
BOT_TOKEN = "YOUR_BOT_TOKEN_HERE"
```

---

🧾 Licencia

Este proyecto se distribuye bajo la **MIT License**.
Puedes usarlo, modificarlo y distribuirlo libremente, dando crédito al autor original.

---

💬 Créditos

Desarrollado por **jvc**
📢 Canal: [@techgeniusjvc](https://t.me/techgeniusjvc)