[README.md](https://github.com/user-attachments/files/31876224/README.md)
# NCRE 刷题题库（GitHub Pages）

这是一个无需构建工具的单文件刷题应用，打开 `index.html` 即可使用，也可以直接部署到 GitHub Pages。

## 题库边界与官方依据

- 当前内置 1,856 道整理练习题，覆盖 C 语言、公共基础、MS Office、WPS Office 和三级 Linux；其中 C 语言 862 道、WPS Office 373 道。新增题目以“原创练习·2025大纲”标识。
- 题目、解析和套题来自项目整理，**不是教育部教育考试院发布的官方完整题库**，不能用作官方真题或考试保证。
- 复习时以中国教育考试网发布的 [NCRE 2025 版考试大纲](https://ncre.neea.edu.cn/html1/report/2412/185-1.htm) 和 [官网试题选登](https://ncre.neea.edu.cn/html1/category/1507/848-1.htm) 为准；可直接查看 [二级 C 语言大纲 PDF](https://ncre.neea.edu.cn/res/Home/2306/6016844d02b8b7fb5d9ea3981f0a0eb9.pdf) 与 [二级 WPS 样题 PDF](https://ncre.neea.edu.cn/res/Home/2501/5126369bd7cb69093afc8646f43acc51.pdf)。
- 题库内容应按新大纲持续人工复核，尤其是考试科目、软件版本、题型和答案解析；仓库不自动抓取或转载受版权保护的完整试卷。

## 已完成的关键优化

1. 顺序、随机、专项和错题练习会优先安排未做题；随机/模拟练习会避开最近 120 道已看题，降低连续重复。
2. 题目在非套题模式按“题干 + 选项 + 答案”去重；套题模式保留同题多次出现，用于还原试卷语境。
3. 近期题目记录写入浏览器 `localStorage`，刷新页面后仍然生效；清除记录不会影响题库文件。
4. 主页明确展示题库边界、官方大纲和官方样题入口，避免把整理题误认为官方题库。
5. 增加 GitHub Pages 工作流，可在仓库设置中选择 Actions 部署。
6. 依据 2025 版 C 语言 12 个大纲模块和 WPS 综合、文字、表格、演示、PDF、在线协作模块，新增 342 道去重后的原创练习题（C 语言 138 道、WPS 204 道）。

## GitHub Pages 部署

1. 在 GitHub 新建仓库，将本目录中的 `index.html`、`README.md`、`.nojekyll` 和 `.github/workflows/pages.yml` 上传到仓库根目录。
2. 打开仓库 `Settings -> Pages`，将构建来源设为 `GitHub Actions`。
3. 推送到 `main`（或默认分支）后，工作流会自动发布；完成后地址通常为 `https://<用户名>.github.io/<仓库名>/`。

本次环境没有提供 GitHub 仓库地址、账号授权或推送令牌，因此这里只完成可发布项目和自动部署配置，未代替用户执行远程推送。

## 本地验证

直接双击 `index.html` 即可运行。若浏览器限制本地文件，可在本目录执行：

```bash
npx serve .
```

刷题记录只保存在当前浏览器，不会上传到服务器。
