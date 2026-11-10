# muse

Sun518-ai 的 monorepo：把账号下的仓库以 git 子模块关联进来，各仓库仍独立维护，这里只做统一入口与版本锁定。

## 包含

| 目录 | 来源 | 说明 |
| --- | --- | --- |
| `paipai/` | 自有 | 派派的 Next.js 全栈项目 |
| `paipai-cli/` | 自有 | |
| `starup/` | 自有 | |
| `neural-atelier/` | fork | 3D 连线解谜游戏：搭神经网络、看向量流动、探索端侧推理，25 关，中英双语 |
| `dsh-superagent-prototype/` | fork | 更自主的 Agent 系统原型 |
| `todomvc/` | fork | 各前端框架的 Todo 示例 |

## 用法

```bash
# 连同子模块一起 clone
git clone --recurse-submodules https://github.com/Sun518-ai/muse.git

# 只 clone 了主仓库时，补拉子模块
git submodule update --init --recursive

# 把某个子模块更新到它 main 分支的最新提交
git submodule update --remote paipai
```

## 说明

- 子模块指向各仓库的默认分支；muse 只锁定 commit，不改仓库本身。
- 想拿掉哪个：`git submodule deinit <目录>` 再 `git rm <目录>`，提交即可。
