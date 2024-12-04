
## monorepo 环境

### 构建目录

monorepo 基于 pnpm

```shell
mkdir packages
mkdir react && cd react && pnpm init
mkdir react-dom && cd react-dom && pnpm init
mkdir react-reconciler && cd react-reconciler && pnpm init
mkdir scheduler && cd scheduler && pnpm init
mkdir shared && cd shared && pnpm init
```

新建 `pnpm-workspace.yaml`

```yaml
packages:
  - 'packages/*'
```

### 安装公共依赖

```shell
pnpm add vitest -Dw
```

### 共享项目内repo

安装 `shared` 给 `scheduler` 使用

```shell
pnpm add shared --filter scheduler
```

## demo 环境

基于vite，`pnpm create vite 目录名 --template 模板枚举`

```shell
pnpm create vite examples --template react-ts
cd examples
pnpm i
pnpm dev
```
