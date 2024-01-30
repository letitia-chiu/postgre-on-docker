# 使用 Docker 執行 PostgresSQL 與 pgAdmin
透過 Docker compose 快速設置 PostgresSQL 與其管理工具 pgAdmin。  
參考資料：[使用 Docker 執行 PostgresSQL 與 pgAdmin | 永誌不忘 • 筆記簿](https://calvinegs.github.io/posts/docker-postgres-pgadmin/)

## 事前準備
✔ 需安裝 Docker 與 Docker Compose。  
可直接安裝 [Docker Desktop](https://www.docker.com/products/docker-desktop/)，後續可直接透過 Docker Desktop 啟動服務。

## 安裝
1. 開啟終端機 (Terminal)，cd 至存放本專案的資料夾，執行以下指令將本專案 clone 至本機電腦。

```
git clone https://github.com/letitia-chiu/postgre-on-docker.git
```

2. 進入此專案資料夾

```
cd postgre-on-docker
```
3. 確認／調整設定
開啟專案資料夾中的 `docker-compose.yml` 確認相關設定。  
本專案使用的 PostgreSQL 與 pgAdmin 版本如下：
- postgres@16
- pgadmin4＠8.2
可自行更改所需版本、運行 port 等設定。

4. 建立 docker compose
在專案資料夾下（與 `docker-compose.yml` 相同目錄中）執行以下指令：
```
docker compose up
```
啟動完畢後，可於 Docker Desktop 的 Containers 分頁中確認運行狀況。  
以 ctrl + c 停止運行。

5. 再次啟動服務
若有安裝 Docker Desktop，可在 Containers 分頁看到此 Compose，可在此啟動／停止。  
或是透過 CMD 於專案資料夾下執行以下指令來啟動／停止服務：
```
docker compose start
docker compose stop
```

## 使用 pgAdmin 連線至 Postgres DB
1. 開啟瀏覽器，於指定 port（本專案預設為 http://localhost:5431/ ）進入 pgAdmin。
2. 第一次開啟，會要求建立 pgAdmin 的密碼，輸入自訂密碼後按下 ok，後續開啟需輸入此密碼。
3. 接著會要求輸入資料庫的使用者密碼(本專案是設定為 docker)，輸入密碼後按下 ok。
4. 密碼輸入完畢後，就可以進行各項操作。