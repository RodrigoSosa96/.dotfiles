# .dotfiles WSL2

Este Repositorio contiene mis archivos de configuración personales para `WSL2`.

Configuraciones para:
- bash
- zsh
- p10k
- git

Antes de aplicar configuración tener instaladas los programas listados.


## Pasos para restaurar

Instalar Stow y clonar este repositorio preferentemente en la carpeta del usuario

```bash
sudo apt install stow
```

Clonar y descargar submodulos
```bash
git clone --recurse-submodules -j3 https://github.com/RodrigoSosa96/dotfiles.git
```

Generar Symlinks y aplicar configuración:
```bash
# Checkear archivos a cambiar
stow -nvt ~ */

# Aplicar cambios si todos son correctos
stow --adopt -vt ~ */
```




##  Ejemplos

| Comando                | Ejemplos                                                                                  |
|:---------------------- | ----------------------------------------------------------------------------------------- |
| `stow -nvt ~ git`      | `Checkea y muestra los cambios que hará. Agrega la carpeta git al directorio personal ~ ` |
| `stow --adopt -vt ~ */` | ` Agregar todas las carpetas al directorio raiz, * selecciona todos los directorios "hijos".`     |
| `stow -vDt ~ bash`     | `Desenlaza link con archivos bash. No borra el archivo en la raiz, solo remueve el link`                                                                   |
| `stow --adopt -vt ~ work` | `Avanzado. Estando en la carpeta bash agrego los links para work o  testing, en este caso work. En caso de querer cambiar a testing, eliminar el link cono -D y luego ejecutar el comando` |
 

### Argumentos

| Argumento | descripción                                                                                                    |
| --------- | -------------------------------------------------------------------------------------------------------------- |
| `-n --no` | `DO NOT perform any operations that modify the filesystem; merely show what would happen.`                     |
| `-v`      | ` Send verbose output to standard error describing what Stow is doing.`                                        |
| `-S`      | `Default.  Stow the packages that follow this option into the target directory.`                               |
| `-D`      | ` Unstow the packages that follow this option from the target directory rather than installing them.`          |
| `-t DIR`  | `Set the target directory to "DIR" instead of the parent of the stow directory. Always at the end for clarity` |
| `--adopt` | ` This behaviour is specifically intended to alter the contents of your stow directory.`                       |




Referencias: 
- [Sync your .dotfiles with git and GNU #Stow like a pro! - YouTube](https://www.youtube.com/watch?v=CFzEuBGPPPg)
 
