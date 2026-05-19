# Newsget

面向新闻线索的多 Agent 协作 + 长链推理示例骨架，适配定时任务运行。

## 运行方式（本地）

安装依赖：

```powershell
python -m pip install -r requirements.txt
```

运行一次任务：

```powershell
python -m newsget.run_job
```

运行调度器（循环执行）：

```powershell
python -m newsget.scheduler
```

启动 FastAPI（仅健康检查与手动触发）：

```powershell
uvicorn newsget.main:app --host 0.0.0.0 --port 8000
```

## 环境变量

- `NEWSGET_WEATHER_API_KEY`：天行天气 API 密钥（可用 `NEWSGET_API_KEY` 兼容）
- `NEWSGET_WEATHER_API_BASE`：天行天气 API 地址（默认 `https://apis.tianapi.com/tianqi/index`）
- `NEWSGET_WEATHER_CITY`：城市名称/城市 ID/IP（默认 `上海`）
- `NEWSGET_WEATHER_TYPE`：查询类型，实时 `1` 或七天 `7`
- `NEWSGET_INTERVAL_SECONDS`：定时任务间隔秒数

## GitHub Actions 部署

已提供 `.github/workflows/deploy.yml` 占位工作流，请在仓库配置好 Secrets 后补充部署细节。
