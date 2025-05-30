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




## 專案 Container Image 自動化建置與 Tagging 邏輯

本專案使用 GitHub Actions 自動化產生 Container Image。

**自動化建置邏輯：**

當程式碼變動時（推送、PR、手動觸發），GitHub Actions 會自動：

1.  下載最新程式碼。
2.  根據 `Dockerfile` 建置 Docker Image。

**Tag 的選擇邏輯：**

* **`latest`**: 主要分支最新的穩定版本。
* **`vX.Y.Z`**: 對應發布版本 (Git Tag)。
* **`pr-XXX`**: 針對 Pull Request 的測試版本。

透過自動化建置和清晰的 Tag 策略，方便管理不同版本和用途的 Container Image。
