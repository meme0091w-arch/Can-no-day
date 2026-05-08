# 🎮 异环任务交易平台 (Game Task Platform)

一个功能完整的**企业级接单平台**，集成了 Fiverr、Upwork、猪八戒、闲鱼等顶级平台的核心功能。

## ✨ 核心特性

### 👥 用户系统
- ✅ 注册/登录（双重密码验证）
- ✅ OAuth 2.0 集成
- ✅ 个人档案定制（头像、昵称、简介）
- ✅ 打手认证审核系统
- ✅ 用户等级与信誉体系

### 💼 悬赏系统
- ✅ 发布悬赏任务
- ✅ 任务分类与标签
- ✅ 实时价格竞价
- ✅ 自动匹配推荐

### 🎯 接单系统
- ✅ 接单大厅展示
- ✅ 一键应聘/投标
- ✅ 并发抢单处理（分布式锁）
- ✅ 订单流程管理（已发布→进行中→已完成）
- ✅ 里程碑式付款

### 💬 沟通系统
- ✅ 实时即时通讯 (WebSocket)
- ✅ 消息已读状态
- ✅ 文件传输

### 💳 支付系统
- ✅ 支付宝/微信集成
- ✅ Stripe/PayPal 国际支付
- ✅ 担保交易
- ✅ 自动退款机制
- ✅ 交易记录审计

### ⭐ 评价系统
- ✅ 5星评价体系
- ✅ 详细评价标签
- ✅ 打手分级（新手→优质→精选→顶级）
- ✅ 平均响应时间统计

### 🔒 安全系统
- ✅ JWT 令牌认证
- ✅ 数据加密 (AES-256)
- ✅ XSS/CSRF 防护
- ✅ 速率限制
- ✅ IP 白名单
- ✅ 风险控制引擎
- ✅ 黑名单管理
- ✅ 完整审计日志

### 📊 数据分析
- ✅ 用户行为分析
- ✅ 收入统计仪表板
- ✅ 接单成功率分析
- ✅ 实时在线用户数

### 📱 前端特性
- ✅ 响应式设计（完全适配手机端）
- ✅ 离线缓存
- ✅ PWA 支持
- ✅ 深色/浅色主题切换

---

## 📂 项目结构

```
game-task-platform/
├── frontend/                      # Vue 3 + Vite 前端
│   ├── src/
│   │   ├── pages/                # 页面组件
│   │   │   ├── Login.vue         # 登录页
│   │   │   ├── Register.vue      # 注册页
│   │   │   ├── Profile.vue       # 个人主页
│   │   │   ├── TaskList.vue      # 接单大厅
│   │   │   ├── PublishTask.vue   # 发布悬赏
│   │   │   ├── OrderDetail.vue   # 订单详情
│   │   │   ├── Messages.vue      # 消息页面
│   │   │   ├── Payment.vue       # 支付页面
│   │   │   └── Dashboard.vue     # 数据仪表板
│   │   ├── components/           # 可复用组件
│   │   ├── services/             # API 服务
│   │   ├── stores/               # Pinia 状态管理
│   │   ├── utils/                # 工具函数
│   │   ├── App.vue
│   │   └── main.ts
│   ├── public/
│   ├── package.json
│   ├── vite.config.ts
│   ├── tsconfig.json
│   └── tailwind.config.js
│
├── backend/                       # Node.js + Express 后端
│   ├── src/
│   │   ├── controllers/          # 业务逻辑
│   │   ├── models/               # 数据模型
│   │   ├── routes/               # API 路由
│   │   ├── middleware/           # 中间件
│   │   ├── services/             # 业务服务
│   │   ├── utils/                # 工具函数
│   │   ├── security/             # 安全模块
│   │   ├── websocket/            # WebSocket 处理
│   │   ├── config/               # 配置文件
│   │   └── index.ts              # 服务器入口
│   ├── package.json
│   ├── tsconfig.json
│   ├── .env.example
│   └── .env.production
│
├── cloudflare-workers/            # Cloudflare Workers API 网关
│   ├── src/
│   │   ├── index.ts              # 主入口
│   │   ├── handlers/             # 请求处理器
│   │   ├── middleware/           # 中间件
│   │   └── utils/                # 工具函数
│   ├── wrangler.toml             # Cloudflare 配置
│   └── package.json
│
├── database/                      # 数据库配置
│   ├── mongodb/
│   │   ├── schemas/              # MongoDB Schema
│   │   ├── migrations/           # 数据迁移脚本
│   │   └── indexes.js            # 索引配置
│   ├── redis/
│   │   └── config.js             # Redis 配置
│   └── init.js                   # 初始化脚本
│
├── security/                      # 安全模块
│   ├── encryption.ts             # AES-256 加密
│   ├── jwt.ts                    # JWT 认证
│   ├── rateLimit.ts              # 速率限制
│   ├── audit.ts                  # 审计日志
│   └── riskControl.ts            # 风险控制引擎
│
├── docs/                          # 文档
│   ├── API.md                    # API 文档
│   ├── DEPLOYMENT.md             # 部署指南
│   ├── SECURITY.md               # 安全指南
│   ├── DATABASE.md               # 数据库设计
│   └── ARCHITECTURE.md           # 架构设计
│
├── .github/workflows/             # GitHub Actions CI/CD
│   ├── test.yml
│   ├── deploy.yml
│   └── security-scan.yml
│
├── docker-compose.yml            # Docker 配置
├── Dockerfile
├── .env.example
├── .gitignore
└── package.json (root)
```

