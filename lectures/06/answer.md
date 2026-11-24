# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：glossary_search_glossary
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Amazon S3 バージョニング 概要', 'topics': ['general']})
- STEP 4 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Using versioning in S3 buckets overview', 'topics': ['general']})

- 気づき・疑問：設定ファイルにMCPサーバーを追加すると、モデルが利用できるツールが1個、2個、7個と増えることを確認できた。用語集とfetchは自分の環境でコマンドによって起動し、AWSのサーバーにはURLで接続するという違いが分かった。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：app/mcp_server.py に server.tool()(tools.get_lecture_summary) を追加し、講義の概要を取得するツールをMCPサーバーで公開した。
- 結果：ツール一覧に glossary_get_lecture_summary が追加された。「第2回では何を学びますか？」という質問に対して、追加したツールが呼ばれ、その結果をもとに回答が生成された。
- 気づき・疑問：サーバー側で公開するツールを追加するだけで、エージェント側のコードを変更せずに新しい機能を使えることが分かった。エージェントが起動時にサーバーからツール一覧を取得する仕組みを、実際の動作を通して理解できた。
