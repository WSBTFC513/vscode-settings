# vscode-settings

## 目次

- [目次](#目次)
- [拡張機能](#拡張機能)
   - [全リポジトリに入れるべき拡張機能(Linter, Formatter)](#全リポジトリに入れるべき拡張機能linter-formatter)
      - [EditorConfig](#editorconfig)
      - [Code Spell Checker](#code-spell-checker)
      - [Markdown All in One](#markdown-all-in-one)
      - [markdownlint](#markdownlint)
      - [YAML](#yaml)
      - [Docker](#docker)
   - [必須ではないが効率化につながる拡張機能(重要度:高)](#必須ではないが効率化につながる拡張機能重要度高)
      - [DotENV](#dotenv)
      - [ErrorLens](#errorlens)
      - [indent-rainbow](#indent-rainbow)
      - [Markdown Preview Enhanced](#markdown-preview-enhanced)
      - [Mermaid Markdown Syntax Highlighting](#mermaid-markdown-syntax-highlighting)
      - [Log File Highlighter](#log-file-highlighter)
      - [Path Intellisense](#path-intellisense)
      - [PlantUML](#plantuml)
      - [vscode-icons](#vscode-icons)
      - [Night Owl](#night-owl)
      - [Code Runner](#code-runner)
   - [必須ではないが効率化につながる拡張機能(重要度:中)](#必須ではないが効率化につながる拡張機能重要度中)
      - [IntelliCode](#intellicode)
         - [IntelliCode API Usage Examples](#intellicode-api-usage-examples)
      - [Japanese Language Pack for Visual Studio Code](#japanese-language-pack-for-visual-studio-code)
      - [Markdown PDF](#markdown-pdf)
      - [Output Colorizer](#output-colorizer)
      - [Partial Diff](#partial-diff)
      - [Rainbow CSV](#rainbow-csv)
      - [Regex Previewer](#regex-previewer)
      - [TODO Highlight](#todo-highlight)
   - [リモート関係の拡張機能(分類が特殊なため別枠)](#リモート関係の拡張機能分類が特殊なため別枠)
      - [Remote Development](#remote-development)
         - [WSL](#wsl)
         - [Dev Containers](#dev-containers)
         - [Remote - SSH](#remote---ssh)
            - [Remote - SSH: Editing Configuration Files](#remote---ssh-editing-configuration-files)
            - [Remote Explorer](#remote-explorer)
         - [Remote - Tunnels](#remote---tunnels)
   - [Web系()](#web系)
      - [Auto Rename Tag](#auto-rename-tag)
      - [CSS Peek](#css-peek)
      - [Highlight Matching Tag](#highlight-matching-tag)
      - [HTML CSS Support](#html-css-support)
      - [Live Server](#live-server)
      - [JavaScript (ES6) code snippets](#javascript-es6-code-snippets)
      - [npm Intellisense](#npm-intellisense)
   - [Web系(Linter, Formatter)](#web系linter-formatter)
      - [Microsoft Edge Tools for VS Code](#microsoft-edge-tools-for-vs-code)
      - [Stylelint](#stylelint)
      - [ESLint](#eslint)
      - [Prettier](#prettier)
   - [Terraform](#terraform)
      - [HashiCorp Terraform](#hashicorp-terraform)

## 拡張機能

### 全リポジトリに入れるべき拡張機能(Linter, Formatter)

システムに関わらずほぼ確実に利用されるか利用頻度の高い要素の拡張機能において、Linter及びFormatterに該当するもの。

関連する設定はワークスペースの`settings.json`に記述して、`extensions.json`で推奨しておくことも忘れずに。

```bash
code --install-extension editorconfig.editorconfig --install-extension streetsidesoftware.code-spell-checker --install-extension yzhang.markdown-all-in-one --install-extension davidanson.vscode-markdownlint --install-extension redhat.vscode-yaml --install-extension ms-azuretools.vscode-docker
```

#### EditorConfig

エディタを跨いで統一される設定を記述可能。設定項目は少ないが基礎的なものが揃っている。

- end_of_line
   - 改行コード
- charset
   - 文字コード(vscodeは未対応なので、settings.jsonでカバーすること)
- indent_style
   - インデントをSpaceで行うかTabで行うか
- indent_size
   - インデントのサイズ
- trim_trailing_whitespace
   - 行末の空白を削除
- insert_final_newline
   - ファイル末尾に空白行を追加
- tab_width
   - タブキーのサイズ(無い場合indent_sizeを基準にタブキーが動作するので基本的には設定する必要は無い)

#### Code Spell Checker

英語のスペルミスを青い波線で教えてくれる。

`settings.json`に記述することで固有名詞などを除外することも可能。

```json
{
  "cSpell.words": [
    "固有名詞1",
    "固有名詞2",
  ],
}
```

#### Markdown All in One

`TOC(目次)作成`や`見出しの自動ナンバリング`や`リンクの自動補完`などを行ってくれる。

#### markdownlint

Markdownの静的解析。

#### YAML

YAMLファイルのフォーマットや入力補完を行える。Kubernetesプロジェクトでは少し設定を変えてあげる必要があるので注意。

#### Docker

`Dockerfile`や`docker-compose.yml`のフォーマットや入力補完、`GUIでのDockerコンテンツ操作`などが可能になる。

### 必須ではないが効率化につながる拡張機能(重要度:高)

システムに関わらずVSCode全般の作業において利便性が向上する拡張機能。

```bash
code --install-extension mikestead.dotenv --install-extension usernamehw.errorlens --install-extension oderwat.indent-rainbow --install-extension shd101wyy.markdown-preview-enhanced --install-extension bpruitt-goddard.mermaid-markdown-syntax-highlighting --install-extension emilast.LogFileHighlighter --install-extension christian-kohler.path-intellisense --install-extension jebbs.plantuml --install-extension vscode-icons-team.vscode-icons --install-extension sdras.night-owl --install-extension formulahendry.code-runner
```

#### DotENV

`.env`に色がついて見やすくなる。

#### ErrorLens

エラー内容がインラインで自動表示されるようになる。

#### indent-rainbow

インデントに色を付けて見やすくする。

#### Markdown Preview Enhanced

Markdownをプレビューする拡張機能。これを用いると`PlantUML`や`Mermaid`もプレビュー可能になる。

#### Mermaid Markdown Syntax Highlighting

Markdown内のMermaid記法がハイライト表示される。

#### Log File Highlighter

logファイルをハイライト表示して見やすくする。

#### Path Intellisense

ファイルパスの入力補完を行う。JavaScriptやTypeScriptで用いる場合は、`settings.json`でデフォルトのサジェスト機能をOFFにする。

```json
{
  "javascript.suggest.paths": false,
  "typescript.suggest.paths": false,
}
```

#### PlantUML

PlantUMLのハイライト、スニペット、VSCode上での生成などの機能を持つ。基本的には`Graphviz`がインストールされている環境でないと描画できない図が多い。

#### vscode-icons

vscodeのファイルやフォルダにアイコンを付けてファイルの種別を分かりやすくする。

#### Night Owl

vscodeのカラーテーマ。最終的には好みなんですが、目に優しく且つ色覚異常まで考えられた配色になっているので、こだわりが無いのであれば採用すると良いでしょう。イタリック調を含まないようにするかどうかは完全に好み。

```json
{
  "workbench.colorTheme": "Night Owl",
}
```

#### Code Runner

プログラムを簡易的に実行可能な拡張機能。デバッグにうれしい。広範囲の言語に対応しています。

### 必須ではないが効率化につながる拡張機能(重要度:中)

必須とまではいかないが入れておいて損のない拡張機能。入れないとしたら、どうしてもストレージ容量が足りない場合くらいか。

```bash
code --install-extension VisualStudioExptTeam.vscodeintellicode --install-extension MS-CEINTL.vscode-language-pack-ja --install-extension yzane.markdown-pdf --install-extension IBM.output-colorizer --install-extension ryu1kn.partial-diff --install-extension mechatroner.rainbow-csv --install-extension chrmarti.regex --install-extension wayou.vscode-todo-highlight
```

#### IntelliCode

`JavaScript`, `TypeScript`, `Python`, `Java`. `T-SQL`の入力補完を行う拡張機能。

対象のSampleをGitHubから持ってきてくれる機能も持つ。

##### IntelliCode API Usage Examples

対象のSampleをGitHubから持ってきてくれる機能のAPI版。

#### Japanese Language Pack for Visual Studio Code

日本語化する。コマンドパレットからLanguageを変更しないといけない場合もある。

#### Markdown PDF

Markdownで高精度なPDF出力が可能になる。

#### Output Colorizer

出力ウインドウに色を付けて見やすくする。

#### Partial Diff

選択2箇所やクリップボードなどを用いて、差分確認ができる機能。

#### Rainbow CSV

CSVファイルに色を付けて見やすくする。

#### Regex Previewer

正規表現のプレビューを表示することができる機能。

#### TODO Highlight

ToDoをハイライト表示して分かりやすくする。

### リモート関係の拡張機能(分類が特殊なため別枠)

OS環境により必須のものが変わるので、インストール方法に注意。（消せばいいんだけども）

#### Remote Development

リモート接続に関する拡張機能4つ(更に2つの拡張機能が付いてくるので合計6つ)をまとめてインストールできる。

Windowsの場合はこれ1つをインストールすればOK。

```bash
code --install-extension ms-vscode-remote.vscode-remote-extensionpack
```

Linux等では、WSL以外をインストールすると良い。

```bash
code --install-extension ms-vscode-remote.remote-containers --install-extension ms-vscode-remote.remote-ssh --install-extension ms-vscode.remote-server
```

##### WSL

WSL環境でのVSCode利用がスムーズになる。Windows以外のOSでは不要。

##### Dev Containers

Docker等のコンテナ環境でVSCodeを利用できるようなる。

##### Remote - SSH

SSH接続先の環境をVSCodeを利用できるようなる。

###### Remote - SSH: Editing Configuration Files

Remote SSH 用の設定ファイル作成時に入力補完される。

Remote SSH をインストールすると付いてくる。

###### Remote Explorer

Remote SSH や Remote Tunnels で接続可能なリモートマシンのリストを表示するViewとなる。

Remote SSH か Remote Tunnels をインストールすると付いてくる。

##### Remote - Tunnels

トンネル接続先の環境をVSCodeを利用できるようなる。

### Web系()

`HTML`, `CSS`, `JavaScript`でフレームワークに依存しないものをカテゴライズします。有力なものでも入力補完を行う`IntelliCode`と`Path Intellisense`の拡張機能は、全般的なやつで紹介済みです。（他の言語でも効くため）

```bash
code --install-extension formulahendry.auto-rename-tag --install-extension pranaygp.vscode-css-peek --install-extension vincaslt.highlight-matching-tag --install-extension ecmel.vscode-html-css --install-extension ritwickdey.LiveServer --install-extension xabikos.JavaScriptSnippets --install-extension christian-kohler.npm-intellisense
```

#### Auto Rename Tag

HTMLタグの片方をリネームすると対応したもう片方のタグも同時にリネームされる。

#### CSS Peek

CSSとHTMLの関連づけを行ってくれる。HTMLコード内でCSSの該当情報を確認したり、F12で飛んだりできる。

#### Highlight Matching Tag

HTMLタグを選択するともう片方を含めてハイライト表示される。

#### HTML CSS Support

HTMLとCSSの`idやclassの入力補完`、`Validate`などを行ってくれる。

#### Live Server

vscodeでローカルホストサーバを即席で作り、HTMLの内容をリアルタイムで表示できる。

#### JavaScript (ES6) code snippets

JavaScriptやTypeScriptの入力補完が利くようになる。

#### npm Intellisense

npmの入力補完が効くようになる。

### Web系(Linter, Formatter)

```bash
code --install-extension ms-edgedevtools.vscode-edge-devtools --install-extension stylelint.vscode-stylelint --install-extension dbaeumer.vscode-eslint --install-extension esbenp.prettier-vscode
```



有効にする場合は、`settings.json`で以下の設定を記述して、ビルトインのValidateを解除する。これはユーザー設定に書くとStylelintの無い状態で完全にValidateがかからなくなるのでワークスペース内のみに書くこと。

```json
{
  "css.validate": false,
  "less.validate": false,
  "scss.validate": false,
}
```

#### Microsoft Edge Tools for VS Code

vscode上でEdgeが開ける他、HTMLのLinter効果(webhint)もある。CSSのStylelintやJavaScriptのESLintと異なり、ライブラリとしてインストールされたものを参照するわけではないので、CI/CDとバージョンが合わない等で困る場合はsettings.jsonから`"vscode-edge-devtools.webhint": false`で設定を切ってしまうか`.hintrc`で除外してしまう。

#### Stylelint

CSSのLinterとなる。拡張機能だけで動くことは無く、ワークスペースにStylelintがインストールされているかを確認して自動でVSCodeと連携してくれる。（ちなみにワークスペースに無い場合はグローバルも探してくれる）



#### ESLint

JavaScriptやTypeScriptのLinterとなる。

#### Prettier

Web系ファイルの総合的なFormatter。





### Terraform

```bash
code --install-extension hashicorp.terraform
```

#### HashiCorp Terraform

Terraformの`Validate`、`Format`、`IntelliSense`、`Syntax highlighting`、`Code Snippets`などが行える。
