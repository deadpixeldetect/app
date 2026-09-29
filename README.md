# Pendientes — app web con backend para Vercel

- **Frontend:** `public/index.html` (HTML/CSS/JS sin build).
- **Backend:** `api/tasks.js` (función serverless de Node en Vercel).

## Probar en local (opcional)
```bash
npm i -g vercel
vercel dev
```

## Publicar
1. Crea un repositorio en GitHub y sube el proyecto:
   ```bash
   git init
   git add .
   git commit -m "Primera versión"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/mi-app-vercel.git
   git push -u origin main
   ```
2. En [vercel.com/new](https://vercel.com/new) elige **Import Git Repository** y selecciona el repo.
3. Deja **Framework Preset: Other** y no cambies nada más. Pulsa **Deploy**.

Cada `git push` a `main` redesplegará la app automáticamente.

## Importante: persistencia
Las tareas se guardan **en memoria** y se pierden cuando la función se reinicia.
Para datos permanentes, conecta una base de datos desde la pestaña *Storage*
de tu proyecto en Vercel (por ejemplo Upstash Redis o Neon Postgres, disponibles en el Marketplace)
y reemplaza el arreglo `tasks` en `api/tasks.js` por consultas a esa base.
