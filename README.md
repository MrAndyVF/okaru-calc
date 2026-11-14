# okaru-calc

La calculadora de [OKARU](https://github.com/MrAndyVF/okaru) (郁). / The calculator of OKARU.

Se instala desde el repositorio pacman `[okaru]` (`pacman -S okaru-calc`) y se compila contra el núcleo compartido
de OKARU (paquete `okaru-core`).

## Compilar / Build

```sh
meson setup build && meson compile -C build
# Probar con sus traducciones de este repo:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-calc
```

Licencia MIT.
