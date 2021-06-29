Hello Cargo

构建系统和包管理工具

cargo --version

cargo new hello_cargo

Tom`s Obvious, Minimal Language
[package] 配置包
name = "hello_cargo" 项目名
version = "0.1.0" 项目版本
authors = ["mqiu <hulen20@gmail.com>"] 项目作者
edition = "2018" Rust 版本
[dependencies] 列出项目的依赖项

代码包称作 crate

顶层目录可以放置：README、许可信息、配置文件和其他与程序无关的文件
如果项目没有使用cargo 可以吧项目转化为使用cargo:
- 把源代码文件移动到src下
- 创建Cargo.toml 并填写相应的配置

cargo build
- 创建可执行文件  
- 运行可执行文件 ./hello_cargo
- 第一次运行 cargo build 会在顶层目录申城 cargo.lock 文件
  - 该文件负责追踪项目依赖的精确版本
  - 不需要手动修改该文件

cargo run
构建并且运行 cargo 项目
  - 如果之前编译成功过，会直接运行二进制文件

mqiu@SHMACL010 hello_cargo % cargo run
   Compiling hello_cargo v0.1.0 (/Users/mqiu/Documents/workspace/nodejs_workspace/rust_standard/1.4/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.39s
     Running `target/debug/hello_cargo`
Hello, world!
mqiu@SHMACL010 hello_cargo % cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/hello_cargo`
Hello, world!

cargo check
检查代码，确保通过编译，不会产生任何可执行文件
cargo check 要比 cargo build 快很多
  - 编写代码的时候可以连续反复的使用 cargo check 检查代码，提高效率

发布构建
cargo build --release
 - 编译时会进行优化
   - 代码会运行的更快，但是编译时间更长
 - 会在 target/release 而不是 target/debug 生成可执行文件
 - 两种配置
   - 开发
   - 发布

尽量使用Cargo