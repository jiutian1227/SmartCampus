# 智慧校园平台（SmartCampus）

基于 HarmonyOS ArkUI 框架开发的轻量化智慧校园前端应用，面向鸿蒙设备用户提供课表查询、成绩查看、GPA计算、请假申请、校园资讯浏览等一站式校园服务。

## 项目说明

本项目为《OpenHarmony程序设计基础》课程设计，**纯前端项目**，所有数据采用本地 Model 模拟，不涉及后端与真实数据库交互。

## 技术栈

- **开发工具**：DevEco Studio 6.0.2
- **SDK版本**：HarmonyOS SDK 5.0.0.100 (API Level 12)
- **开发语言**：ArkTS
- **UI框架**：ArkUI
- **数据存储**：本地模拟数据（数组存储）
- **运行平台**：HarmonyOS / OpenHarmony

## 功能模块

- **用户认证**：学号密码登录、身份证校验账号激活、登录密码修改
- **学业服务**：课程表查询、期末成绩查询、GPA自动计算、线上请假申请与记录查看
- **校园资讯**：校园公告列表、学校要闻详情浏览
- **校园文化**：学校简介、校训校歌、校徽、校历、校园风光浏览
- **个人中心**：个人信息展示、个人二维码生成、系统设置

## 项目结构

```
SmartCampus/
├── AppScope/                    # 应用全局配置
│   ├── app.json5
│   └── resources/
├── entry/                       # 主模块
│   ├── src/main/ets/
│   │   ├── model/               # 数据层：数据模型与模拟数据
│   │   │   ├── UserModel.ets
│   │   │   ├── CourseModel.ets
│   │   │   ├── ScoreModel.ets
│   │   │   ├── LeaveModel.ets
│   │   │   ├── NewsModel.ets
│   │   │   ├── NoticeModel.ets
│   │   │   ├── SchoolIntroModel.ets
│   │   │   ├── SchoolScenicModel.ets
│   │   │   └── userState.ets    # 全局状态管理
│   │   ├── pages/               # 业务层：页面
│   │   │   ├── Login.ets
│   │   │   ├── Activation.ets
│   │   │   ├── Index.ets        # 主容器（Tabs底部导航）
│   │   │   ├── Home.ets
│   │   │   ├── Service.ets
│   │   │   ├── MyInfo.ets
│   │   │   ├── QrCodePage.ets
│   │   │   └── service/         # 业务子页面
│   │   │       ├── CourseTable.ets
│   │   │       ├── ScoreTable.ets
│   │   │       ├── GpaCalculator.ets
│   │   │       ├── LeavePage.ets
│   │   │       ├── NoticePage.ets
│   │   │       ├── NewsPage.ets
│   │   │       ├── SchoolIntroPage.ets
│   │   │       └── SchoolScenicPage.ets
│   │   └── resources/
│   ├── build-profile.json5
│   └── oh-package.json5
├── build-profile.json5
├── oh-package.json5
├── hvigorfile.ts
└── README.md
```

## 系统架构

采用三层架构设计：

- **数据层（Model）**：统一管理数据模型、模拟数据源与数据访问逻辑
- **业务层（Page/Component）**：实现UI渲染、用户交互与业务逻辑
- **状态管理层（userState.ets）**：管理全局用户登录状态与信息共享

## 核心技术实现

**ArkUI 高级组件**
- **Swiper**：首页轮播图，自动播放校园宣传图与重要通知
- **Grid / GridItem**：快捷功能入口、服务分类网格布局
- **Tabs**：底部全局导航（首页、服务、信息码、我的）
- **Router**：页面路由跳转与全局状态共享
- **CustomDialog**：修改密码、编辑信息、二维码展示、系统设置等弹窗
- **List / ListItem**：请假记录、公告列表、新闻列表等数据展示

**主要功能实现**
- 用户登录校验（区分密码错误 / 账号未激活）
- 课程表按班级+学期筛选展示
- 成绩查询与通过/未通过统计
- GPA 计算公式运算
- 请假申请提交与记录管理
- 二维码生成（含用户信息）
- 校园资讯图文展示与轮播

## 运行环境

- DevEco Studio 5.0 及以上
- HarmonyOS SDK API Level 12
- 手机模拟器或鸿蒙真机

## 运行步骤

1. 使用 DevEco Studio 打开项目
2. 等待依赖同步完成
3. 选择模拟器或连接鸿蒙真机
4. 点击运行按钮，编译并安装应用
5. 使用测试账号登录（学号 `20230801050142`，密码 `123456`）

## 开发说明

- 本系统为**纯前端演示项目**，未接入后端与数据库，应用重启后数据恢复初始状态
- 所有数据均在 `entry/src/main/ets/model/` 下的 Model 文件中以静态数组形式定义
- 部分图片资源位于 `entry/src/main/resources/base/media/` 目录

## 作者

九天
