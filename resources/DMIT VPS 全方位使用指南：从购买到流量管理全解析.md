# DMIT VPS 全方位使用指南：从购买到流量管理全解析

DMIT 全新升级的管理后台 UI 设计让 VPS 管理变得更加便捷，无论是重装系统、设置 root 密码、上传密钥，还是查看流量计费、取消服务器续费等操作都能轻松完成。本文将详细介绍 VPS 购买后的各项管理功能。

## 一、DMIT VPS 购买指南
👉 [【点击查看】2025年最新 DMIT 优惠码及特价云服务器方案汇总](https://bit.ly/dmit_coupon)

## 二、流量计费策略详解

DMIT 对 HKG.T1 和 SJC.T1 套餐实施了全新的流量计费策略，采用单向取最大值计算方式：

- 仅计量 MAX(IN, OUT)
- 系统会分别统计流入和流出流量
- 流量统计将取两者中的最大值
- UI 界面会同步更新显示最新数据

**不同套餐的计费方式对比：**

1. **PVM.HKG.T1.STARTER 套餐**
   - 单向流量计费
   - 超量后自动降速

2. **PVM.LAX.sPro.CREATOR 套餐**
   - 双向流量计费
   - 超量后服务暂停

3. **PVM.HKG.Pro 套餐**
   - 双向计费模式
   - 超量后服务暂停

## 三、SSH 密钥登录与 Root 密码设置

### 密钥登录配置
- 支持自行配置密钥登录
- 可替代传统 SSH 密钥登录方式

### Root 密码设置指南
**重要提示：**
- Root 密码默认仅用于访问控制台
- 如需 SSH 访问，需修改系统配置
- 更改密码后需完成电源生命周期（关机→开机）才能生效

**设置方法（Debian 11 系统）：**

**方法1：命令行快速设置**
bash
passwd # 设置密码
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo service sshd restart
reboot # 重启服务器

**方法2：手动配置文件**
1. 使用 root 身份登录
2. 执行 `passwd` 设置 root 密码
3. 编辑 `/etc/ssh/sshd_config` 文件
4. 确保包含以下配置：
   
   PermitRootLogin yes
   PasswordAuthentication yes
   
5. 执行 `reboot` 重启服务器

## 四、快照功能使用
DMIT 提供1个免费快照功能，可用于系统备份和恢复。

## 五、系统重装指南
DMIT 后台提供全面的操作系统选择，支持一键重装：
- 多种 Linux 发行版可选
- 操作简单直观

## 六、账单续费管理
在管理后台可轻松完成：
- 查看账单详情
- 续费服务
- 取消自动续费

## 七、洛杉矶 PVM.LAX.Pro 套餐特色
- **网络线路优势：**
  - 电信去程：GIA(AS4809)
  - 联通去程：直连 AS4837
  - 移动去程：香港移动(AS58453)
  - 三网回程：GIA(AS4809)

如需了解更多 DMIT 产品特性和最新优惠，请访问：
👉 [【点击查看】2025年最新 DMIT 优惠码及特价云服务器方案汇总](https://bit.ly/dmit_coupon)