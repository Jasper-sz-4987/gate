# gate

VPN Gate 节点检测与 GitHub Pages 发布，用于 qiiqii.cc 部署。

## 配置

1. 在仓库 Settings → Secrets and variables → Actions 添加 Secret `DOMAIN`，值为 `check.matkehiatanley6178.workers.dev`。
2. 在 Settings → Pages 中将 Source 设为 GitHub Actions。
3. 在 Actions 中手动运行 `VPN Gate Node Check`。工作流默认每天 00:00 UTC 自动运行。
4. 工作流成功后访问 `https://jasper-sz-4987.github.io/gate/nodes.txt`。确认文件实际生成并可访问后，再将该 URL 填入 edgetunnel 后台“自定义优选IP”。

脚本、依赖和工作流分别位于 `vpngate.py`、`requirements.txt` 和 `.github/workflows/vpngate.yml`。`DOMAIN` 可以是 Worker 主机名，脚本会补全检测路径。生产使用前请查看 Actions 日志和节点检测结果。不要把管理员密钥或 UUID 提交到仓库。