---

## 🚀 快速开始

### 前置要求
- Node.js 18+
- MongoDB 5.0+
- Redis 6.0+
- Cloudflare 账户

### 1. 克隆项目
```bash
git clone https://github.com/meme0091w-arch/Can-no-day.git
cd Can-no-day
```

### 2. 安装依赖
```bash
# 安装 root 依赖
npm install

# 安装后端依赖
cd backend && npm install

# 安装前端依赖
cd ../frontend && npm install

# 安装 Cloudflare Workers 依赖
cd ../cloudflare-workers && npm install
```

### 3. 配置环境变量
```bash
# 后端配置
cp backend/.env.example backend/.env.production
# 编辑 backend/.env.production，填入你的配置

# 前端配置
cp frontend/.env.example frontend/.env.production
```

### 4. 初始化数据库
```bash
npm run db:init
npm run db:migrate
```

### 5. 启动开发服务器
```bash
# 启动后端
npm run backend:dev

# 在另一个终端启动前端
npm run frontend:dev

# 在另一个终端启动 Cloudflare Workers
npm run workers:dev
```

访问 `http://localhost:5173` 开始使用！

---

## 🔐 安全特性

- **端到端加密**：所有敏感数据采用 AES-256 加密
- **JWT 认证**：使用 RS256 算法签名
- **速率限制**：防止暴力破解和 DDoS 攻击
- **XSS/CSRF 防护**：使用 CSP 和 CSRF 令牌
- **审计日志**：记录所有敏感操作
- **风险控制**：异常交易检测和自动冻结机制
- **黑名单管理**：自动封禁恶意用户
- **IP 白名单**：支持 IP 限制

---

## 📚 API 文档

详见 [API 文档](./docs/API.md)

主要端点：
- `POST /api/auth/register` - 用户注册
- `POST /api/auth/login` - 用户登录
- `GET /api/tasks` - 获取任务列表
- `POST /api/tasks` - 发布新任务
- `POST /api/orders/bid` - 投标/应聘
- `WS /ws/messages` - WebSocket 消息连接
- `POST /api/payments` - 发起支付
- `GET /api/user/profile` - 获取用户档案

---

## 🌐 Cloudflare 集成

该项目配置了 Cloudflare Workers 作为 API 网关：

- 全球 CDN 加速
- 自动缓存优化
- DDoS 防护
- WAF 规则
- 自定义域名支持

详见 [部署指南](./docs/DEPLOYMENT.md)

---

## 💳 支付集成

支持多种支付方式：
- 🇨🇳 支付宝 (Alipay)
- 🇨🇳 微信支付 (WeChat Pay)
- 💳 Stripe (国际信用卡)
- 💰 PayPal

---

## 📊 数据分析

内置仪表板提供：
- 日/周/月收入统计
- 接单成功率分析
- 用户行为热力图
- 实时在线用户数
- 平均响应时间

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

## 📄 许可证

MIT License

---

## 📞 支持

- 📧 邮箱：support@game-task-platform.com
- 💬 微信：scan_qr_code_here
- 📱 小红书：@game-task-platform

---

**祝你使用愉快！** 🚀
