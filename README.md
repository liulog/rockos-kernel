Personal Usage Notes
===============

If you want to run qwen_sample or other AI demos on eswin eic7700x soc.

Please use branch `rockos-v6.6.77`. I have run it locally on Sifive Hifive-premier-p550.

Example commands are below:
```bash
export ARCH=riscv
export CROSS_COMPILE=riscv64-unknown-linux-gnu-
make eic7700_defconfig # or win2030_defconfig
make -j
```

> `CONFIG_DEVFREQ_GOV_USERSPACE` is not set in the original eic7700_defconfig.
>
> I have added it, so you can use current eic7700_defconfig directly.
>

In board, you need:
```bash
# insert related modules
insmod eic7700_dsp.ko
insmod eic7700_npu.ko
```

Official README
===============

Linux kernel
------------

There are several guides for kernel developers and users. These guides can
be rendered in a number of formats, like HTML and PDF. Please read
Documentation/admin-guide/README.rst first.

In order to build the documentation, use ``make htmldocs`` or
``make pdfdocs``.  The formatted documentation can also be read online at:

    https://www.kernel.org/doc/html/latest/

There are various text files in the Documentation/ subdirectory,
several of them using the Restructured Text markup notation.

Please read the Documentation/process/changes.rst file, as it contains the
requirements for building and running the kernel, and information about
the problems which may result by upgrading your kernel.
