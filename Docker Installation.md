
##### 更新 APT 倉庫
```bash
sudo apt update && sudo apt upgrade -y
```

##### 安裝必要的依賴工具
```bash
sudo apt install -y ca-certificates curl
```

##### 創見 keyrings 目錄
```bash
sudo install -m 0755 -d /etc/apt/keyrings
```
##### 下載 Docker GPG 密鑰
```bash
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
```

###### 設定權限
```bash
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

##### 添加 Docker 軟體倉庫
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#####  更新 APT 倉庫
```bash
sudo apt update
```

##### 安裝 Docker 引擎和相關工具
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---
##### 測試安裝是否成功
```bash
sudo docker run hello-world
```
