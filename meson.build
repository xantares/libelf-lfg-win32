# Copyright © 2020 Lag Free Games LLC

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

project(
  'libelf-lfg-win32',
  ['c'],
  version : '1.0.0',
  license : 'BSD',
  meson_version : '>= 0.46',
  default_options : ['buildtype=debugoptimized', 'c_std=gnu99'],
)

pkg = import('pkgconfig')

cc = meson.get_compiler('c')

libelf = static_library(
  'elf',
  [files(
     'contrib/elftoolchain/libelf/elf.c',
     'contrib/elftoolchain/libelf/elf_data.c',
     'contrib/elftoolchain/libelf/elf_end.c',
     'contrib/elftoolchain/libelf/elf_errmsg.c',
     'contrib/elftoolchain/libelf/elf_errno.c',
     'contrib/elftoolchain/libelf/elf_flag.c',
     'contrib/elftoolchain/libelf/elf_memory.c',
     'contrib/elftoolchain/libelf/elf_scn.c',
     'contrib/elftoolchain/libelf/elf_shnum.c',
     'contrib/elftoolchain/libelf/elf_shstrndx.c',
     'contrib/elftoolchain/libelf/elf_strptr.c',
     'contrib/elftoolchain/libelf/elf_version.c',
     'contrib/elftoolchain/libelf/gelf_ehdr.c',
     'contrib/elftoolchain/libelf/gelf_fsize.c',
     'contrib/elftoolchain/libelf/gelf_shdr.c',
     'contrib/elftoolchain/libelf/libelf_allocate.c',
     'contrib/elftoolchain/libelf/libelf_ar_util.c',
     'contrib/elftoolchain/libelf/libelf_convert.c',
     'contrib/elftoolchain/libelf/libelf_data.c',
     'contrib/elftoolchain/libelf/libelf_ehdr.c',
     'contrib/elftoolchain/libelf/libelf_elfmachine.c',
     'contrib/elftoolchain/libelf/libelf_extended.c',
     'contrib/elftoolchain/libelf/libelf_fsize.c',
     'contrib/elftoolchain/libelf/libelf_memory.c',
     'contrib/elftoolchain/libelf/libelf_msize.c',
     'contrib/elftoolchain/libelf/libelf_shdr.c',
   ),
  ],
  include_directories : include_directories('contrib/binutils/include/aout', 'contrib/elftoolchain/common', 'contrib/elftoolchain/libelf', 'sys'),
  install : true,
)

libelf_dep = declare_dependency(
  link_with : libelf,
  include_directories : include_directories('contrib/elftoolchain/common', 'contrib/elftoolchain/libelf', 'sys'),
)

pkg.generate(
  libelf,
  name : 'libelf',
  subdirs : ['libelf'],
  version : meson.project_version(),
  description : 'libelf description',
)
