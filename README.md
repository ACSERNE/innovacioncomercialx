# 🚀 InnovacionComercialX

![Deploy Status](https://github.com/tu-usuario/tu-repo/actions/workflows/deploy.yml/badge.svg)

## 📦 Descripción
InnovacionComercialX es un cockpit técnico federado que integra frontend React + Vite y backend Node.js, desplegado automáticamente con GitHub Actions y PM2.

## ⚙️ CI/CD
Cada push a `main` dispara el workflow `.github/workflows/deploy.yml`:
- Compila el frontend en GitHub con heap extendido.
- Copia el `dist/` al servidor vía SSH.
- Ejecuta `deploy.sh` con rollback automático.
- Copia el backend y reinicia PM2 en el servidor.

## 🔑 Configuración de Secrets
En tu repo, ve a **Settings → Secrets → Actions** y agrega:
- `SERVER_HOST` → IP o dominio del servidor.
- `SERVER_USER` → usuario SSH (ej. `root`).
- `SERVER_SSH_KEY` → clave privada para conectar.

## 🚦 Despliegue manual
```bash
./deploy.sh

