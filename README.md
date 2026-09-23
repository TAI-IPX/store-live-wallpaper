# Windows 壁纸助手 · 交互 Demo

> ### ▶ 直接打开就能玩：[**https://tai-ipx.github.io/store-live-wallpaper/**](https://tai-ipx.github.io/store-live-wallpaper/)
>
> 公开站点，**无需登录、无需安装、无需构建**，点开即用。手机/平板也能打开（会等比缩放）。

`LU55l`（锁屏）与 `r5F9TT`（桌面挂件）两个画板稿生成的可交互网页 Demo，零依赖、无需构建。

## 直接进入某个状态（深链）

不想自己操作的话，这些链接可以直接落到指定画面：

| 链接 | 打开后看到 |
| --- | --- |
| [打开主页](https://tai-ipx.github.io/store-live-wallpaper/) | 锁屏（默认，动态壁纸已在播放） |
| [`?s=desktop`](https://tai-ipx.github.io/store-live-wallpaper/?s=desktop) | 桌面 + 壁纸助手挂件已展开 |
| [`?assist=1`](https://tai-ipx.github.io/store-live-wallpaper/?s=desktop&assist=1) | 桌面，并**钉住**壁纸助手浮窗（不会自动收起） |
| [`?menu=1`](https://tai-ipx.github.io/store-live-wallpaper/?menu=1) | 锁屏，「设为 …」菜单固定展开 |
| [`?wall=2`](https://tai-ipx.github.io/store-live-wallpaper/?wall=2) | 直接定位到第 3 张动态壁纸 |
| [`?detail=2`](https://tai-ipx.github.io/store-live-wallpaper/?detail=2) | 直接进该壁纸的详情页 |
| [`?app=1`](https://tai-ipx.github.io/store-live-wallpaper/?app=1) | 走一遍客户端唤起动画，最后停在壁纸库 |
| [`?app=scroll`](https://tai-ipx.github.io/store-live-wallpaper/?app=scroll) | 直接停在「壁纸轮播设置」页 |
| [`?static=3`](https://tai-ipx.github.io/store-live-wallpaper/?static=3) | 关闭动态壁纸后的静态壁纸态（第 4 张） |

> 「Ctrl + L」在画板上有标注，但**本站未绑定该快捷键**，点击「唤起屏保」才是真正的入口。

## 本地运行

下载仓库后**必须用 http 服务**打开——壁纸与字体通过相对路径加载，`file://` 下会被浏览器拦截：

```bash
python3 -m http.server 8765
# 打开 http://localhost:8765/demo/index.html
```

## 结构

```
index.html     根目录跳转页（GitHub Pages 入口，自动进 demo）
demo/          演示本体：index.html + assets/（壁纸、缩略图、六个视频封面）
images/        Demo 依赖的外部素材：六个动态壁纸 MP4、D-DIN 字体、三张窗口截图
```

> `demo/index.html` 里对 `../images/...` 的引用是刻意保留的相对路径，
> 所以 `demo/` 与 `images/` 必须放在同一层，不要单独移动其中一个。

## 发布方式

GitHub Pages 从 `main` 分支**根目录**发布（仓库里没有构建步骤，推上去即生效）：

- 推 `main` → Pages 自动重新构建（约 1 分钟），无需其他操作；
- 根目录的 `.nojekyll` 阻止 Jekyll 处理，避免下划线开头的资源被过滤；
- 站点是**公开**的，仓库也是 public，任何人拿到链接都能直接打开。

## 交互说明

完整的交互说明见 [`demo/README.md`](./demo/README.md)。
