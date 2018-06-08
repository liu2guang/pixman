Import('RTT_ROOT')
Import('rtconfig')

from building import *
import os

PIXMAN_VERSION = '0.24.4'
PIXMAN_PATH = 'pixman-' + PIXMAN_VERSION

if not os.path.exists(PIXMAN_PATH):
    print('================ERROR============================')
    print('Please get pixman dist and put them under pixman folder')
    print('=================================================')
    exit(0)

# core source files 
src = Split('''
pixman-access-accessors.c
pixman-access.c
pixman-bits-image.c
pixman-combine32.c
pixman-combine64.c
pixman-conical-gradient.c
pixman-cpu.c
pixman-edge-accessors.c
pixman-edge.c
pixman-fast-path.c
pixman-general.c
pixman-gradient-walker.c
pixman-image.c
pixman-implementation.c
pixman-linear-gradient.c
pixman-matrix.c
pixman-mmx.c
pixman-radial-gradient.c
pixman-region16.c
pixman-region32.c
pixman-solid-fill.c
pixman-timer.c
pixman-trap.c
pixman-utils.c
pixman.c
pixman-noop.c
''')

for item in range(len(src)):
    src[item] = PIXMAN_PATH + '/pixman/' + src[item]

CPPDEFINES  = ['PIXMAN_NO_TLS', 'PACKAGE']
swd = GetCurrentDir()
CPPPATH = [swd + '/' + PIXMAN_PATH + '/pixman']

group = DefineGroup('pixman', src, depend = ['PKG_USING_PIXMAN'], CPPDEFINES = CPPDEFINES, CPPPATH = CPPPATH)

Return('group')
