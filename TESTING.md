# v0.1.8 真机测试

1. 卸载旧版 `celso.modcontrolcenter`，安装 v0.1.8 后完全结束 Terraria 进程。
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
MCCProbe.MANAGED_DRAW_SEEN
MCCProbe.MANAGED_DRAW_NO_CONTEXT
MCCProbe.PIXEL_READBACK_OK / MCCProbe.PIXEL_READBACK_FAIL
MCCProbe.PROBE_PIXEL_...
```

`MANAGED_DRAW_SEEN + PIXEL_READBACK_OK` 时应出现左下角洋红色方块和顶部 `MOD` 按钮；若出现 `MANAGED_DRAW_NO_CONTEXT`，说明该版本的 `Main.Draw` 不是 GLES 上下文所在位置，需要进一步改挂 `GraphicsDevice.Present`。
