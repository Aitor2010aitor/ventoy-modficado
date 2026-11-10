# Ventoy Modificado (TreeView / Navegación por Carpetas por Defecto)

> **Autor del proyecto / Modificación:** [Aitor2010aitor](https://github.com/Aitor2010aitor)  
> **Proyecto base:** Fork independiente basado en el código fuente de [Ventoy](https://github.com/ventoy/Ventoy).

[Español](#español) | [English](#english) | [Français](#français) | [Deutsch](#deutsch)

---

## Español

### ¿Qué es este proyecto y por qué está modificado?
En la versión oficial de Ventoy, al meter decenas de sistemas operativos e ISOs en el USB, todas aparecen juntas en una lista plana interminable y desordenada. Además, para navegar por carpetas hay que pulsar combinaciones de teclas cada vez que arrancas.


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f818d505-d541-4d84-893e-0e433af5c7d3" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c9f19d20-f615-44bc-92f7-f445208d52fa" />


**Esta versión modificada resuelve eso por completo:**
1. **Modo Árbol / Carpetas Activo por Defecto (`TreeView`)**:
   - Al encender el ordenador con el USB, **arranca directamente en modo carpetas**.
   - No necesitas pulsar ninguna tecla extra: navega con las flechas, pulsa **Enter** para entrar a una carpeta y **ESC** para volver atrás.
2. **Estructura Automática al Instalar**:
   - Al usar el instalador `Ventoy2Disk.exe`, se crean automáticamente en el USB las siguientes carpetas organizadas:
     - `📁 Windows/` -> Para tus ISOs de Windows 10, 11, etc.
     - `📁 Linux/` -> Para Ubuntu, Debian, Arch, Kali, etc.
     - `📁 Herramientas/` -> Para utilidades de rescate, antivirus, Clonezilla, etc.
     - `📁 ISOs/` -> Para cualquier otra imagen general.
3. **Configuración Automática (`ventoy.json`)**:
   - Crea en el USB el archivo `ventoy/ventoy.json` preconfigurado con las directivas `VTOY_DEFAULT_MENU_MODE` y `VTOY_TREE_VIEW_MENU_STYLE`.
4. **Modificaciones realizadas en el código fuente**:
   - `GRUB2/MOD_SRC/.../ventoy_cmd.c`: Modificada la variable interna `g_default_menu_mode = 1` y la lógica de arranque de GRUB para forzar TreeView.
   - `Ventoy2Disk/PhyDrive.c`: Integrada la función `CreateDefaultFolderTreeAndConfig()` para crear el árbol de carpetas y el JSON de forma nativa nada más formatear.

---

### 📥 Descargas Listas para Usar
Descarga los ejecutables ya compilados en la sección de **[Releases](https://github.com/Aitor2010aitor/ventoy-modficado/releases)**:
- 🪟 **Windows**: Descarga `Ventoy2Disk.exe` o el paquete completo `ventoy-1.1.18-windows.zip`.
- 🐧 **Linux / Mac**: Descarga `ventoy-1.1.18-linux.tar.gz`.

---

## English

### What is this modified version?
In stock Ventoy, all ISOs appear cluttered in a single long flat list by default. Navigating by directories requires manually pressing hotkeys every time you boot.

**This modified release improves the workflow completely:**
1. **Default TreeView / Folder Navigation**:
   - Boots directly into folder view automatically.
   - Press **Enter** to open a folder and **ESC** to go back.
2. **Auto-Generated Directory Structure**:
   - Installing via `Ventoy2Disk.exe` automatically creates standard directories:
     - `📁 Windows/`
     - `📁 Linux/`
     - `📁 Herramientas/` (Rescue tools)
     - `📁 ISOs/`
3. **Auto-Generated `ventoy.json`**:
   - Generates configuration directives with TreeView preset.
4. **Source Code Modifications**:
   - Core bootloader modified in `ventoy_cmd.c` to enforce `g_default_menu_mode = 1`.
   - Windows installer modified in `PhyDrive.c` with `CreateDefaultFolderTreeAndConfig()` logic.

---

## Français

### Qu'est-ce que cette version modifiée ?
Dans la version officielle de Ventoy, tous les fichiers ISO s'affichent pêle-mêle dans une liste plate. 

**Cette version modifiée par Aitor2010aitor change tout :**
- Démarrage automatique en **mode arborescence (dossiers)** dès le boot.
- Touche **Entrée** pour ouvrir un dossier, **Échap** pour revenir.
- Création automatique des dossiers (`Windows/`, `Linux/`, `Herramientas/`, `ISOs/`) et du fichier `ventoy.json`.

---

## Deutsch

### Was ist diese modifizierte Version?
Standardmäßig zeigt Ventoy alle ISO-Dateien in einer langen, unübersichtlichen Liste an.

**Diese modifizierte Version von Aitor2010aitor bietet:**
- Startet automatisch im **Ordner-Modus (TreeView)**.
- Ordner öffnen mit **Enter**, zurückkehren mit **ESC**.
- Automatische Erstellung der Ordner (`Windows/`, `Linux/`, `Herramientas/`, `ISOs/`) und der Konfigurationsdatei `ventoy.json`.

---

### 📄 Licencia
Este proyecto es software libre bajo licencia **GPL v3.0**.
