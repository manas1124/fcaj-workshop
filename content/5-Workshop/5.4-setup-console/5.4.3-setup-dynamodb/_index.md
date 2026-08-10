---
title: "5.4.3 Setup DynamoDB | Setup DynamoDB"
date: 2026-08-09
draft: false
weight: 543
---

# 5.4.3. Setup DynamoDB
## 5.4.3. Setup DynamoDB

### Tiếng Việt

Tạo 8 bảng DynamoDB để lưu trữ dữ liệu hệ thống. SAM template chỉ gán quyền (`DynamoDBCrudPolicy`) nhưng **không tự tạo bảng**.

**Trên AWS Console:**

1. Truy cập **DynamoDB → Tables → Create table**
2. Lặp lại cho 8 bảng sau:

| STT | Table Name | Partition Key | Billing Mode |
|-----|-----------|---------------|--------------|
| 1 | `smart-campus-users` | `pk` (String) | On-demand |
| 2 | `smart-campus-faces` | `pk` (String) | On-demand |
| 3 | `smart-campus-attendance` | `pk` (String) | On-demand |
| 4 | `smart-campus-leaves` | `pk` (String) | On-demand |
| 5 | `smart-campus-holidays` | `pk` (String) | On-demand |
| 6 | `smart-campus-tasks` | `pk` (String) | On-demand |
| 7 | `smart-campus-notifications` | `pk` (String) | On-demand |
| 8 | `smart-campus-security` | `pk` (String) | On-demand |

**Cách tạo mỗi bảng:**

- Table name: nhập tên từ bảng trên
- Partition key: `pk` — Type: `String`
- **Table settings:** Custom settings
- **Capacity mode:** On-demand
- **Create table**

### English

Create 8 DynamoDB tables for system data storage. The SAM template only assigns permissions (`DynamoDBCrudPolicy`) but **does not create tables**.

**On AWS Console:**

1. Go to **DynamoDB → Tables → Create table**
2. Repeat for the following 8 tables:

| No. | Table Name | Partition Key | Billing Mode |
|-----|-----------|---------------|--------------|
| 1 | `smart-campus-users` | `pk` (String) | On-demand |
| 2 | `smart-campus-faces` | `pk` (String) | On-demand |
| 3 | `smart-campus-attendance` | `pk` (String) | On-demand |
| 4 | `smart-campus-leaves` | `pk` (String) | On-demand |
| 5 | `smart-campus-holidays` | `pk` (String) | On-demand |
| 6 | `smart-campus-tasks` | `pk` (String) | On-demand |
| 7 | `smart-campus-notifications` | `pk` (String) | On-demand |
| 8 | `smart-campus-security` | `pk` (String) | On-demand |

**How to create each table:**

- Table name: enter from the table above
- Partition key: `pk` — Type: `String`
- **Table settings:** Custom settings
- **Capacity mode:** On-demand
- **Create table**

<!-- [SCREENSHOT: AWS Console → DynamoDB → Tables → hiển thị 8 bảng với trạng thái Active] -->
<!-- [SCREENSHOT: AWS Console → DynamoDB → Tables → showing 8 tables with Active status] -->
