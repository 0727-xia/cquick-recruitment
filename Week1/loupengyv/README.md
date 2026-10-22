# 第 1 周考核 · loupengyv

- 姓名：<填你的真实姓名>
- 姓名拼音：loupengyv
- 学号 / 联系方式：<选填>
- 完成日期：2026-10-22

## 任务 1：系统安装与 ROS2 环境自检

用 VMware Workstation 17.6.3 装了 Ubuntu 22.04 虚拟机（没走双系统），再用鱼香 ROS 一键脚本装的 ROS2 Humble。

遇到并解决的问题：

1. **虚拟机连不上网**：VMware 的 `VMware NAT Service` 和 `VMnetDHCP` 两个服务是禁用状态，手动启动报 `错误 1067 进程意外终止`，`VMnet8` 只能拿到 169.254.x 的无效地址。最后把网络适配器改成**桥接模式**，虚拟机直接从路由器拿地址，才连上网。
2. **sudo 密码输不进去**：屏幕上一个字符都不回显，连续两次提示「对不起，请重试」。后来发现是输入法停在中文状态，敲出来的字符不对，切回英文（Shift）后正常。
3. **Windows 和 Ubuntu 之间不能复制粘贴**：虚拟机是用 VMware「轻松安装」建的，带了 `autoinst.iso` / `autoinst.flp` 应答文件，得装 `open-vm-tools-desktop` 才能互通。
4. **命令打错**：`wget` 打成 `wegt`、把大写 `O` 写成数字 `0`，报「无效的选项」。改成不带参数的两步写法（`wget <网址>` 再 `. install`）才跑通。

装完后 `printenv ROS_DISTRO` 输出 `humble`，`ros2 --help` 能正常打印帮助信息。

## 任务 2：小乌龟

<这一节请用你自己的话写，不要抄模板。建议覆盖下面几点：>

- `turtlesim_node` 和 `turtle_teleop_key` 分别负责什么？
- 它们是同一个程序的两部分，还是两个各自独立运行的东西？怎么看出来的？
- 我按方向键的时候，按键输入是怎么变成乌龟移动的？中间经过了什么？
- 如果只关掉 `turtle_teleop_key` 那个终端，乌龟窗口还在吗？乌龟还会动吗？为什么？
- 「节点」和「话题」各自是什么，两者是什么关系？（谁发布、谁订阅）

## 任务 3：Git 提交

<写第一次走 Fork + Pull Request 的感想和踩过的坑，例如：>

- 浏览器把 GitHub 页面自动翻译成中文，找不到 Fork 按钮
- clone 到自己想要的目录时报 Permission denied，换目录才成功
- push 时不能用登录密码，要用 Personal Access Token
- 打开 PR 时的操作流程

---

> 截图说明：每张截图都带「姓名拼音 + 实时时间戳」（终端里执行 `date; whoami` 后截图）。
