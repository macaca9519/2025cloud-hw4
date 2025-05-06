# 2025cloud-hw4
# 您的專案名稱

這個專案包含兩個不同的應用程式，它們分別使用不同的 Dockerfile 進行打包和運行。

## 打包應用程式

### 主要應用程式 (`Dockerfile`)

**指令:**
```bash
docker build -t your_username/main_app:latest -f Dockerfile .
```
描述: 使用 Dockerfile 在目前目錄建構名為 your_username/main_app，標籤為 latest 的映像檔。

第二個應用程式 (Dockerfile.app2)
指令:

```Bash

docker build -t your_username/app2:latest -f Dockerfile.app2 .
```
描述: 使用 Dockerfile.app2 在目前目錄建構名為 your_username/app2，標籤為 latest 的映像檔。

運行 Container Image
運行主要應用程式
指令範例 (假設需要 Port Mapping):

```Bash

docker run -p 8080:80 your_username/main_app:latest
```
描述: 運行 your_username/main_app:latest 映像檔，並將 Container 的 80 Port 映射到 Host 的 8080 Port。

運行第二個應用程式
指令範例 (假設需要在背景運行):

```Bash

docker run -d --name my_app2 your_username/app2:latest
```
描述: 在背景運行名為 my_app2 的 your_username/app2:latest 映像檔。
