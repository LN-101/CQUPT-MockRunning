# README 截图

实机拍摄（HarmonyOS，浅色主题），原图 1224×2776。处理成 **720 宽 + 256 色 PNG（带抖动）** ——
UI 截图用调色板量化是标准做法，体积掉一半多，肉眼看不出差别。

| 文件 | 页面 | 内容 |
|---|---|---|
| `icon.png` | — | 应用图标（插画），README 顶部大图，512×512 真彩 |
| `01-run.png` | 【主页】 | 风华运动场 / 配速 5:45 / 距离 2.0 / 配速抖动 20 / **绿色**电池条 / 开始打卡 / 仪表盘 |
| `02-stats.png` | 【统计】 | 刷新统计 + 汇总 + 分场地 + 最近记录（数据已打码） |
| `03-start.png` | 【上手】 | 使用教程 + 账号 openid 输入 + 连接并拉取场地 |
| `04-settings.png` | 【设置】 | 主题三段式 + 说明 + 开源仓库入口 + 署名 |
| `05-battery-bad.png` | — | 电池条 · **红色**（未加白名单） |
| `06-battery-ok.png` | — | 电池条 · **绿色**（已加白名单，无 ✅ emoji） |
| `07-log.png` | 【日志】 | 完整运行日志，①~⑥ 全流程 |

> `01`~`04` 是 v1.10.0（底部四页悬浮栏）拍的。
> `05`~`07` 还是 v1.8 拍的，但那三处**没改过**，仍然准确：
> 电池条的红/绿两态、以及独立的日志页。

## 拍摄时做的脱敏

- `03-start.png` 里 openid 输入框填了内容，已打码
- `02-stats.png` 统计页所有数字打了码
- 旧图里日志的 `token =` 和 `sportRecordNo` 也打了码

## 重新处理

原图放一边，改 [`../../refs/icon/process_shots.py`](../../refs/icon/process_shots.py)
里的 `SRC` / `MAP` 后重跑（记得把 `MAP` 里的时间戳换成新截图的）：

```bash
python ../../refs/icon/process_shots.py <截图目录>
```

## 显示尺寸

README 里用 HTML `<img>` 控制宽度，不用 markdown 图片语法
（markdown 没法限宽，竖屏截屏会撑满整个页面）：

```html
<img src="docs/img/01-run.png" width="200">
```
