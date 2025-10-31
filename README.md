# Scaffold_Structure_Virtual_Env

# 📝 Python 项目脚手架 (Project Scaffold) 设置指南 (Git + Cloud + Virtual Env)

This note summarizes the steps to set up a basic, well-structured Python project using Git, GitHub, and a virtual environment, complete with linting, formatting, and testing tools.

## 🚀 Step-by-Step Instructions (分步操作指南)

| 步骤 (Step) | 动作 (Action) | 目的 (Purpose) | 命令 (Command) |
| :--- | :--- | :--- | :--- |
| **1. 创建 Git 仓库** | **Create GitHub Repository** | 在 GitHub 上创建项目仓库，包含 **`README`** 和默认 **Python `.gitignore`** 文件。 | N/A (在 GitHub 网页操作) |
| **2. 设置 SSH Key** | **Set up SSH Keys** | 生成 SSH 密钥对，并将公钥 (Public Key) 上传到 GitHub，以实现安全且免密连接。 | `ssh-keygen -t rsa` <br> `cat ~/.ssh/id_rsa.pub` |
| **3. 克隆仓库** | **Clone Repository** | 将远程 GitHub 仓库克隆到本地环境 (e.g., Cloud9)。 | `git clone git@github.com:USER/scaffold.git` |
| **4. 创建初始文件** | **Create Initial Files** | 在项目目录中创建必要的骨架文件。 | `cd scaffold`<br>`touch Makefile`<br>`touch hello.py`<br>`touch test_hello.py`<br>`touch requirements.txt` |
| **5. 创建虚拟环境** | **Create Virtual Environment** | 使用 `venv` 模块在主目录 (`~`) 下创建隐藏的虚拟环境，与项目同名 (`.scaffold`)。 | `python3 -m venv ~/.scaffold` |
| **6. 激活虚拟环境** | **Activate Virtual Environment** | 激活隔离环境，确保所有包安装在该项目环境中。 | `source ~/.scaffold/bin/activate` |
| **7. 填写 `requirements.txt`** | **Fill `requirements.txt`** | 添加项目所需的开发和测试库 (e.g., `pylint`, `pytest`, `click`, `black`, `pytest-cov`)。 | N/A (编辑文件) |
| **8. 编写 `Makefile`** | **Write `Makefile`** | 编写 `Makefile`，定义常用任务（如 `install`, `format`, `lint`, `test`, `all`），简化工作流程。 **(注意：使用 Tab 键)** | N/A (编辑文件) |
| **9. 安装依赖** | **Install Dependencies** | 执行安装命令，升级 `pip` 并安装 `requirements.txt` 中的所有依赖。 | `make install` |
| **10. 编写代码 (Hello)** | **Write Initial Code** | 编写基础代码 (e.g., `hello.py` 中的 `add` 函数) 以供后续测试。 | N/A (编辑 `hello.py`) |
| **11. 运行 Lint** | **Run Linting** | 使用 `make lint` 运行 `pylint` 检查代码质量和潜在错误。 | `make lint` |
| **12. 运行 Format** | **Run Formatting** | 使用 `make format` 运行 `black` 自动格式化代码，统一代码风格。 | `make format` |
| **13. 编写测试** | **Write Tests** | 编写测试文件 (`test_hello.py`)，导入函数并使用 `assert` 进行断言测试。 | N/A (编辑 `test_hello.py`) |
| **14. 运行测试** | **Run Tests** | 执行测试命令，运行 `pytest` 并获取测试覆盖率。 | `make test` |
| **15. 运行全部任务** | **Run All Tasks** | 运行 `make all` 一次性执行 `install`, `lint`, 和 `test` (根据 `Makefile` 配置)。 | `make all` |
| **16. 暂存和提交** | **Stage and Commit** | 暂存所有新建/修改的文件，并提交到本地 Git 历史记录。 | `git status`<br>`git add *`<br>`git commit -m "Adding initial structure"` |
| **17. 推送到 GitHub** | **Push to GitHub** | 将本地提交推送到远程 GitHub 仓库。 | `git push` |

-----

## 🛠️ Key Tools & Concepts (关键工具与概念)

  * **Virtual Environment (虚拟环境)**: 隔离项目依赖，防止包冲突。 (Command: `python3 -m venv`)
  * **`requirements.txt`**: 列出项目所需的所有 Python 库。
  * **`Makefile`**: 用于自动化项目任务的脚本，通过 `make` 命令执行。
  * **`pip install --upgrade pip`**: 确保使用最新版本的 `pip`。
  * **`black` (Formatting)**: 自动格式化工具，保持代码风格一致。 (`make format`)
  * **`pylint` (Linting)**: 静态代码分析工具，检查代码质量和错误。 (`make lint`)
  * **`pytest` (Testing)**: 强大的测试框架，支持简单的 `assert` 语句。 (`make test`)
  * **`pytest-cov` (Coverage)**: 报告测试覆盖率。
