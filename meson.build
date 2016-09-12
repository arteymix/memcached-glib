project('libmemcached-glib', ['c', 'vala'],
        version: '1.0.0',
        meson_version: '>=0.31.0')

if not meson.is_subproject()
add_global_arguments(['-Wno-deprecated-declarations',
                      '-Wno-unused',
                      '-Wno-discarded-qualifiers',
                      '-Wno-incompatible-pointer-types',
                      '-Wno-pointer-sign'], language: 'c')

add_global_arguments(['--target-glib=2.32',
                      '--fatal-warnings',
                      '--enable-deprecated'], language: 'vala')
endif

glib = dependency('glib-2.0')
gobject = dependency('gobject-2.0')
gio = dependency('gio-2.0')
memcached = dependency('libmemcached')

subdir('src')
subdir('benchmarks')
subdir('tests')
subdir('vapi')
