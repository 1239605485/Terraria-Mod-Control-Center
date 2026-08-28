# 构建 v0.1.7

推荐直接使用仓库自带的 GitHub Actions 工作流：

1. 将本目录全部文件上传到 GitHub 仓库根目录。
2. 打开仓库的 **Actions** 页面。
3. 运行 **Build MOD Control Center ImGui Full Damage Test**。
4. 下载产物 `泰拉MOD控制中心-v0.1.7-FullDamage-Test`。
5. 将下载后的产物作为 ZIP 导入 TEFManager。

工作流固定使用 Android NDK r28c、arm64-v8a、Android API 24，并自动获取 Dear ImGui v1.92.9 与 ShadowHook v1.0.10。

不要把旧版 v0.1.6 的 `.so` 放入 v0.1.7 包中，否则版本信息变化了，但实际修复代码不会生效。
