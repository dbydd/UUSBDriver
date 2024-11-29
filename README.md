# UUSBDriver

Uniform USB System Busified Driver
通用跨平台 USB 驱动框架

## 解释

- **加粗**说明任务正在进行中

- [ ] 说明任务未开始
- [x] 说明任务已完成

## 项目目标

- [x] 能正常运行
- [ ] 非线性编程模型支持(异步&多线程)
- [ ] 跨 OS（Linux 上能运行）
- [ ] 支持基本的 usb 类型(键盘/鼠标/存储/摄像头)

## 长期 TODO

- [x] 完成基本的框架，并将其迁移至此
- [ ] 完善异步部分，将系统修改为基于中断/异步
- [x] 设计一套可扩展的驱动加载系统
- [x] 适配设备树，重写需要的库，形成最小的可运行系统
- [ ] 撰写论文

## 短期 TODO

- [x] 完成位于[arceos_experiment](https://github.com/arceos-usb/arceos_experiment/tree/usb-camera-dbydd)下的 USB 系统的原型的编写
  - 目前基于arceos进行开发，待功能成熟后会将代码剥离出来
## 文件结构：

- [文档](./documents/)
- [代码](./code)
- [论文](./article/)
- [技术积累](./documents/blogs)
