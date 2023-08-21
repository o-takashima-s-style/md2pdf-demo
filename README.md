# md2pdf-demo

## これは何

コミットされたMarkdownをPDFにビルドしてArtifactsにアップロードします。

## 使い方

### PDFをビルドするコンテナイメージをビルド

※この作業を初回コンテナイメージが1つも作成されていない時だけでOK

Actions > build pandoc container > Run workflow に移動してRun workflowを実行する。

### PDFをビルド

`Chapter`プレフィックスのファイルをコミットすると自動でPDFがビルドされる。ビルドされたPDFは Actions > pandoc > 実行されたジョブを開くとArtifactsの欄にアップロードされている。

## Markdownの書き方

[公式ドキュメント](https://pandoc-doc-ja.readthedocs.io/ja/latest/users-guide.html#pandocs-markdown)に書き方が記載されているので、こちらを参考に。

## 特徴

Pandocを使って自動生成してるので、いくつかPandoc特有の動作をします。

- Pandocのオプションで`--toc`や`--toc-depth`を指定しているので、セクション(行頭に#がある行)を集めて目次を自動生成します。セクションは自動で採番されるので、もし、番号をつけたくなければセクションの行末に`{-}`か`{.unnumberd}`をつけてください。目次にも載せたくない場合は`{.unlisted .unnumberd}`を指定します。
- ページを切り替える時は`\pagebreak`の1行を追加します。
- Pandocはコードスパンに対応していましせん。(``で囲む以外に他に書き方がある？）
