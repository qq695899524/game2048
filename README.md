# 2048

2048 经典益智小游戏，纯单文件 HTML 实现（CSS/JS 全内联，零外部依赖），支持键盘方向键、WASD 与移动端滑动手势。

## 玩法

- 4×4 网格，方向键 / WASD / 滑动屏幕移动方块
- 相同数字碰撞合并，得分累加，冲向 2048
- 合成 2048 弹出胜利提示，可选择继续挑战更高分
- 棋盘满且无可合并时判定游戏结束
- 最高分自动保存（localStorage 容错适配）

## 技术架构

单文件内部分层：InputManager（键盘/触摸输入归一）→ GameManager（对局状态机）→ Grid/移动合并引擎（纯领域逻辑）→ StorageManager（持久化容错）→ Actuator（DOM 渲染与 CSS 动画）。逻辑与渲染严格分离，动画采用 DOM transform 过渡（≤100ms），Tile 身份标识跨帧复用保证动画连续。

## 在线体验

- 公网地址：http://121.36.229.39/hc-activity/index.html（华为云 Flexus L 实例 + Nginx 持久化部署）
- 沙箱地址：https://pfabrawu-80.devbridge-s2.hwtunnel.com（DevKit 沙箱部署）