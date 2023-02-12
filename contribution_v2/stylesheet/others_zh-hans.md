# 为 Wiki 定制的样式

由于 Docsify 原生样式尚存不足，本 Wiki 在其基础上，定制了若干文字样式，以丰富阅读体验。本页将重点介绍它们的用法。  
它们均存放于根目录下 `assets/css/common.css` 文件中。

Wiki 同时也对 Docsify 提供的“深色主题”样式进行了深度改良，并挂载于 `assets/css/dark.css`。“浅色”主题未有变动。

## 定制样式

!> **使用原则**

* **尽量优先使用 Markdown 和 HTML 的默认样式。**如果确实无法满足，再考虑使用这里的样式。
* 可供引用的样式数量应保持精简。
* 所有定制样式的类名，应以 `aw-` 开头，以免与 Docsify 内置的样式发生冲突。

下面列举出所有通用样式的示例使用方法。

### 常用样式

| 样式 | 在源文件中编辑 | 效果 |
| - | - | - |
| 隐藏的文本<br>当鼠标移动到 / 在触摸屏上点击该文本时，内容就会重现。 | `<span class="aw-spoiler">我藏起来啦</span>` | <span class="aw-spoiler">我藏起来啦</span> |
| 有着注释的文本 | `<span class="aw-explain" title="对于该词的解释内容">Chrome</span>` | <span class="aw-explain" title="包括其它基于 Chromium，且内核版本 ≧32 的浏览器">Chrome</span> |
| 重要的文本 | `<span class="aw-important">重要的文本</span>` | <span class="aw-important">重要的文本</span> |

### 不常用样式

| 样式 | 在源文件中编辑 | 效果 |
| - | - | - |
| 红色标注；<br />旧式近战武器 | `<span class="aw-mark-red">红色标注</span>` | <span class="aw-mark-red">红色标注</span> |
| 绿色标注；<br />旧式远程武器 | `<span class="aw-mark-green">绿色标注</span>` | <span class="aw-mark-green">绿色标注</span> |
| 蓝色标注；<br />旧式魔法武器 | `<span class="aw-mark-blue">蓝色标注</span>` | <span class="aw-mark-blue">蓝色标注</span> |
| 黄色标注；<br />旧式召唤武器 | `<span class="aw-mark-yellow">黄色标注</span>` | <span class="aw-mark-yellow">黄色标注</span> |
| 紫色标注；<br />原 T4 怪物及武器 | `<span class="aw-mark-purple">紫色标注</span>` | <span class="aw-mark-purple">紫色标注</span> |

> 注：<span class="aw-important">重要的文本</span>是<span class="aw-mark-red">红色标注</span>的加粗型。

定制工作主要集中在**配色**上。为便于维护，已改动的样式被移至 `dark.css` 文件前列。感兴趣者可在本地环境下尝试修改。  

此页面原文来自NyaaCat
