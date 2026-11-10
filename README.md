# HAC 学者、期刊与方法文献

> **网页版（点开就是渲染好的页面）**
> ## 👉 https://menghualu-newstart.github.io/HAC-methods/
>
> 打不开时把上面的地址复制到浏览器地址栏，不要在这里点代码文件。

## 各页面直达链接

| 页面 | 链接 |
|---|---|
| 学者 | https://menghualu-newstart.github.io/HAC-methods/ |
| 期刊与编辑 | https://menghualu-newstart.github.io/HAC-methods/#journals |
| 经典方法（含课程配套资料） | https://menghualu-newstart.github.io/HAC-methods/#methods |
| 经典文献 | https://menghualu-newstart.github.io/HAC-methods/#refs |
| 专刊与征稿 | https://menghualu-newstart.github.io/HAC-methods/#cfps |
| 伯克利 DRL 课程材料（子页面） | https://menghualu-newstart.github.io/HAC-methods/methods/drl-berkeley.html |

## 记住这条规律

```
仓库地址   github.com/用户名/仓库名
网页地址   用户名.github.io/仓库名
```

把 `github.com/` 换成 `用户名.github.io/` 就得到网页地址。

## 文件说明

| 文件 / 目录 | 作用 |
|---|---|
| `index.html` | 主页面：五个 tab（学者 / 期刊与编辑 / 经典方法 / 经典文献 / 专刊） |
| `style.css` | 全站样式（颜色、字号、间距、卡片），主页面与子页面共用 |
| `methods/` | 二级页面，例如伯克利课程材料目录 |
| `pdf/` | PDF 原件，卡片里的链接指向这里 |

## 怎么更新

### 只改内容（大多数情况）

1. 打开 GitHub Desktop，确认仓库是 `HAC-methods`
2. 用 VS Code 改本地文件，双击 `index.html` 预览（`#methods`、`#refs`、`#cfps` 可切视图）
3. 满意后在 Desktop 里写 Summary → **Commit to main** → **Push origin**
4. 等 30–60 秒，刷新网页版地址（按 `Ctrl+F5` 强制刷新）

### 加一篇 PDF

1. 文件放进 `pdf/`，**文件名用英文小写加连字符**（如 `causal-inference-notes.pdf`）
2. 在对应页面的卡片里写相对路径：`<a class="sch" href="pdf/causal-inference-notes.pdf">PDF ↗</a>`
3. 单文件不要超过 100 MB；超过 25 MB 不能用网页上传，要用 GitHub Desktop 推送

### 改样式

`style.css` 是全站共用的文件，**改之前先跟另外两位说一声**，改完立刻 push。

## 协作约定

- 一人负责一个 tab（学者 / 期刊与编辑 / 经典方法 / 经典文献 / 专刊），各改各的区块
- 不要两个人同时改 `style.css`
- 不要用 Force push
- 改坏了不用慌：仓库首页点 Commits 能找到历史版本回滚

---

整理于 2026-11 · 供文献梳理与投稿参考
