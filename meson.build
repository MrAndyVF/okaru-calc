# okaru-calc: la calculadora de OKARU. Se compila contra el núcleo instalado (paquete okaru-core).
project('okaru-calc', 'cpp',
  version: files('VERSION'),
  meson_version: '>=1.1',
  default_options: ['cpp_std=c++23', 'cpp_extensions=false', 'warning_level=0', 'b_ndebug=if-release'],
)

# El núcleo y sus bibliotecas son privados (/usr/lib/okaru): se enlazan con su ruta en el binario.
okaru_core = dependency('okaru-core')
_okaru_libdir = get_option('prefix') / get_option('libdir') / 'okaru'
_deps = [okaru_core, dependency('libqalculate'), dependency('tomlplusplus')]
_inc = include_directories('src')
_args = ['-Wall', '-Wextra', '-Wno-missing-field-initializers', '-Wpedantic', '-Wconversion', '-Wshadow']

_engine = files('src/apps/calculator/calc_engine.cpp', 'src/apps/calculator/calc_state.cpp')

executable('okaru-calc',
  sources: files('src/apps/calculator/calculator_window.cpp', 'src/apps/calculator/main.cpp') + _engine,
  include_directories: _inc,
  dependencies: _deps,
  cpp_args: _args,
  install_rpath: _okaru_libdir,
  install: true,
)

# Sus textos, que el núcleo busca en /usr/share/okaru/apps/calculator/translations.
install_subdir('apps/calculator/translations', install_dir: get_option('datadir') / 'okaru' / 'apps' / 'calculator')
install_data('assets/dev.okaru.Calculator.desktop', install_dir: get_option('datadir') / 'applications')

if get_option('tests').allowed()
  test('okaru_calc_engine', executable('okaru_calc_engine_test',
    sources: files('tests/okaru_calc_engine_test.cpp') + _engine,
    include_directories: _inc,
    dependencies: _deps,
    build_rpath: _okaru_libdir,
    override_options: ['b_ndebug=false'],
  ))
endif
