## ゼロからのOS自作入門 Setup
1. VcXsrvの起動
「Extra Settings」の画面において、「Disable access control」にチェックを入れる。

2. \<cstdint>を使えるようにする
$ source ~/osbook/devenv/buildenv.sh
3. kernelのmake
$ cd ~/workspace/mikanos/kernel
$ git checkout \<tag>
$ make
4. ブートローダのビルド、カーネルの起動
$ cd ~/edk2
$ source `edksetup.sh`
$ build
$ ~/osbook/devenv/run_qemu.sh Build/MikanLoaderX64/DEBUG_CLANG38/X64/Loader.efi ~/workspace/mikanos/kernel/kernel.elf