## a-Shell-commands

shell commands, pre-compiled to webAssembly, ready to use in a-Shell

## Purpose

[a-Shell](https://github.com/holzschu/a-shell) is a terminal for iOS. Several commands are provided, pre-compiled to iOS format. With the latest release (1.4.x), you can also execute commands compiled to webAssemly (wasm). If the command creates, writes or reads local files, it is best to use the specific [WASI-sdk](https://github.com/holzschu/wasi-sdk) to compile them.

Once compiled to webAssembly, binaries can be shared with other users of a-Shell. Click on the command you want, download it to your iPad or iPhone, move it to `~/Documents/bin/` and use it (a-Shell will add ".wasm" at the end and call the webAssembly JIT compiler on commands that are in the PATH).

file, tree, ctags and readtags are also part of the a-Shell AppStore release.

The idea is that we can share pre-compiled commands. Submit yours through pull-requests.

## List of commands, with their source code:

-   [ctags](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/ctags.wasm)/[readtags](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/readtags.wasm): [https://github.com/universal-ctags/ctags/](https://github.com/universal-ctags/ctags/)
-   f2c: [http://www.netlib.org/f2c/](http://www.netlib.org/f2c/)
    -   [f2c](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/f2c)
    -   [libf2c.a](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/libf2c.a)
    -   Compile Fortran code to C with `f2c file.f`, then compile the C code with `clang file.c -L ~/Library/lib -lf2c -D_WASI_EMULATED_SIGNAL -lwasi_emulated_signal`.
    -   `-L` is followed by the directory where you actually installed `libf2c.a`
-   [file](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/file.wasm): [https://github.com/file/file/](https://github.com/file/file/)
-   ffmpeg: [https://www.ffmpeg.org](https://www.ffmpeg.org/)
    -   [ffmpeg](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/ffmpeg.wasm) (all codecs enabled, external libs: libx264, zlib: 18 MB)
    -   [ffprobe](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/ffprobe.wasm) (all codecs enabled, external libs: libx264, zlib: 18 MB)
    -   [ffmpeg\_lite](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/ffmpeg_lite.wasm) (decoders: H263, H264, Mpeg4, MKV, AAC, AC3 only, 3.2 MB)
-   [tree](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/tree.wasm): [http://mama.indstate.edu/users/ice/tree/](http://mama.indstate.edu/users/ice/tree/)
-   [xz](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/xz.wasm), [xzdec](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/xzdec.wasm), [lzmadec](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/lzmadec.wasm), [lzmainfo](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/lzmainfo.wasm): [https://git.tukaani.org/xz](https://git.tukaani.org/xz)
-   [zip](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/zip.wasm), [unzip](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/unzip.wasm), [zipcloak](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/zipcloak.wasm), [zipnote](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/zipnote.wasm), [zipsplit](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/zipsplit.wasm), [funzip](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/funzip.wasm), [unzipsfx](https://github.com/holzschu/a-Shell-commands/releases/download/0.1/unzipsfx.wasm): [http://infozip.sourceforge.net/UnZip.html](http://infozip.sourceforge.net/UnZip.html)