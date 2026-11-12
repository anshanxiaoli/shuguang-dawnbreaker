# 曙光号 · DAWN BREAKER

同一场 60 秒宇宙空战，两种完全不同的拍法 —— **A｜赛璐璐动画版** vs **B｜写实机甲版**。
两个版本都是**单文件、零构建**的 Web 作品：打开 HTML 就能播放，可拖动进度、可倒放、可逐帧定位。

## 在线预览 / Live Demo

| | 互动版 | 风格 |
|---|---|---|
| **Version A** | [toon.html](https://anshanxiaoli.github.io/shuguang-dawnbreaker/toon.html) | 日式赛璐璐三段着色 + 反壳轮廓线，变形机设（战机⇄人形），160 BPM 程序化电子乐，日文文案 |
| **Version B** | [mecha.html](https://anshanxiaoli.github.io/shuguang-dawnbreaker/mecha.html) | PBR 写实材质 + 程序化地球/大气，实例化小行星带，132 BPM 配乐 + 拟真音效，中文文案 |

🎬 60 秒同步对比片：[compare/shuguang-compare.mp4](https://anshanxiaoli.github.io/shuguang-dawnbreaker/compare/shuguang-compare.mp4)（左右分屏，音频按幕在 A/B 间交替）

## 本地运行

无需构建，直接用浏览器打开任一 HTML 即可（Three.js / GSAP 来自 cdnjs，需联网）：

```
open toon.html    # 或 mecha.html
```

快捷键：`空格` 播放/暂停 · `←/→` ±2s · `R` 重播 · `V` 倒放 · `M` 静音 · `H`（A 版）隐藏 HUD

## 技术要点

- **纯函数时间轴**：一切画面状态 = `f(t)`，任意 seek 结果一致，倒放无损
- **程序化音频**：WebAudio `OfflineAudioContext` 离线烘焙整轨（作曲、混音、压缩、混响全在代码里）
- **手写后处理链**：亮度提取 → 半分辨率双向高斯 → 合成（泛光/色差/暗角/径向模糊/冲击帧），不依赖 EffectComposer
- **确定性随机**：固定种子 RNG，每次刷新画面完全一致

## License

MIT
