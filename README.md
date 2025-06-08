# UUSBDriver

Uniform USB System Busified Driver
通用跨平台 USB 驱动框架

## 成果复现
已提供docker镜像，详情参考[复现指南](https://github.com/dbydd/UUSBDriver/blob/main/documents/20250410-Docker%E7%8E%AF%E5%A2%83%E5%A4%8D%E7%8E%B0%E6%95%99%E7%A8%8B.md)

## 解释

- **加粗**说明任务正在进行中

- [ ] 说明任务未开始
- [x] 说明任务已完成

## 项目目标

- [x] 能正常运行
- [x] 非线性编程模型支持(异步&多线程)
- [ ] 跨 OS（Linux 上能运行）
- [ ] **支持基本的 usb 类型(键盘/鼠标/存储/摄像头)**

## 长期 TODO

- [x] 完成基本的框架，并将其迁移至此
- [x] 完善异步部分，将系统修改为基于中断/异步
- [x] 设计一套可扩展的驱动加载系统
- [x] 适配设备树，重写需要的库，形成最小的可运行系统
- [x] 撰写论文

## 短期 TODO

- [x] 完成位于[arceos_experiment](https://github.com/arceos-usb/arceos_experiment/tree/usb-camera-dbydd)下的 USB 系统的原型的编写
  - 目前基于arceos进行开发，[正在剥离并重构](https://github.com/arceos-usb/axusb_host.git)
    - 本次重构的目标是实现驱动本身的异步化，并使其兼容其他usb 栈
    - 如：[cotton](https://github.com/pdh11/cotton.git),[embassy](https://github.com/embassy-rs/embassy/tree/main/embassy-usb)
    - 当前采用embassy作为运行时与异步工具crate，考虑将异步工具更换为更好使的tokio栈上去
    - 话说回来，tokio能在nostd下工作嘛？主要是需要一些async的lock，channel一类的东西。
## 文件结构：

- [文档](./documents/)
- [代码](./code)
- [论文](./article/)
- [技术积累](./documents/blogs)
