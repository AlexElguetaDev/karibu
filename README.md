# Karibu

Proyecto Astro que integra Storyblok para obtener contenido dinámico.

## 🚀 Configuración

### Instalación

```bash
pnpm install
```

### Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```env
STORYBLOK_TOKEN=tu_token_de_storyblok
DEFAULT_NAME=Karibu
```

- `STORYBLOK_TOKEN`: Tu token de acceso de Storyblok (obligatorio)
- `DEFAULT_NAME`: Nombre por defecto que se mostrará si no se puede obtener el contenido de Storyblok (opcional)

## 📖 Uso

### Desarrollo

Inicia el servidor de desarrollo:

```bash
pnpm dev
```

El proyecto estará disponible en `http://localhost:4321`

### Build

Genera la versión de producción:

```bash
pnpm build
```

### Preview

Previsualiza la build de producción:

```bash
pnpm preview
```

## 🏗️ Estructura del Proyecto

```
/
├── public/
│   └── favicon.svg
├── src
│   ├── layouts
│   │   └── Layout.astro
│   └── pages
│       └── index.astro
└── package.json
```

## 📝 Cómo Funciona

El proyecto obtiene el nombre desde Storyblok:

1. Intenta obtener el contenido de la story `karibu` desde Storyblok
2. Extrae el campo `myname` del primer elemento del body
3. Si la obtención falla o no hay contenido, usa el valor por defecto (`DEFAULT_NAME` o "Karibu")

### Configuración en Storyblok

Asegúrate de tener:
- Una story llamada `karibu`
- Un campo `myname` dentro del primer elemento del array `body` en el contenido

### Actualización Automática

El proyecto está configurado como **server-side rendering**, lo que significa que:
- Cada vez que alguien visita la página, obtiene el contenido más reciente de Storyblok
- Los cambios en Storyblok se reflejan inmediatamente sin necesidad de hacer deploy
- Solo necesitas publicar el contenido en Storyblok y estará disponible al instante

## 🛠️ Comandos Disponibles

| Comando           | Acción                                    |
| :---------------- | :---------------------------------------- |
| `pnpm install`    | Instala las dependencias                  |
| `pnpm dev`        | Inicia el servidor de desarrollo          |
| `pnpm build`      | Genera la build de producción             |
| `pnpm preview`    | Previsualiza la build localmente          |
| `pnpm astro ...`  | Ejecuta comandos CLI de Astro             |

## 📚 Dependencias

- **astro**: Framework base
- **storyblok-js-client**: Cliente para interactuar con la API de Storyblok

## 🔗 Enlaces Útiles

- [Documentación de Astro](https://docs.astro.build)
- [Documentación de Storyblok](https://www.storyblok.com/docs)
