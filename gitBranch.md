# 111410525: git branch怎麼用

`git branch` 是 Git 中用來**管理與操作分支**的核心指令。

---

## 常用基本用法

### 1. 查看分支

* **查看本地所有分支**
```bash
git branch

```


* **查看本地與遠端（Remote）所有分支**
```bash
git branch -a

```


* **查看最新一次 Commit 訊息與分支**
```bash
git branch -v

```



### 2. 建立分支

* **新建分支**（僅建立，不自動切換過去）
```bash
git branch <branch-name>

```


* **新建並立即切換過去**（推薦常用組合）
```bash
git checkout -b <branch-name>
# 或使用較新的指令：
git switch -c <branch-name>

```



### 3. 切換分支

* **切換至已存在的分支**
```bash
git checkout <branch-name>
# 或使用較新的指令：
git switch <branch-name>

```



### 4. 重命名分支

* **修改目前所在的分支名稱**
```bash
git branch -m <new-branch-name>

```



### 5. 刪除分支

* **安全刪除分支**（若該分支還有未合併的修改會發出警告）
```bash
git branch -d <branch-name>

```


* **強制刪除分支**（放棄該分支所有未合併的修改）
```bash
git branch -D <branch-name>

```



---

## 典型開發工作流程範例

1. **新建並切換至功能分支:**
開發新功能時，從主分支建立獨立分支進行修改：

```bash
git checkout -b feature/login

```


2. **提交變更:**
在該分支完成程式碼修改並提交：

```bash
git add .
git commit -m "Add login feature"

```


3. **切回主分支並合併:**
切回主分支（如 `main`），並將新功能合併進來：

```bash
git checkout main
git merge feature/login

```


4. **清理已合併的分支:**
功能完成且合併後，刪除舊分支保持乾淨：

```bash
git branch -d feature/login

```