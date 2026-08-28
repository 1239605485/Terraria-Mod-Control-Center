# v0.1.7 真机测试

1. 卸载旧版 `celso.modcontrolcenter`，安装 v0.1.7 后完全结束 Terraria 进程。
2. 重新启动游戏，进入主菜单或世界后等待 5~10 秒。
3. 观察左下角是否出现紫色小方块、顶部中间是否出现青色小方块和 `MOD`。
4. 导出 TEFManager 日志。

重点查看：

```text
MCCProbe.SWAP_SURFACE_MATCH
MCCProbe.SWAP_SURFACE_MISMATCH
MCCProbe.MAKECURRENT_OK
MCCProbe.VIEWPORT_SEEN
MCCProbe.FB_COMPLETE
MCCProbe.EGL_SURFACE_...
MCCProbe.GL_VIEWPORT_...
MCCProbe.GAME_SIZE_...
MCCProbe.SURFACE_RELATION_...
MCCProbe.GL_ERROR_...
MCCProbe.DAMAGE_KHR_SEEN / MCCProbe.DAMAGE_EXT_SEEN
MCCProbe.FULL_DAMAGE_FORCED
MCCProbe.PIXEL_READBACK_OK / MCCProbe.PIXEL_READBACK_FAIL
MCCProbe.PROBE_PIXEL_...
```

若仍不可见，请同时提供最新 TEFKernel 日志与模组私有目录中的 `imgui_runtime.log`。
