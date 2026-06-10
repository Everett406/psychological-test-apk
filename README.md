# 心理韧性深度测评

一个基于 HTML/CSS/JavaScript 的沉浸式心理测评小游戏，现已支持打包为 Android APK 应用。

## 项目说明

本项目是一个单页面 Web 应用，通过 Capacitor 框架封装为 Android 原生应用。

## 自动构建 APK

本项目已配置 GitHub Actions 工作流，推送代码到 main 分支后会自动构建 APK 并发布到 Release 页面。

## 本地构建 APK 步骤

### 环境要求
- Node.js 20+
- Java JDK 21
- Android Studio (含 Android SDK)

### 构建步骤

```bash
# 1. 安装依赖
npm install

# 2. 添加 Android 平台
npx cap add android

# 3. 同步 Web 资源到 Android 项目
npx cap sync android

# 4. 构建 Debug APK
cd android
./gradlew assembleDebug

# APK 输出路径：
# android/app/build/outputs/apk/debug/app-debug.apk
```

### 构建 Release APK

```bash
cd android
./gradlew assembleRelease
```

## 项目结构

```
psychological_test/
├── www/
│   └── index.html          # 主页面
├── .github/workflows/       # GitHub Actions 配置
├── capacitor.config.json    # Capacitor 配置
└── package.json
```

## 版本历史

- v1.0.0 - 初始版本，基础心理测评功能
- v1.0.1 - 修复 GitHub Actions 权限配置
