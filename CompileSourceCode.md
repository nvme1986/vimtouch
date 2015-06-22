# Note: This project has been moved to https://github.com/momodalo/vimtouch #

#summary One-sentence summary of this page.


# How to compile the source code? #

The project is compiling with the Android source tree. Please setup the AOSP repo first. http://source.android.com/source/index.html (Please use gingerbread or above)

## Get the source code ##

Use git to get VimTouch and put it under [aosp](aosp.md)/vendor/
```
git clone https://code.google.com/p/vimtouch/
```

Get the vim source code from http://www.vim.org/sources.php and extract it under vimtouch/jni/vim
```
cd vimtouch/jni
wget ftp://ftp.vim.org/pub/vim/unix/vim-7.3.tar.bz2
tar jxvf vim-7.3.tar.bz2
mv vim73 vim
rm vim/src/auto/config.h
rm vim/src/feature.h
wget http://ftp.gnu.org/pub/gnu/libiconv/libiconv-1.14.tar.gz
mv libiconv-1.14 libiconv
```

Get the libncurses under vimtouch/jni/libncurses
```
git clone https://github.com/CyanogenMod/android_external_libncurses.git libncurses
```

Setup the Android NDK and SDK build environment
```
cd [path to vimtouch]
android update project -p .
```

Compile it!
```
cd [path to vimtouch]
ndk-build
ant debug
```