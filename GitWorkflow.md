# 🚀 Flujo de Trabajo con Ramas en Git

Este documento describe los pasos para crear, trabajar, fusionar y eliminar ramas en Git.

---

## 📌 1. Crear una Nueva Rama
Cuando quieras desarrollar una nueva funcionalidad sin afectar `main`, crea una nueva rama:
```bash
git checkout -b nueva-funcionalidad
```
Esto crea y cambia automáticamente a la nueva rama.

Para verificar en qué rama estás:
```bash
git branch
```

---

## ✍ 2. Hacer Cambios en la Nueva Rama
Realiza cambios en tu código y luego:
```bash
git add .
git commit -m "Implementando nueva funcionalidad"
```

---

## 🔄 3. Subir la Nueva Rama a GitHub
Para guardar la rama en el repositorio remoto:
```bash
git push origin nueva-funcionalidad
```

Si deseas colaborar con otros, puedes abrir un **Pull Request (PR)** en GitHub para que la rama se fusione con `main`.

---

## 🔀 4. Unir la Nueva Rama con `main` (Merge)
Después de finalizar el desarrollo:

1. Cambia a la rama `main`:
   ```bash
   git checkout main
   ```

2. Asegúrate de que `main` está actualizado:
   ```bash
   git pull origin main
   ```

3. Fusiona la rama `nueva-funcionalidad` en `main`:
   ```bash
   git merge nueva-funcionalidad
   ```

4. Sube los cambios a GitHub:
   ```bash
   git push origin main
   ```

---

## 🗑 5. Eliminar la Rama Después del Merge
Una vez fusionada, elimina la rama:

- **Eliminar la rama en local:**
  ```bash
  git branch -d nueva-funcionalidad
  ```

  Si Git no permite eliminarla porque no está fusionada, usa `-D`:
  ```bash
  git branch -D nueva-funcionalidad
  ```

- **Eliminar la rama en GitHub:**
  ```bash
  git push origin --delete nueva-funcionalidad
  ```

---

## 📌 Resumen del Flujo Completo
```bash
# Crear y cambiar a una nueva rama
git checkout -b nueva-funcionalidad

# Hacer cambios y confirmarlos
git add .
git commit -m "Implementando nueva funcionalidad"

# Subir la rama a GitHub
git push origin nueva-funcionalidad

# Cambiar a la rama main
git checkout main

# Traer la última versión de main
git pull origin main

# Fusionar la rama con main
git merge nueva-funcionalidad

# Subir los cambios a GitHub
git push origin main

# Eliminar la rama en local
git branch -d nueva-funcionalidad

# Eliminar la rama en GitHub
git push origin --delete nueva-funcionalidad
```

---

## 🎯 ¿Cuándo Usar Ramas?
✔ Para desarrollar **nuevas funcionalidades** sin afectar `main`.
✔ Para trabajar en **correcciones de errores**.
✔ Para realizar **pruebas de código** sin afectar la versión estable.
✔ Para permitir que **varios desarrolladores trabajen en paralelo**.

