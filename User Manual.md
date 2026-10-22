- WeKnora Lite 便携版（Windows x64）
  =================================
  
  双击「WeKnora Lite.exe」即可启动，无需安装、无需管理员权限。
  
  便携模式
  --------
  本目录里有 portable.txt，程序会把全部数据放在同级的 data\ 目录：
    data\weknora.db                 知识库数据库
    data\files\                     上传/解析的文件
    data\appdata\WeKnora Lite\      偏好设置、签名密钥、WebView2 缓存
  
  因此整个目录可以随意移动 / 拷贝到 U 盘，删掉 data\ 就等于恢复出厂状态。
  
  首次使用
  --------
  1. 建议先启动本地 Ollama 并拉取模型（默认地址 http://127.0.0.1:11434）：
       ollama serve
       ollama pull qwen2.5:7b
       ollama pull nomic-embed-text
     也可以在应用「设置 → 模型」里改用任意 OpenAI 兼容服务。
  2. 启动后免注册登录，自动创建本地账号 admin@weknora.local。
  
  配置
  ----
  目录内的 .env 可改运行参数（数据库路径、日志级别、Ollama 地址等），改完重启生效。
  文件位置、端口、局域网访问等也可以在应用内「设置」里调整。
  
  注意
  ----
  * 需要 Microsoft Edge WebView2 运行时（Windows 10/11 一般已自带）。
  * 程序未做数字签名，个别安全软件可能拦截首次运行或阻止其写用户目录；
    便携版把数据写在自身目录，规避了「无权写 %APPDATA%」的问题。
  * Windows 版未内置 DuckDB 数据分析（上游 duckdb-go 的 Windows 静态库为 MSVC 构建，
    与 Go 的 MinGW CGO 工具链不兼容），相关功能会给出提示，其余能力不受影响。
