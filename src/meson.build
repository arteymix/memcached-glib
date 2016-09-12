memcached_glib_sources = [
    'libmemcached-glib.vala',
    'libmemcached-glib-context.vala',
    'libmemcached-glib-context-source.vala',
    'libmemcached-glib-error.vala']
memcached_glib_lib = library('libmemcached-glib', memcached_glib_sources,
                             vala_args: '--vapidir=' + meson.current_source_dir() + '/../vapi',
                             dependencies: [glib, gobject, gio, memcached],
                             install: true)

memcached_glib = declare_dependency(dependencies: memcached,
                                    link_with: memcached_glib_lib,
                                    include_directories: include_directories('.'))

pkg_config = import('pkgconfig')
pkg_config.generate(name: 'libmemcached-glib',
                    description: 'GLib wrapper around libMemcached',
                    requires: 'glib-2.0 gobject-2.0 gio-2.0 libmemcached',
                    libraries: memcached_glib_lib)

install_data(meson.current_build_dir() + '/libmemcached-glib.vapi', install_dir: 'share/vala/vapi')
install_data('libmemcached-glib.deps', install_dir: 'share/vala/vapi')
