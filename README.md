# okaru-calc

**English** · [Español](#español)

The calculator of [OKARU](https://github.com/MrAndyVF/okaru) (郁): basic, advanced, financial and programming modes plus unit
and currency conversion (powered by libqalculate), with the shell's look and theme.

## Install

It ships in OKARU's pacman repository `[okaru]` (set up by OKARU's installer):

```sh
sudo pacman -S okaru-calc
```

## Build

It builds against OKARU's shared core, provided by the `okaru-core` package:

```sh
meson setup build && meson compile -C build
meson test -C build
# Run it with the translations from this repository:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-calc
```

Translations live in `apps/calculator/translations/` (English and Spanish).

## License

MIT.

---

## Español

La calculadora de [OKARU](https://github.com/MrAndyVF/okaru) (郁): modos básico, avanzado, financiero y de programador, y
conversión de unidades y divisas (con libqalculate), con el aspecto y el tema de la shell.

### Instalar

Viene en el repositorio pacman de OKARU, `[okaru]` (lo configura el instalador de OKARU):

```sh
sudo pacman -S okaru-calc
```

### Compilar

Se compila contra el núcleo compartido de OKARU, que trae el paquete `okaru-core`:

```sh
meson setup build && meson compile -C build
meson test -C build
# Ejecutarla con las traducciones de este repositorio:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-calc
```

Las traducciones están en `apps/calculator/translations/` (inglés y español).

### Licencia

MIT.
