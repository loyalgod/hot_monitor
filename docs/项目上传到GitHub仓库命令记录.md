# 项目上传到 GitHub 仓库命令记录

## 背景

将经过改造（去除原始仓库痕迹）的项目上传到新建的 GitHub 仓库 `https://github.com/loyalgod/hot_monitor.git`。

## 完整命令流程

### 1. 初始化 Git 仓库

```bash
git init
```

在项目根目录下创建新的 `.git` 目录，初始化版本控制。

### 2. 重命名分支为 main

```bash
git branch -M main
```

将默认分支从 `master` 重命名为 `main`，与 GitHub 默认分支保持一致。

### 3. 添加远程仓库

```bash
git remote add origin https://github.com/loyalgod/hot_monitor.git
```

将 GitHub 仓库地址添加为远程仓库，命名为 `origin`。

> 如果使用 SSH 方式：
> ```bash
> git remote add origin git@github.com:loyalgod/hot_monitor.git
> ```

### 4. 添加所有文件到暂存区

```bash
git add .
```

将所有项目文件添加到 Git 暂存区。

### 5. 创建首次提交

```bash
git commit -m "Initial commit: AI hotspot monitoring tool"
```

创建项目的第一个提交记录。

### 6. 推送到远程仓库

```bash
git push -u origin main
```

将本地 `main` 分支推送到远程 `origin` 仓库，并设置上游跟踪关系。

## 常用后续命令

### 查看远程仓库配置

```bash
git remote -v
```

### 查看当前状态

```bash
git status
```

### 日常开发工作流

```bash
# 修改文件后添加
git add .

# 提交更改
git commit -m "描述本次修改内容"

# 推送到远程
git push
```

### 拉取远程更新

```bash
git pull origin main
```

## 注意事项

1. **HTTPS vs SSH**：HTTPS 需要输入 GitHub 账号密码或 Personal Access Token；SSH 需要配置 SSH Key
2. **首次推送**：使用 `-u` 参数设置上游跟踪，后续可直接使用 `git push`
3. **大文件**：如果项目包含大文件（>100MB），需要使用 Git LFS
4. **敏感信息**：确保 `.env`、`.gitignore` 等文件已正确配置，避免泄露敏感信息

## 完整命令汇总

```bash
# 一次性执行所有命令
git init
git branch -M main
git remote add origin https://github.com/loyalgod/hot_monitor.git
git add .
git commit -m "Initial commit: AI hotspot monitoring tool"
git push -u origin main
```

## 验证推送结果

在浏览器中打开 `https://github.com/loyalgod/hot_monitor`，确认所有文件已正确上传。
