## Nanopi-NEO-Core 环境搭建
#### 下载
```bash
# 下载 Linux 源码并切换分支
git clone https://github.com/zengwangfa/linux.git -b sunxi-4.14.y --depth 1
```

#### 编译
```bash
make zImage dtbs ARCH=arm CROSS_COMPILE=arm-linux-
```

#### 烧写
```bash
# 通过scp命令通过网络更新 zImage 与 dtb
sudo scp arch/arm/boot/zImage root@192.168.31.213:/boot/
sudo scp arch/arm/boot/dts/sun8i-h3-nanopi-neo-core.dtb root@192.168.31.213:/boot/
```

## 提交规范
- 使用 `Markdown emoji` 以及 关键词 作为 `commit message` 开头，表明本次提交主要作用：
  - `🐛 Fix:` 修复
  - `🔨 ENH:` 完善
  - `📝 Docs:` 文档
  - `✨ Feature:` 新特性
  - `🎉 Release:` 发布


```bash
# 提交示例
git add .
git commit -s -m "🔨 ENH: add focus camera control"
git commit --amend
git push -u origin master
```
