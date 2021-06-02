# br2-external-f3rp70

This is a br2-external for [f3rp70](https://www.yokogawa.com/solutions/products-platforms/control-system/ert3-embedded-controller/ert3-products/ert3-products-cpu/).

# How to make

```
$ cd /path/to/buildroot-dir
$ make BR2_EXTERNAL=/path/to/this-repo f3rp70_defconfig
$ make BR2_EXTERNAL=/path/to/this-repo LOADADDR=0x02000000
```

# Known Issues

## Cannot apply patches-4.14.164-rt73.tar.xz

Because the patches have renames. Currently, patches with renames are refused, as they reqire patch 2.7 or newer.

This will be resolved once [this commit](https://git.buildroot.org/buildroot/commit/?h=next&id=f46e13f05fa04a180a416876cf1dd4252dd841ad) is released.

### Work around

Comment out [this line](https://github.com/buildroot/buildroot/blob/6668381363364c89d43689322cc5ce4249c8fd9d/support/scripts/apply-patches.sh#L119).

