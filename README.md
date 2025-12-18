# 🎮 TrivIAndo - Plataforma de Trivias Inteligentes en Tiempo Real

![React](https://img.shields.io/badge/React-18.3.1-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.5.3-blue?logo=typescript)
![Vite](https://img.shields.io/badge/Vite-7.1.12-purple?logo=vite)
![TailwindCSS](https://img.shields.io/badge/Tailwind-3.4.18-cyan?logo=tailwindcss)
![Socket.IO](https://img.shields.io/badge/Socket.IO-4.8.1-black?logo=socket.io)

Una plataforma de trivia interactiva multijugador en tiempo real con mecánicas de buzzer, chat en vivo y generación dinámica de preguntas. Desarrollada por el equipo **Pokesaurios**.

## 📋 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Stack Tecnológico](#-stack-tecnológico)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación](#-instalación)
- [Configuración](#️-configuración)
- [Scripts Disponibles](#-scripts-disponibles)
- [Arquitectura](#-arquitectura)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Equipo](#-equipo)

## ✨ Características Principales

- 🎯 **Juego Multijugador en Tiempo Real**: Salas de juego con múltiples jugadores conectados simultáneamente
- ⚡ **Sistema de Buzzer**: Mecánica de respuesta rápida para contestar primero
- 💬 **Chat en Vivo**: Sistema de mensajería instantánea dentro de las salas de juego
- 🎨 **Interfaz Animada**: Animaciones fluidas con Framer Motion para una experiencia visual atractiva
- 🔐 **Autenticación JWT**: Sistema de registro e inicio de sesión seguro
- 📊 **Sistema de Ranking**: Tabla de posiciones en tiempo real durante el juego
- 🎭 **Avatares Personalizados**: Sistema de avatares con colores y emojis únicos para cada jugador
- 📱 **Diseño Responsivo**: Interfaz adaptable a diferentes dispositivos
- 🔄 **Reconexión Automática**: Manejo robusto de conexiones WebSocket con auto-reconexión
- 📈 **Estadísticas**: Panel de estadísticas de rendimiento del jugador

## 🛠️ Stack Tecnológico

### Frontend Core
- **React 18.3.1** - Biblioteca UI con hooks y componentes funcionales
- **TypeScript 5.5.3** - Tipado estático para mayor seguridad y mantenibilidad
- **Vite 7.1.12** - Build tool ultra-rápido con HMR

### Estilos y Animaciones
- **Tailwind CSS 3.4.18** - Framework CSS utility-first
- **Framer Motion 12.23.22** - Biblioteca de animaciones para React
- **Lucide React 0.344.0** - Iconos modernos y personalizables
- **PostCSS 8.5.6** - Transformación de CSS

### Comunicación en Tiempo Real
- **Socket.IO Client 4.8.1** - Cliente WebSocket para comunicación bidireccional
- **TanStack Query 5.90.5** - Gestión de estado del servidor y caché
- **Axios** (integrado en apiClient) - Cliente HTTP para llamadas REST

### Utilidades
- **React Router DOM 7.9.4** - Enrutamiento declarativo
- **React Hot Toast 2.6.0** - Notificaciones elegantes
- **React Confetti 6.4.0** - Efectos de celebración
- **React Use 17.6.0** - Colección de hooks útiles

### Testing
- **Vitest 4.0.14** - Framework de testing rápido
- **Testing Library** - Testing centrado en el usuario
- **JSDOM 27.2.0** - Simulación del DOM para tests
- **Vitest UI** - Interfaz visual para tests
- **Coverage V8** - Análisis de cobertura de código

### Herramientas de Desarrollo
- **ESLint 9.9.1** - Linting y análisis estático
- **TypeScript ESLint** - Reglas de ESLint para TypeScript
- **Autoprefixer** - Prefijos CSS automáticos

## 📁 Estructura del Proyecto

```
triviando-frontend/
├── public/                    # Archivos estáticos
│   ├── favicon.ico
│   ├── logo180.png
│   ├── logo512.png
│   └── pokesaurios.png
├── src/
│   ├── app/                   # Páginas principales
│   │   ├── App.tsx           # Componente raíz y rutas
│   │   ├── LoginPage.tsx     # Página de autenticación
│   │   ├── DashboardPage.tsx # Panel principal
│   │   ├── CreateTriviaPage.tsx # Creación de trivias
│   │   ├── JoinRoomPage.tsx  # Unirse a sala
│   │   ├── WaitingRoomPage.tsx # Sala de espera
│   │   ├── GamePage.tsx      # Página de juego
│   │   └── StatsPage.tsx     # Estadísticas
│   ├── components/            # Componentes reutilizables
│   │   └── ui/               # Componentes UI
│   │       ├── Button.tsx
│   │       ├── InputField.tsx
│   │       ├── Alert.tsx
│   │       ├── LoadingSpinner.tsx
│   │       ├── PlayerAvatar.tsx
│   │       ├── AnimatedBackground.tsx
│   │       └── ...
│   ├── features/             # Módulos por funcionalidad
│   │   ├── auth/            # Autenticación
│   │   ├── chat/            # Sistema de chat
│   │   ├── game/            # Lógica del juego
│   │   └── waitingRoom/     # Sala de espera
│   ├── hooks/                # Custom hooks
│   │   ├── useAuthForm.ts
│   │   ├── useGameSocket.ts
│   │   ├── useRoomSocket.ts
│   │   ├── useChat.ts
│   │   └── ...
│   ├── lib/                  # Bibliotecas y utilidades
│   │   ├── api/             # Cliente API y middleware
│   │   │   ├── apiClient.ts
│   │   │   ├── middleware.ts
│   │   │   ├── normalizers.ts
│   │   │   └── queryClient.ts
│   │   ├── services/        # Servicios de negocio
│   │   │   ├── authServices.ts
│   │   │   ├── roomServices.ts
│   │   │   └── statsServices.ts
│   │   └── socket.ts        # Configuración Socket.IO
│   ├── config/              # Configuraciones
│   │   ├── constants.ts
│   │   ├── endpoints.ts
│   │   └── animations.ts
│   ├── types/               # Definiciones TypeScript
│   │   ├── auth.types.ts
│   │   ├── game.types.ts
│   │   ├── room.types.ts
│   │   ├── chat.types.ts
│   │   └── ...
│   ├── utils/               # Funciones utilitarias
│   │   ├── validation.ts
│   │   └── avatar.ts
│   ├── test/                # Tests unitarios
│   │   ├── hooks/
│   │   ├── components/
│   │   ├── features/
│   │   └── utils/
│   ├── main.tsx             # Punto de entrada
│   └── index.css            # Estilos globales
├── .env.example             # Variables de entorno ejemplo
├── package.json             # Dependencias y scripts
├── tsconfig.json            # Configuración TypeScript
├── vite.config.ts           # Configuración Vite
├── tailwind.config.js       # Configuración Tailwind
├── eslint.config.js         # Configuración ESLint
└── README.md                # Este archivo
```

## 📋 Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- **Node.js** >= 18.0.0
- **npm** >= 9.0.0 (o **yarn** / **pnpm** como alternativa)
- **Git** para clonar el repositorio

## 🚀 Instalación

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/JesusJC15/triviando-frontend.git
   cd triviando-frontend
   ```

2. **Instalar dependencias**
   ```bash
   npm install
   ```

3. **Configurar variables de entorno**
   ```bash
   cp .env.example .env
   ```
   
   Edita el archivo `.env` y configura las variables necesarias (ver sección [Configuración](#️-configuración))

4. **Iniciar el servidor de desarrollo**
   ```bash
   npm run dev
   ```

5. **Abrir en el navegador**
   ```
   http://localhost:5173
   ```

## ⚙️ Configuración

### Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```env
# URL del backend (incluye el path /api/v1)
VITE_API_URL=http://localhost:3000/api/v1

# URL del servidor de sockets
VITE_SOCKET_URL=http://localhost:3000
```

### Configuración del Backend

Este frontend requiere un backend que provea:
- API REST para autenticación y gestión de salas
- Servidor WebSocket (Socket.IO) para comunicación en tiempo real
- Endpoints documentados en `src/config/endpoints.ts`

## 📜 Scripts Disponibles

```bash
# Desarrollo
npm run dev              # Inicia el servidor de desarrollo
npm run preview          # Preview de la build de producción

# Build
npm run build            # Genera la build de producción
npm run typecheck        # Verifica tipos TypeScript

# Testing
npm run test             # Ejecuta tests en modo watch
npm run test:ui          # Abre la interfaz de Vitest
npm run test:coverage    # Genera reporte de cobertura

# Linting
npm run lint             # Ejecuta ESLint en el código fuente
```

## 🏗️ Arquitectura

### Patrones y Principios

- **Arquitectura por Capas**: Separación clara entre UI, lógica de negocio y datos
- **Feature-Based Structure**: Organización por funcionalidades (auth, game, chat)
- **Custom Hooks**: Encapsulación de lógica reutilizable
- **Service Layer**: Capa de servicios para comunicación con API
- **Type Safety**: TypeScript en toda la aplicación para prevenir errores

### Flujo de Datos

```
Usuario → Componente → Hook → Service → API/WebSocket
                ↓
           Estado Local
                ↓
        React Query Cache
                ↓
           Renderizado
```

### WebSocket Events

El sistema utiliza Socket.IO para eventos en tiempo real:

**Eventos del Juego:**
- `room:created` - Sala creada exitosamente
- `room:joined` - Jugador se unió a la sala
- `room:left` - Jugador abandonó la sala
- `game:start` - Inicio del juego
- `game:question` - Nueva pregunta
- `game:buzzer` - Buzzer presionado
- `game:answer` - Respuesta enviada
- `game:result` - Resultado de la ronda
- `game:end` - Fin del juego

**Eventos de Chat:**
- `chat:message` - Nuevo mensaje
- `chat:typing` - Usuario escribiendo

### Gestión de Estado

- **TanStack Query**: Estado del servidor y caché
- **React Hooks**: Estado local de componentes
- **Context API**: Estado global cuando es necesario
- **Socket.IO**: Estado en tiempo real compartido

## 🧪 Testing

El proyecto cuenta con una suite completa de tests:

```bash
# Ejecutar todos los tests
npm run test

# Tests con interfaz visual
npm run test:ui

# Cobertura de código
npm run test:coverage
```

### Estructura de Tests

- **22 archivos de test** cubriendo:
  - Hooks personalizados
  - Componentes UI
  - Servicios y API
  - Utilidades y validaciones

### Tecnologías de Testing

- **Vitest**: Framework de testing rápido y compatible con Vite
- **Testing Library**: Testing centrado en el comportamiento del usuario
- **JSDOM**: Simulación del DOM para tests de componentes

## 🚢 Deployment

### Build de Producción

```bash
# Generar build optimizada
npm run build

# Los archivos estarán en la carpeta 'dist/'
```

### Variables de Entorno en Producción

Asegúrate de configurar las variables de entorno en tu plataforma de hosting:

```env
VITE_API_URL=https://tu-backend.com/api/v1
VITE_SOCKET_URL=https://tu-backend.com
```

### Plataformas Recomendadas

- **Vercel** - Deployment automático con Git
- **Netlify** - Hosting con CI/CD integrado
- **Azure Web Apps** - Integración con Azure
- **GitHub Pages** - Hosting estático gratuito

### CI/CD

El proyecto está configurado con GitHub Actions para:
- Linting automático
- Ejecución de tests
- Build de producción
- Deployment automático

## 👥 Equipo

Desarrollado por el equipo **Pokesaurios**:

- **Proyecto**: TrivIAndo - Plataforma de Trivias en Tiempo Real
- **Frontend**: React + TypeScript + Socket.IO
- **Backend**: Node.js + Socket.IO + REST APIs

## 📄 Licencia

Este proyecto es privado y fue desarrollado como proyecto académico/profesional.

---

## 🤝 Contribución

Si deseas contribuir al proyecto:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

### Guías de Contribución

- Sigue las convenciones de código TypeScript
- Escribe tests para nuevas funcionalidades
- Actualiza la documentación cuando sea necesario
- Asegúrate de que los tests pasen antes de hacer PR
- Usa commits descriptivos y claros

---

## 📞 Soporte

Para preguntas, problemas o sugerencias:

- **Issues**: Abre un issue en GitHub
- **Documentación**: Revisa la documentación del código

---

**Hecho con ❤️ por el equipo Pokesaurios**