### What is Rwallpaper?

This is a win10 program that changes the wallpaper randomly at a set time, implemented with Rust.

### Version

0_init_trayicon_examples_crossbeam

### Reference

```bash
https://github.com/Ciantic/trayicon-rs
```

### Cargo.toml Of this version

```toml
[package]
name = "Rwallpaper"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
winapi = { version = "0.3.9", features = ["winuser", "windef", "minwindef", "shellapi", "libloaderapi", "commctrl", "basetsd"] }
crossbeam-channel = "0.5"
trayicon = {git = "https://github.com/Ciantic/trayicon-rs" ,branch = "master",features = ["crossbeam-channel"]}

[profile.release]
opt-level = "z" # 优化级别为z，表示最小化代码大小
lto = true # 启用链接时优化
codegen-units = 1 # 减少代码生成单元的数量，增加优化的可能性
panic = "abort" # 遇到panic时直接终止程序，不使用堆栈展开
strip = true # 去除二进制文件中的符号信息
```
