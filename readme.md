# Mobile Focus Interceptor

通过拦截 SillyTavern 的自动聚焦行为，阻止移动端页面在面板切换时反复弹出虚拟键盘，只在用户真正点击输入框时才允许键盘出现，从而消除卡顿、提升浏览流畅度。

## 聚焦拦截范围

- 默认只拦截 SillyTavern 主会话输入框 `#send_textarea` 的脚本自动聚焦，避免全局修改影响扩展和弹窗中的其他输入框。
- 用户直接点击输入框或关联的 `<label>` 时会正常聚焦；许可与具体目标绑定，不会因为点击了另一个输入框而误放行。
- 为元素添加 `data-mfi-block-auto-focus`，可将它加入自动聚焦拦截范围。
- 为元素或其祖先添加 `data-mfi-allow-focus`，可始终允许程序化聚焦。
- `#phone-panel-content` 内的输入控件默认豁免，避免影响嵌入式手机扩展的输入体验。
