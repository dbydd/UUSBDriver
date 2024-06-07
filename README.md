# UUSBDriver
Uniform USB System Busified Driver
通用跨平台USB驱动框架


## 项目目标
* [ ] 能正常运行
* [ ] 非线性编程模型支持(异步&多线程)
* [ ] 跨OS（Linux上能运行）
* [ ] 支持基本的usb类型(键盘/鼠标/存储/摄像头)

## 长期TODO
* [ ] 完成基本的框架，并将其迁移至此
* [ ] 完善异步部分，将系统修改为基于中断/异步
* [ ] 设计一套可扩展的驱动加载系统
* [ ] 适配设备树，重写需要的库，形成最小的可运行系统
* [ ] 撰写论文

## 短期TODO
* [ ] 完成位于[arceos_experiment](https://github.com/arceos-usb/arceos_experiment/tree/phytium_pi_dev)下的USB系统的原型的编写
* [ ] [思索：如何让设备驱动能够自动加载，换句话来说，是否有设计一套二进制接口的必要？](./documents/ideas/idea_driver_load_system_three_step_bus.md)


## 文件结构：
* [文档](./documents/)
* [代码](./code/)
* [论文](./article/)
