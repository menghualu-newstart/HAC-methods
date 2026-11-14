# HAC 学者、期刊与方法文献

> **网页版（点开就是渲染好的页面）**
> ## 👉 https://hacdm.github.io/HAC-methods/
>
> 打不开时把上面的地址复制到浏览器地址栏，不要在这里点代码文件。

## 各页面直达链接

| 页面 | 链接 |
|---|---|
| 学者 | https://hacdm.github.io/HAC-methods/ |
| 期刊与编辑 | https://hacdm.github.io/HAC-methods/#journals |
| 经典方法（含课程配套资料） | https://hacdm.github.io/HAC-methods/#methods |
| 经典文献 | https://hacdm.github.io/HAC-methods/#refs |
| 专刊与征稿 | https://hacdm.github.io/HAC-methods/#cfps |
| 伯克利 DRL 课程材料（子页面） | https://hacdm.github.io/HAC-methods/methods/drl-berkeley.html |

## 文件说明

| 文件 / 目录 | 作用 |
|---|---|
| `index.html` | 主页面：五个 tab（学者 / 期刊与编辑 / 经典方法 / 经典文献 / 专刊） |
| `style.css` | 全站样式（颜色、字号、间距、卡片），主页面与子页面共用 |
| `methods/` | 二级页面，例如伯克利课程材料目录 |
| `pdf/` | PDF 原件，卡片里的链接指向这里 |

## 怎么修改

### 0. 第一次：装软件 + 登录 + 拿到仓库

1. 装 **GitHub Desktop**：https://desktop.github.com/
2. 打开后先 **Sign in to GitHub.com**，用你自己的 GitHub 账号登录
   （**不登录的话，clone 和 push 都会失败**）
3. **File → Clone repository** → 选 `HACDM/HAC-methods`
4. 本地路径选 **F 盘（仅作示例）**，例如 `F:\文档\GitHub\HAC-methods`
5. 装 **VS Code** → **File → Open Folder** → 选这个目录

### 1. 找到要改的那一段

`index.html` 里五个 tab 各占一段，搜锚点就能定位：

| tab | 搜这个 | 卡片外层标签 |
|---|---|---|
| 学者 | `id="page-scholars"` | `<div class="card">` |
| 期刊与编辑 | `id="page-journals"` | `<div class="jcard">` |
| 经典方法 | `id="page-methods"` | `<div class="mcard">` |
| 经典文献 | `id="page-refs"` | `<div class="mcard">` |
| 专刊 | `id="page-cfps"` | `<div class="mcard">` |

### 2. 加一张卡片

找一张**同类**卡片，**整块复制**，粘在它后面，改四个地方：

```html
<div class="mcard" data-kind="课程">
  <div class="mtop"><div class="mname">名称</div><span class="mchip">课程</span></div>
  <div class="mfield">学科 · 作者</div>
  <div class="mdesc">一句话说清它是什么、怎么用（40 字内）。</div>
  <div class="mlinks"><a class="sch" href="https://..." target="_blank">链接 ↗</a></div>
</div>
```

改 **`mname`**（名称）、**`mfield`**（学科与作者）、**`mdesc`**（描述）、**`href`**（链接）。

### 3. 本地先看效果

双击 `index.html`，查看改后效果

### 4. 提交前先同步（重要）

1. 回到 GitHub Desktop，点顶部 **Fetch origin**
2. 如果右侧出现 **Pull origin** 按钮（说明别人已经推过新东西），**先点 Pull**
3. 没有 Pull 按钮、或者 Pull 完，才进下一步

**跳过这步的后果**：你本地是旧版本，提交时会冲突，或者把别人的改动盖掉。

### 5. 看一遍改动，再写提交说明

1. 左侧 **Changes** 面板列出改过哪些文件（一般只有 `index.html`）
2. **点文件名**，右侧出现逐行对照：绿色是新增、红色是删除
3. 确认只加了自己那段，没误删别人的卡片
4. 左下角 **Summary**(必填) 写一句话，例如「专刊新增 MISQE 与 ISF」
5. **Description**（可选）写详细说明
6. 点蓝色按钮 **Commit to main**

提交成功后，Changes 面板会显示「0 changed files」。

### 6. 推到 GitHub

1. 点右上角 **Push origin**
   （如果那里显示的是 **Publish branch**，点它，效果一样）
2. 弹出的登录窗口用同一个账号授权
3. 推送成功后，右上角变成 **Fetch origin**，旁边写「Last fetched just now」

**只 Commit 不 Push 的话，网页上不会有任何变化**——这一步最容易漏。

### 7. 等上线，再验证

1. 等 **30–60 秒**（GitHub Pages 要重新构建）
2. 打开 https://hacdm.github.io/HAC-methods/
3. 按 **Ctrl+F5** 强制刷新（不加这个可能看到旧页面）
4. 切到你改的那个 tab，确认内容对了

### 8. 推送失败对照表

| 提示 | 原因 | 怎么办 |
|---|---|---|
| 要求先 Pull / branch is out of date | 别人先推了 | 点 **Pull**，再 **Push** |
| 让重新登录 / 授权 | 首次推送，或令牌过期 | 用 GitHub 账号登录授权 |
| **Conflict**（冲突） | 同一行被别人改过 | **别硬推**，找我看，别自己乱改 |
| 一直转圈 / 网络错误 | 网络问题 | 换个网络重试，**不要连点多次** |

### 9. 忘了提交就关了软件

**改动不会丢**——文件在本地已经改了，下次打开 GitHub Desktop 还会显示在 Changes 里。

### 三种改动分别要注意什么

- **只改文字 / 加卡片**：按上面走，最省事
- **加 PDF**：文件放进 `pdf/`，**文件名英文小写加连字符**（如 `causal-inference-notes.pdf`）；单文件 **≤100 MB**，超过 **25 MB** 必须用 GitHub Desktop 推，网页上传会失败
- **改样式**：`style.css` 是全站共用的，改之前先跟另外两位说一声，改完立刻 push

## 改坏了怎么办

- **看历史**：仓库首页点 **Commits**，或 GitHub Desktop 的 **History**
- **想撤掉本地改动**：History 里右键上一次正常提交 → **Revert**
- **已经推上去才发现**：同样用 Revert，再推一次
- **拿不准**：先别 push，改动留在本地，找我看

## 协作约定

- 一人负责一个 tab，各改各的区块，改动的行不重叠，GitHub 能自动合并
- **不要两个人同时改 `style.css`**
- **不要直接在 GitHub 网页上改 `index.html`**，会和本地版本冲突
- 不要用 Force push

---

整理于 2026-11 · 供文献梳理与投稿参考
