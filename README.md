# changhong-gongkai

定时触发器：通过 GitHub Actions 每 5 分钟调用一次巡检接口。

本仓库**不包含任何密钥或业务数据**，仅有一个工作流文件。所需参数均配置在仓库 Secrets 中：

| Secret | 说明 |
|---|---|
| `TICK_URL` | 巡检接口地址，必须为 `https://` |
| `CRON_SECRET` | 巡检接口的 Bearer 密钥 |

- 未配置 Secrets 时，工作流只输出警告并跳过，不会报错。
- 日志只输出 HTTP 状态码，不输出接口返回内容。
- 工作流每周自动保活，避免 60 天无提交后定时任务被停用。
