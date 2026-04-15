# 🚀 Agile-PM-Workflow 部署手册 (Cursor 专属版)

本手册将指导你将敏捷 PM 工作流技能注入到 Cursor AI 中，使其能够通过斜杠指令 `/` 或 `@`唤醒，并引导你完成从需求采集到 PRD 产出的全过程。

---

## 🛠️ 第一阶段：获取源码 (全平台通用)

在你的电脑上创建一个合适的文件夹（如 `Developer` 文件夹），克隆本项目仓库。

1. 打开终端 (Mac) 或 PowerShell (Windows)。
   ```bash
   cd /Users/你的用户名/Developer
   ```
2. 执行以下命令：
   ```bash
   git clone https://github.com/chyxin071-sys/Agile-PM-Workflow.git
   ```

---

## 💻 第二阶段：MacOS 部署步骤（Windows用户跳过）

### 1. 确定路径 (核心提示)
*   **进入项目根目录**：你刚才克隆代码的文件夹，例如 `/Users/你的用户名/Developer/Agile-PM-Workflow`。
*   **Skills/Rules存放路径**：必须在项目根目录`Agile-PM-Workflow`下的 `.cursor/rules/` 文件夹中。

### 2. 执行部署
打开终端，依次运行：
```bash
# 进入项目目录
cd ~/路径/到/你的/Agile-PM-Workflow

# 创建项目专属的规则目录 (注意：.cursor 是隐藏文件夹)
mkdir -p .cursor/rules

# 将定义文件复制到规则目录，并重命名为 .mdc 格式
cp pm_workflow_template/pm_workflow_definition.md .cursor/rules/agile-pm.mdc
```

### 3. 配置元数据 (让斜杠指令生效)
在 Cursor 中的`Agile-PM-Workflow`下打开 `.cursor/rules/agile-pm.mdc`，并在文件 **最顶部** 插入/确认是否有以下已经定义好的内容：
```markdown
---
description: 开启敏捷产品经理工作流，引导需求采集、原型设计与 PRD 生成
globs: 
---

# 敏捷产品经理需求产出工作流

## 触发方式
当用户提供一个初步的想法或需求描述时，请严格按照以下**七个步骤**引导用户...
.....
```

---

## 🪟 第二阶段：Windows 部署步骤（Mac用户跳过）

### 1. 确定路径 (核心提示)
*   **项目根目录**：例如 `C:\Users\你的用户名\Developer\Agile-PM-Workflow`。
*   **注意**：Windows 的文件夹路径使用反斜杠 `\`，且 `.cursor` 文件夹在资源管理器中可能默认隐藏。

### 2. 执行部署
1. 进入 `Agile-PM-Workflow` 文件夹。
2. 在该目录下新建文件夹，命名为 `.cursor`，进入后再新建文件夹 `rules`。
3. 将 `pm_workflow_template` 目录下的 `pm_workflow_definition.md` 文件**复制**到 `.cursor\rules\` 文件夹中。
4. 将该文件重命名为 `agile-pm.mdc`。
```bash
# 1. 进入项目根目录 (请将 "你的用户名" 替换为实际名称)
cd C:\Users\你的用户名\Developer\Agile-PM-Workflow

# 2. 创建项目专属的规则目录 (Windows 会处理点开头的文件夹)
mkdir .cursor\rules

# 3. 将定义文件复制到规则目录，并直接重命名为 .mdc 格式
copy pm_workflow_template\pm_workflow_definition.md .cursor\rules\agile-pm.mdc

```
### 3. 配置元数据
在 Cursor 中的`Agile-PM-Workflow`下打开 `.cursor\rules\agile-pm.mdc`，并在文件 **最顶部** 插入或确认是否有以下已经定义好的内容：
```markdown
---
description: 开启敏捷产品经理工作流，引导需求采集、原型设计与 PRD 生成
globs: 
---

# 敏捷产品经理需求产出工作流

## 触发方式
当用户提供一个初步的想法或需求描述时，请严格按照以下**七个步骤**引导用户...
.....
```

---

## 🔍 第三阶段：验证与使用

### 1. 刷新索引
回到 Cursor 界面，按下 `Command + L` (Mac) 或 `Ctrl + L` (Win) 打开聊天窗口。

### 2. 唤醒技能
在聊天框中输入`/` 或者  **`@`**，确保 AI 读到了新规则。
*   **成功标志**：菜单中出现了名为 **`agile-pm`** 的选项。
*   **使用**：选中该选项，后面跟上你的想法（例如：`/agile-pm`为香港警队（HKPF）警署打造专属排队取号系统，包含5个部分市民取票终端、前台人员柜台终端、电视墙（TV Wall）显示屏、自助服务机（kiosk）及后台内容管理系统（CMS）管理终端，所有终端共用同一套取号后端及显示模板引擎。该系统支持通过电视盒子（TV Box）实现电视墙（TV Wall）显示（展示叫号号码），通过便携式触控显示器/平板搭配打印机（用于打印取号凭证）实现自助机应用（Kiosk App）取票功能，以及通过人员移动应用（Officer Mobile App）供警署人员操作队列及叫号。该系统可规范警署的排队取号流程，提高现场服务调度及后台管理效率，改善市民办事体验，减轻警务人员及运营人员的人工管理工作量。）。

---

## ⚠️ 重要注意事项 (必读)

1.  **文件后缀名**：必须是 **`.mdc`**。如果后缀是 `.md`，斜杠指令可能无法在菜单中弹出。
2.  **元数据位置**：顶部的 `---` 必须是文件的**第 1 行**，且前后不能有空格。
3.  **项目独立性**：此部署方式为“项目级部署”，该技能仅在你打开 `Agile-PM-Workflow` 文件夹时有效。如果你想在其他新项目中使用，只需将 `.cursor/rules` 文件夹整体复制到新项目的根目录下即可。
4.  **避免污染**：不要将此规则粘贴到 Cursor 的全局设置 (Rules for AI) 中，除非你希望在任何临时聊天（即使是写简单的 Python 脚本）时 AI 都以产品经理的口吻和你说话。

---

## 💡 故障排查

*   **输入 `/` 没反应？**
    *   尝试输入 `@` 然后选择 `Rules`，看是否有 `agile-pm`。
    *   检查路径是否正确：`.cursor` 文件夹必须在 Cursor 当前打开的文件夹的最外层。
*   **AI 还是不够聪明？**
    *   对话时记得点击 **`+ Codebase`**，让 AI 拥有整个项目的上下文感知能力。
