# Windows 壁纸助手 · 交互 Demo

`LU55l`（锁屏）与 `r5F9TT`（桌面挂件）两个画板稿生成的可交互网页 Demo，零依赖、无需构建。

## 在线预览

**https://tai-ipx.github.io/store-live-wallpaper/** —— 根目录自动跳转到 `demo/index.html`。

> 由 GitHub Pages 从 `main` 分支根目录发布；页面本身是纯静态资源，不需要任何构建。

也可以直接打开 `demo/index.html`，但**必须用 http 服务**——壁纸与字体通过相对路径加载，`file://` 下会被浏览器拦截：

```bash
python3 -m http.server 8765
# 打开 http://localhost:8765/demo/index.html
```

## 结构

```
index.html     根目录跳转页（GitHub Pages 入口）
demo/          演示本体：index.html + assets/（壁纸、缩略图、六个视频封面）
images/        Demo 依赖的外部素材：六个动态壁纸 MP4、D-DIN 字体、三张窗口截图
```

> `demo/index.html` 里对 `../images/...` 的引用是刻意保留的相对路径，
> 所以 `demo/` 与 `images/` 必须放在同一层，不要单独移动其中一个。

## 交互说明

完整的交互说明见 [`demo/README.md`](./demo/README.md)。
