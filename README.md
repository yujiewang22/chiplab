chiplab用于对LoongArch32r处理器核进行敏捷开发测试，该项目目前已在chiplab/IP/myCPU目录内提前移植了open-la500的verilog内核源码。


## 一、环境搭建

### 1. GCC交叉编译器
(https://gitee.com/loongson-edu/la32r-toolchains/releases)

1. 下载`loongarch32r-linux-gnusf-${TOOLCHAINS_DATE}.tar.gz`并解压;
2. 将解压后目录放置在`chiplab/toolchains/loongarch32r-linux-gnusf-${TOOLCHAINS_DATE}`;
3. 将`loongarch32r-linux-gnusf-${TOOLCHAINS_DATE}/bin`目录添加到path中。

### 2. picolibc库（Makefile默认）
(https://gitee.com/ffshff/la32r-picolibc/releases/tag/v1.1)

1. 下载`picolibc.tar.gz`并解压；
2. 将解压后目录放置在`chiplab/toolchains/picolib`。

### 3. NEMU
(https://gitee.com/wwt_panache/la32r-nemu/releases)

1. 下载`la32r-nemu-interpreter-so`;
2. 将下载后文件放置在`chiplab/toolchains/nemu`。

### 4. QEMU
(https://gitee.com/loongson-edu/la32r-QEMU/releases/tag/v0.0.2)

1. 下载`la32r-QEMU-x86_64-*-22.04.tar`并解压；
2. 将`la32r-QEMU-x86_64-ubuntu-22.04`目录添加到path中。

## 二、Verilator仿真

### 1. 测试hello_world
```
export CHIPLAB_HOME=/home/wyj/project/chiplab
cd $CHIPLAB_HOME/sims/verilator/run_prog
./configure.sh --run hello_world
make clean
make
```

### 2. 测试func_labx
```
export CHIPLAB_HOME=/home/wyj/project/chiplab
cd $CHIPLAB_HOME/sims/verilator/run_prog 
./configure.sh --run func/func_lab3
make clean
make
```

### 3. 测试dhrystone
```
export CHIPLAB_HOME=/home/wyj/project/chiplab
cd $CHIPLAB_HOME/sims/verilator/run_prog 
./configure.sh --run dhrystone
make clean
make
```