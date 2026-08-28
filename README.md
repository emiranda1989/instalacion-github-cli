<p align="center">
  <img src="inacap.png" alt="INACAP Logo" width="220" />
</p>

# Bitácora de Instalación y Configuración de GitHub CLI

Este repositorio documenta el procedimiento completo realizado para la instalación, verificación, autenticación y configuración de **GitHub CLI (`gh`)** en un entorno Windows con PowerShell.

---

## 📋 Resumen del Trabajo Realizado

1. **Verificación de Entorno y Gestores de Paquetes**
   - Comprobación de la disponibilidad de Windows Package Manager (`winget`).
   - Verificación de la versión del sistema y estado previo de herramientas CLI.

2. **Instalación de GitHub CLI**
   - Instalación automatizada de la herramienta oficial mediante `winget`:
     ```powershell
     winget install --id GitHub.cli -e --source winget
     ```
   - Instalación exitosa del paquete `GitHub.cli` en su versión **2.98.0** (x64).

3. **Verificación de la Instalación**
   - Actualización de variables de entorno (`PATH`).
   - Validación del binario mediante:
     ```powershell
     gh --version
     ```
   - Salida confirmada: `gh version 2.98.0`.

4. **Autenticación en GitHub**
   - Inicio del flujo de autenticación seguro OAuth para dispositivos:
     ```powershell
     gh auth login --hostname github.com --git-protocol https --web
     ```
   - Generación del código de un solo uso para validación en navegador (`https://github.com/login/device`).
   - Vinculación exitosa con la cuenta de GitHub: **`emiranda1989`**.

5. **Configuración de Git y Credenciales**
   - Configuración del protocolo Git como `HTTPS`.
   - Vinculación de `gh` como gestor de credenciales de Git (`gh auth setup-git`).
   - Configuración de identidad de autor en Git (`user.name` y `user.email`).

6. **Creación y Publicación del Repositorio**
   - Inicialización del repositorio Git local (`git init`).
   - Creación de la documentación completa (`README.md`).
   - Publicación remota en GitHub mediante GitHub CLI (`gh repo create`).

---

## 🛠️ Comandos Útiles de GitHub CLI

- **Ver estado de autenticación:**
  ```powershell
  gh auth status
  ```
- **Listar repositorios:**
  ```powershell
  gh repo list
  ```
- **Clonar un repositorio:**
  ```powershell
  gh repo clone <usuario/repositorio>
  ```
- **Crear un nuevo repositorio remoto:**
  ```powershell
  gh repo create <nombre-del-repo> --public --source=. --push
  ```

---
*Repositorio creado y documentado automáticamente con Antigravity Assistant.*
