def merge_dicts(x, y):
  z = x.copy()
  z.update(y)
  return z

cxx_library(
  name = 'sodium',
  header_namespace = '',
  exported_headers = merge_dicts(subdir_glob([
    ('src/libsodium/include', '**/*.h'),
  ]), {
    'sodium/version.h': 'builds/msvc/version.h', 
  }), 
  headers = merge_dicts(subdir_glob([
    ('src/libsodium/include/sodium', '*.h'),
    ('src/libsodium/include/sodium', 'private/*.h'),
    ('', 'src/libsodium/**/*.h'),
  ]), {
    'version.h': 'builds/msvc/version.h', 
  }), 
  srcs = glob([
    'src/libsodium/**/*.c',
  ]),
  visibility = [
    'PUBLIC',
  ],
)
