# learn-graphrag


[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Yoshida24/preset-python-venv)

Preset for development on Python using venv.

**included:**
- Lint and Format
- Task runner
- Env support

## Usage

depends on:
- Python: 3.11
- pip: 24.0
- GNU Make: 3.81

support:
- OS: M1 Macbook Air Sonoma 14.4


## Gettig Started

> ref. https://microsoft.github.io/graphrag/posts/get_started/

First of all, install VSCode recommended extensions. This includes Linter, Formatter, and so on. Recommendation settings is written on `.vscode/extensions.json`.

Then, make virtual env and activate it:

```bash
python -m venv .venv
. .venv/bin/activate
```

Install dependencies:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Init GraphRAG

```bash
python -m graphrag.index --init --root ./ragtest
```

## Build KnowledgeGraph

```
python -m graphrag.index --root ./ragtest
```

## Run Query

```bash
python -m graphrag.query \
--root ./ragtest \
--method global \
"この物語の登場人物同士の関係は？"
```

Output Example:

```markdown
### 登場人物同士の関係

#### メロスとセリヌンティウス
メロスとセリヌンティウスの関係は非常に深い友情に基づいています。セリヌンティウスがメロスの代わりに処刑される覚悟を示すことで、その友情の強さと高い道徳的価値が強調されています [Data: Reports (2)]。さらに、メロスがセリヌンティウスに自分を打つように頼む場面もあり、これにより彼らの絆と信頼が試されることが描かれています [Data: Reports (2)]。

#### ディオニスとセリヌンティウス
ディオニスとセリヌンティウスの関係は相互の尊敬と敬意に満ちています。ディオニスがセリヌンティウスをメロスの代わりとして受け入れることは、彼らの間の深い信頼と尊敬を示しています [Data: Reports (2)]。

#### メロスの妹とその夫、村人たち
メロスの妹とその夫、そして村人たちを含む広範なコミュニティも物語に関与しています。これにより、個人的な忠誠心と公共の利益の相互関係が強調されています [Data: Reports (1)]。

#### 王様とアレキス様
王様とアレキス様の関係は非常に緊張しています。王様がアレキス様を殺害したことで、王様の暴政とコミュニティに対する恐怖の支配が示されています [Data: Reports (0)]。

### 結論
この物語における登場人物同士の関係は、友情、尊敬、忠誠心、そして恐怖といった多様な感情と価値観に基づいています。これらの関係は、物語の進行とともにそれぞれのキャラクターの行動や決断に大きな影響を与えています。
```

## Run Query Local

```bash
python -m graphrag.query \
--root ./ragtest \
--method local \
"この物語の登場人物同士の関係は？"
```

## make via make

```markdown
# 登場人物同士の関係

## メロスとセリヌンティウス

メロスとセリヌンティウスの関係は、深い絆と信頼に基づいています。メロスはセリヌンティウスの処刑を防ぐために競走し、彼の全ての旅と苦労はセリヌンティウスを救うという彼のコミットメントによって動機付けられています。疑念の瞬間の後、二人は信頼を再確認するために身体的な交流を共有します。また、メロスはセリヌンティウスを訪ねる予定であり、セリヌンティウスはメロスの身代わりとして処刑されることに同意しました。これらの行動から、彼らの間には互いに対する深い信頼と献身があることが明らかです [Data: Relationships (1)]。

## メロスとディオニス

ディオニスとメロスは、複雑な関係を持つ二人の登場人物です。ディオニスは、メロスとセリヌンティウスに受け入れられることを望んでおり、これは彼の心の変化や真のつながりを求める願望を示しています。一方、メロスはディオニスに対して三日間の猶予を求め、ディオニスはこれを許可しました。しかし、メロスはディオニスの政治に反対し、彼の暴政から市を救うことを試みています。この情報から、ディオニスとメロスの間には、信頼と反目、そして理解を求める複雑なダイナミクスが存在することがわかります [Data: Relationships (3)]。

## メロスと妹

メロスは妹の結婚式の準備に深く関わっており、彼女の幸せと幸福を確保するために多大な努力を払っています。メロスが三日間の猶予を求めた理由は、特に妹が夫を得ることを確実にするためでした。これにより、彼の妹に対する強い家族愛と献身が示されています [Data: Relationships (5)]。

## メロスと花婿

メロスは妹の夫である花婿に妹と羊を託し、彼を弟として迎え入れます。この関係は、メロスが家族の一員として花婿を受け入れ、彼に対する信頼と期待を示しています [Data: Relationships (10)]。

## メロスとフィロストラトス

メロスとフィロストラトスの関係は、直接的な相互作用と相互影響によって特徴付けられます。フィロストラトスはセリヌンティウスの弟子であり、最初はメロスを止めようとしますが、最終的にはセリヌンティウスを救うためにメロスに従います。この行動は、メロスのリーダーシップと信頼を示しています [Data: Relationships (14)]。

## メロスと村の人たち

メロスは村の人々に結婚式の知らせを伝える計画を立てており、これにより彼がコミュニティに深く関わっていることが示されています。彼の行動は、個人的な義務とコミュニティへの貢献の両方を強調しています [Data: Relationships (8)]。

## 王様とアレキス様

王様はアレキス様を殺害したとされており、この行動は王様の暴虐さと権力維持のための冷酷さを示しています。アレキス様の死は、コミュニティに大きな影響を与え、王様の恐怖政治を強調しています [Data: Relationships (17)]。

これらの関係は、物語の登場人物同士の複雑な相互作用と深い絆を浮き彫りにしています。各キャラクターの行動と動機は、彼らの関係性によって大きく影響されており、物語全体のテーマである忠誠、信頼、そして正義の追求を強調しています。
```

You can run script via `make`:

```bash
# load environment variables from .env to your shell.
set -a && source ./.env && set +a
make run
```

> **Note**
>
> This project *does not* depends on `dotenv-python`. Instead, using below script.
> `set -a && source ./.env && set +a`

## Jupyter

```bash
jupyter lab
```

## Develop App
On usual develop, first you activate `venv` first like below.

```bash
source .venv/bin/activate
```

Save requirements:

```bash
pip freeze > requirements.txt
```

Deactivate venv:

```bash
deactivate
```
