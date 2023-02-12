# 参与贡献 Wiki

AicWiki 采用 [Docsify](https://docsify.js.org) 构建，源文件存放于 [GitHub](https://github.com/AliceInCradle-Community/Wiki)。

!>本文提及的用户均为官方Discord中的用户ID

### 参与要求 :id=required

- 明白本Wiki才用Markdown和HTML语言
- 了解 AliceInCradle 的内容。

### 参与方式

##### 加入 Editor

如果您得到`zelda123123#0896`或`Tsurukawa#6897`的认可，可以不经审核编辑内容，可通过上述两位的邀请加入。

##### 提交 PR

如果你尚不熟悉 Markdown 语法，但是希望参与贡献，可以 fork 本 repo 或直接在相应页面上方点击 "Edit on Github" 来编辑。

完成后，访问本 repo 并提交 Pull Request (PR)。Editor将 review 所有变更，如无问题，即可合并进本 repo。

但为了方便管理，你仍需联系`Tsurukawa#6897`来加入Writer，然后才可提交PR


### 文件结构

后缀标记:

- `A` 仅供Administrator组修改
- `E` 仅供Editor组修改

结构:

- `index.html` - 用于导入 Docsify，并包含 Docsify 的各项参数，请勿修改。`A`
- `README.md` - Wiki 主页内容。`E`
- `_navbar.md` - 导航栏，如无必要请勿修改。`E`
- `_sidebar.md` - 侧边栏，如果新增较重要的页面可在这里做相应的修改。
- `_404.md` - 404 页面，如无必要无需修改。`E`
- `assets` - 各种静态文件目录。
  - `css` - Wiki样式规则。`A`
  - `docsify` - Wiki基础组件。`A`
  - `images` - **图片存放处。**如需内部引用图片，请先复制至此。
  - `js` - Wiki基础组件。`A`
  - `xlsx-loader` - Excel表格加载渲染组件。`A`
- 分类目录说明
  - `contribution` - 已废弃，停止更新。
  - `contribution_v2` - 现版Wiki编辑说明。
  - `wiki` - Wiki内容，对应语言目录进行对应语言的编写。
    + `en` - 英语。
    + `ja` - 日语。
    + `ko` - 韩语。
    + `zh-hans` - 简体中文。
    + `zh-hant` - 繁体中文。
    + 若有其他语言的计划请自行新建目录。

  

- 此外各个语言的Wiki目录中的`_navbar.md`可根据语言进行翻译，`_sidebar.md`应当按照实际需求进行编辑，`README.md`则为当前语言Wiki的首页。

### 编辑说明 :id=editing-notes

1. **所有文本都必须使用 UTF-8 编码** 推荐使用 [VS Code](https://code.visualstudio.com/) 编辑器。
2. 编辑或新建页面时，应保持文件结构正确、整洁。
3. 文件和目录命名保持简洁，文件名应只包含英文、数字、下划线（`_`）、短线（`-`）。
4. Wiki 内的链接应使用相对路径，并注意检查引用路径是否正确。
5. 文本排版保持简洁、美观。中文和西文、数字之间要有空格。
6. 请勿滥用 heading 语法。推荐：
   - 页首标题使用HTML(避免侧边栏目录的重复索引) 二/三级 heading；
     + 当页面仅存在一个标题或存在总标题时，可使用二级HTML的heading, 若仅存在多个并列标题时候，应当使用Markdown的三级heading。
   - 章节/section 使用三级 heading；
   - 根据需求情况使用四、五级 heading。
   - 为方便引用及跳转，可将章节标题编辑成 `## 标题 :id=required` （其中 `required` 可替换为任意内容）。  
   此后，引用该章节仅需 `[像这样](#required)` 设置链接，例如在本页转到[参与要求](#required)。  
   如在其它页面引用该章节，`[可以这样](wiki/contribution_v2/basic/start_zh-hans#required)`。
7. 并不是所有的页面都要列入侧边栏。一些详细内容的页面也可以存放在相应目录下并通过其他页面访问。
8. 本Wiki源仓库托管于 GitHub，为确保拉取、推送顺畅，应尽量避免上传文本以外的文件。  
  对于图片，请规范上传至`assets/images`进行引用(建议使用Mozjpeg 与 PngQuant等工具对图片文件大小进行压缩)。
  对于非图片文件，请使用稳定可靠的文件托管外链服务。
9. Docsify 可能与你所用 Markdown 编辑器**存在分歧**。为避免过多的 commit，可先尝试在本地运行 Wiki 预览效果。
   - 如使用 VS Code，可以安装插件 [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)，然后点击右下角的 **Go Live**，用浏览器访问 `localhost:5500` 即可预览。  
   - 对于其它情况，可运行 `docsify serve`，然后浏览`localhost:4000`。
10. 本 Wiki 没有限制使用自定义 CSS，但请尽量避免使用这一手段改变内容样式。<br>
12. 所有 commit 的备注内容都将公开于众，为便于跟踪与更正，应如实概括所作变更，并避免加入任何无关信息。

(WIP)

### 推荐资源

* [Docsify 的特有文档语法](https://docsify.js.org/#/helpers)
* [其他便捷样式](contribution_v2/stylesheet/others_zh-hans)
* [Jpgmin](https://jpgmin.cn)——Mozjpeg 与 PngQuant 的第三方网页界面，压缩效果好，可批量压缩，操作简便。
