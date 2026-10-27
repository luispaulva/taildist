# taildist

**分析标签分布的长尾程度与影响。**

`taildist` —— 统计各类别样本量分布，给出长尾截断点与被忽略类别的规模

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`taildist.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install luispaulva-taildist
```

装完直接用命令名调用：

```bash
taildist --help
```

也可以不用安装，直接把 `taildist.py` 拷走用——它只依赖标准库。

## 为什么需要它

同时报告「长尾有多长」和「丢掉长尾会损失多少」

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 类别长尾分布 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python taildist.py --file input.txt
python taildist.py --text "示例内容"
python taildist.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分箱是等宽或等频，样本太少时结论不稳。
- 不做显著性检验。

## 跑测试

```bash
python test_taildist.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/luispaulva/taildist>

---

## 关于作者

luispaulva 做类别长尾分布相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://luispaulva.github.io>
- 仓库：<https://github.com/luispaulva/taildist>

## 许可

MIT，见 [LICENSE](LICENSE)。
