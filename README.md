# GitHub-FirstTry

GitHub 簡單設定以及同步 GitHub 與電腦間兩端的 code

本文參考[沈弘哲的 YouTube](https://www.youtube.com/user/blue524326/) 教學 [github 基本教學 - 從無到有](https://www.youtube.com/watch?v=py3n6gF5Y00)。

## 在 GitHub 網站申請帳號

參考 [Signing up for a new GitHub account](https://help.github.com/en/github/getting-started-with-github/signing-up-for-a-new-github-account)。

在 [GitHub](https://github.com/) 網站先申請帳號。

![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_20-56-25.png)

## 在新電腦上設定 Git

1. ### 到 [Git](https://git-scm.com/downloads) 網站下載 Git 並且安裝。

2. ### 產生 SSH Key：

    參考 [Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)。

    開啟 Git Bash，輸入以下指令：

    ```bash
    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_21-14-42.png)

    進入互動模式，輸入 `Enter` 鍵即表示接受預設值。預設會在 User Profile 目錄下的 \\.ssh 目錄產生私鑰檔案 (id_rsa) 與 公鑰檔案 (id_rsa.pub)。
    
3. ### 將 SSH Key 加到自己的 GitHub 帳戶：

    參考 [Adding a new SSH key to your GitHub account](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)。

    開啟公鑰檔案（~\\.ssh\id_rsa.pub），複製其內容。
    
    開啟 GitHub 網站，點選右上角 Settings。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_21-37-04.png)
    
    再點到 SSH and GPG Keys ➜ SSH Keys ➜ `New SSH Key` 按鍵。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_21-45-58.png)
    
    張貼到[網頁](https://github.com/settings/ssh/new)的 Key 欄位中，再輸入 Title 後，按下 `Add SSH Key`。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-00-01.png)
    
    完成後，Email 信箱會收到一封來自 GitHub 的通知信。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-02-10.png)
    
4. ### Git 設定帳號與 Email：

    參考 [Setting your username in Git](https://help.github.com/en/github/using-git/setting-your-username-in-git)。
    
    在 Git Bash 輸入以下指令：

    ```bash
    $ git config --global user.name "your name"
    $ git config --global user.email "your_email@example.com"
    ```

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-10-22.png)

## 在 GitHub 網站開新專案

參考 [Creating a new repository](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository)。

右上角 `+` 號下的 `New Repository`：

![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-17-04.png)

輸入專案名稱，其餘可視需要填寫，填寫完後按下 `Create repository`：

![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-30-55.png)

## 複製專案到電腦

在該專案頁面下，找到 `Clone or Download`，複製該網址。

![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_22-37-58.png)

在電腦上開一個資料夾，Git Bash 切換到該路徑下，輸入剛才複製的網址內容。

```bash
$ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

整個專案就會下載為以該專案為檔名的資料夾了，當中有 REDAME.md 檔案。

![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_23-00-51.png)

## 若電腦內專案的檔案內容有更新

1.  ### Git Bash 切換到該專案路徑。

2.  ### 將有變更的檔案加入追蹤：

    ```bash
    $ git add modified.file
    ```

3.  ### Commit。並且需要加上一點註解 / 訊息。

    ```bash
    $ git commit -m "Some comment"
    ```

4.  ### 將專案上傳至 GitHub：

    ```bash
    $ git push
    ```

    過程如圖所示：

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-02_23-58-01.png)

    此時回到 GitHub 專案頁面，會發覺頁面更新了。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-03_00-14-09.png)

## 若 GitHub 上專案內容有更新

1.  ### 先將 GitHub 上的 README.md 內容稍作修改。

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-03_00-25-27.png)

2.  ### Git Bash 切換到該專案路徑。

3.  ### 輸入以下指令

    ```bash
    $ git pull --rebase
    ```

    ![](https://github.com/hsychen/GitHub-FirstTry/blob/master/images/2020-02-03_00-28-16.png)
