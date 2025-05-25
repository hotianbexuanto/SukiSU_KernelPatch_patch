# SukiSU's KernelPatch patch

** This is only a simple fork from bmax121's KernelPatch. **

这是一个fork自bmax121的KernelPatch，经过剪裁后用于给SukiSU Ultra提供KPM支持

## 构建

### 本地构建

```bash
# 在Linux环境下
./build.sh

# 在Windows环境下
make.bat
```

### GitHub Actions构建

本项目支持通过GitHub Actions进行自动化构建：

1. **自动构建**：当代码推送到main/master分支或创建Pull Request时，会自动触发构建流程。
2. **手动构建**：在GitHub仓库的Actions页面可以手动触发构建，并选择构建类型（全部、仅Android、仅Linux）。

构建产物包括：
- Android和Linux版本的补丁程序
- 内核模块（kpimg）
- KPM模块（kpms文件夹中的demo模块）

构建完成后，可以在Actions运行记录中下载构建产物。

## Thanks

[APatch](https://github.com/bmax121/APatch)
[KernelPatch](https://github.com/bmax121/KernelPatch)


# KernelPatch

**Patching and hooking the Linux kernel with only stripped Linux kernel image.**

``` shell
 _  __                    _ ____       _       _     
| |/ /___ _ __ _ __   ___| |  _ \ __ _| |_ ___| |__  
| ' // _ \ '__| '_ \ / _ \ | |_) / _` | __/ __| '_ \ 
| . \  __/ |  | | | |  __/ |  __/ (_| | || (__| | | |
|_|\_\___|_|  |_| |_|\___|_|_|   \__,_|\__\___|_| |_|

```

- Obtain all symbol information without source code and symbol information.
- Inject arbitrary code into the kernel. (Static patching the kernel image or Runtime dynamic loading).
- Kernel function inline hook and syscall table hook are provided.
- Additional SU for Android.

If you are using Android, [APatch](https://github.com/bmax121/APatch) would be a better choice.

## Requirement

CONFIG_KALLSYMS=y  

## Supported Versions

Currently only supports arm64 architecture.  

Linux 3.18 - 6.6 (theoretically)  

## Get Involved

## More Information

[Documentation](./doc/)

## Credits

- [vmlinux-to-elf](https://github.com/marin-m/vmlinux-to-elf): Some ideas for parsing kernel symbols.
- [android-inline-hook](https://github.com/bytedance/android-inline-hook): Some code for fixing arm64 inline hook instructions.
- [tlsf](https://github.com/mattconte/tlsf): Memory allocator used for KPM. (Need another to allocate ROX memory.)

## License

KernelPatch is licensed under the **GNU General Public License (GPL) 2.0** (<https://www.gnu.org/licenses/old-licenses/gpl-2.0.html>).
