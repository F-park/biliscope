首先，感谢你愿意为`biliscope`做出贡献！

## 贡献代码之前

如果你有改动多行以上代码的想法，我建议你先提交一个`issue`（议题），来谈谈你想要实现的东西。在你投入太多精力之前，我们应该讨论一下你的这个修改是否合适。

你还需要安装`pre-commit`钩子，来检查你的提交没有一些细节上的问题。

```
// 电脑没有python环境的话请先安装python
pip install pre-commit
pre-commit install
```

## 代码风格

### `javaScript`文件

```js
function main(args) {
    if (!args) {
        return -1;
    }
}
```

- 语句末尾使用分号
- `if`/`for`/`while`语句与`(`空一格
- `)`与`{`空一格且不新开一行

### 其他文件

- 在文件末尾新开一行
- 行尾没有多余的空格

## 贡献代码

> [TIP]
> 如果你还不会使用`git`，建议你观看[这个视频](https://www.bilibili.com/video/BV19e4y1q7JJ/)。

### 克隆代码到本地

你需要`fork`（复刻）此项目，然后创建一个新的功能分支。

```
git clone https://github.com/<你的用户名>/biliscope.git
cd biliscope
git checkout -b <功能分支的名字>
```

### 测试

#### 常规测试

1. 打开浏览器的[扩展](chrome://extensions/)界面
2. 打开开发人员模式
3. 点击`加载解压缩的扩展`按钮，选择`biliscope`文件夹
4. 禁用在浏览器扩展市场安装的`biliscope`
5. 打开[B站](https://www.bilibili.com/)，验证你所完成的功能

#### `github actions`

> [TIP]
> 在测试前先`commit`你当前的修改，但不要`push`，测试成功后，再`checkout`回当前分支`push`。

1. 创建一个测试分支`test_ci_<要测试的ci名>`
2. 向待测试文件中的`on.push.branches`追加`test_ci_*`
3. `push`这个测试分支
4. 在你`fork`的远程仓库中查看测试结果。
5. 删掉这个测试分支（可选）

---

如果你的电脑有`docker`环境，可以使用[act](https://github.com/nektos/act)在本地进行测试。

### 发起`Pull Request`（拉取请求）

你需要向`gaogaotiantian/viztracer`的`master`分支发起一个`Pull Request`（拉取请求），我会尽快审查代码并给予反馈。
