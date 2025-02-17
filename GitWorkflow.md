# 🚀 Flujo de Trabajo con Git

Este documento describe los pasos para crear un proyecto en Git, trabajar con ramas, hacer merge y gestionar cambios con pull y push.

---

## 🛠 1. Crear un Proyecto en Git
Para empezar desde cero con un nuevo proyecto:
```bash
# Crear una carpeta para el proyecto
mkdir mi-proyecto
cd mi-proyecto

# Inicializar un repositorio Git
git init

# Crear un archivo README.md y agregarlo al control de versiones
echo "# Mi Proyecto" > README.md
git add README.md
git commit -m "Initial commit"
```

Si el repositorio ya existe en GitHub y deseas clonarlo en tu máquina local:
```bash
git clone git@github.com:usuario/mi-proyecto.git
cd mi-proyecto
```

Si Git creó la rama por defecto como `master`, renómbrala a `main`:
```bash
git branch -M main
```

---

## 🔹 2. Conectar con un Repositorio Remoto
Para conectar tu proyecto local con un repositorio en GitHub:
```bash
git remote add origin git@github.com:usuario/mi-proyecto.git
```
Verifica la conexión con:
```bash
git remote -v
```

---

## 🔄 3. Hacer Pull y Push

### 🛠 Subir cambios al repositorio remoto
1. Verifica el estado del repositorio:
   ```bash
   git status
   ```
2. Agrega los cambios al área de preparación:
   ```bash
   git add .
   ```
3. Confirma los cambios:
   ```bash
   git commit -m "Descripción del cambio"
   ```
4. Sube los cambios a GitHub:
   ```bash
   git push origin main
   ```

### 🔄 Traer cambios del remoto al local
Para actualizar tu copia local con los cambios de GitHub:
```bash
git pull origin main
```

---

## 📌 4. Crear una Nueva Rama
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

## ✍ 5. Hacer Cambios en la Nueva Rama
Realiza cambios en tu código y luego:
```bash
git add .
git commit -m "Implementando nueva funcionalidad"
```

---

## 🔄 6. Subir la Nueva Rama a GitHub
Para guardar la rama en el repositorio remoto:
```bash
git push origin nueva-funcionalidad
```

Si deseas colaborar con otros, puedes abrir un **Pull Request (PR)** en GitHub para que la rama se fusione con `main`.

---

## 🔀 7. Unir la Nueva Rama con `main` (Merge)
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

## 🗑 8. Eliminar la Rama Después del Merge
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