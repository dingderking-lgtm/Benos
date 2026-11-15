# Benos · AI 网站设计与 CMS 托管平台 — 交付包

本仓库保存 2026-11-15 的完整源码交付包。解压后即是可直接构建的产品源码（前端 + 后端 + 迁移 + 测试 + 文档）。

| 项 | 值 |
| --- | --- |
| 文件 | `benos-project-2026-11-15-grammar.zip` |
| 大小 | 37.4 MB |
| 文件数 | 1084 |
| SHA256 | `a1f51f0f37086b78b1a6ae02d6e7f51cd82d1025c3a1ca22ec14e7ef403260f5` |

## 解压后

包内 `SHA256SUMS.txt` 列出每个文件的哈希，可逐个核对。

```
benos-project-2026-11-15-grammar/
├─ README.md                 项目总览、本地运行与常用命令
├─ platform/                 后端（Cloudflare Worker + D1 + R2）
│  ├─ src/                   业务代码（含 src/design-system/grammar 版式语法引擎）
│  ├─ migrations/            D1 迁移（含 0071 语法审批台账）
│  ├─ tests/                 后端测试
│  ├─ scripts/               构建、打包、身份校验
│  └─ docs/                  交付与验收文档（本轮见 DELIVERY-2026-11-15-GRAMMAR.md）
└─ UI模板/                    前端（Next.js 静态导出 + 运行时样式/模块）
```

## 构建

```bash
cd UI模板 && npm ci
cd ../platform && npm ci
npm run db:local     # 应用本地 D1 迁移
npm run dev          # 构建前端并启动 127.0.0.1:4180
```

## 本轮内容

版式语法引擎（bnl-0）、13 行业 × 3 方向配色引擎、代码级审批模型、运营后台「语法引擎」页、DeepSeek 兼容修复、语法站点 AI 配图。详见 `platform/docs/DELIVERY-2026-11-15-GRAMMAR.md`。

## 注意

包内不含任何真实密钥、本地数据库、上传文件或依赖缓存；`.dev.vars` 只有示例文件，真实密钥需自行配置。
