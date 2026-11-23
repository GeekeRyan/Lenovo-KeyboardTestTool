# Lenovo-KeyboardTestTool


联想键盘测试工具




一、运行环境
- Windows 10 / Windows 11（32 位、64 位）
- Windows 10 PE（x86 与 x64 PE 均可）


二、使用说明
操作
效果
直接按键
键帽变绿（已触发）、进度与击键数 +1
按住某键 ≥ 0.6 秒
该键红/橙交替闪烁（模拟卡键告警），松开立即停止
鼠标点击虚拟键
同一次按键，键帽瞬时高亮并计为已触发（悬停有淡蓝描边）
底部黄色按钮
重置测试
标题栏 — / ✕
最小化 / 退出（也可 Alt+F4）
拖动标题区域
移动窗口（最小化后可从任务栏恢复）
F11
全屏 / 还原（全屏中按 Esc 也可退出）
颜色图例：浅灰=未测试，绿=已触发，橙=按下瞬间，红橙闪烁=长按/卡键。


三、目录结构
keyboard-tool/
├─ src/
│  ├─ keyboard_test.cpp   # 全部逻辑: 布局/绘制/输入/状态机
│  ├─ app.rc              # 图标 + 版本信息资源
│  ├─ make_icon.py        # 纯标准库生成多尺寸 ICO (4x 超采样)
│  ├─ build.sh            # 一键构建
│  ├─ shot.py             # 测试用: PrintWindow 截图 + 纯 Python PNG 编码
│  ├─ test_gui.py         # 测试用: 截图/按键/最小化/关闭 自动验证
│  ├─ test_states.py      # 测试用: 高进度/全屏/21:9/最小尺寸 渲染验证
│  ├─ smoke_test.py       # 测试用: 按键 / 长按 验证
│  ├─ test_resize.py      # 测试用: 多尺寸 + F11 验证
│  └─ test_mouse.py       # 测试用: 点击 / 重置 验证
├─ shots/                 # 历史验证截图
├─ tools/                 # i686 MinGW-w64 工具链 (仅构建需要, 可删)
└─ README.md
