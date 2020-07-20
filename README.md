# 构建和上传 release assets

这个 action 是用来自动将push的 branch 向某个分支进行提 PR

## 约定条件

#### 分支 命名规范
格式：pr_${BRANCH_TO}_other
说明：分支必须以 pr_开头，后面是向 某个分支发起的PR请求分支, 最后是其他名字

注意这里需要使用 ACCE


## Inputs
无

## Example usage

```yaml
on:
  push:
    branches:
      - pr_*


name: Auto add PR label

jobs:
  add_pr_labels:
    name: Auto add pull request labels if need
    runs-on: ubuntu-latest
    steps:
      - name: Add labels
        uses: jumpserver/action-auto-pr-branch@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
