# Azure Cognitive Search パワースキル

パワースキルは、Azure Cognitive Searchのカスタムスキルとして展開される便利な機能のコレクションです。スキルは、[テンプレート](Template/HelloWorld/README.md)または独自のカスタムスキルの開始点として使用できます。また、要件を満たしていれば、そのまま展開して使用することもできます。また、[プルリクエスト](https://github.com/nohanaga/azure-search-power-skills/compare)を送信して、ご自身の作業に貢献することをお勧めします。

## 機能

このプロジェクトは、次のカスタムスキルを提供します。

* [**HelloWorld**](Template/HelloWorld/README.md): 自分のスキルの出発点またはテンプレートとして使用できる最小限のスキル。
* [**GeoPointFromName**](Geo/GeoPointFromName/README.md): 場所の名前と住所から座標を取得します。
* [**BingEntitySearch**](Text/BingEntitySearch/README.md): 公共の人物、場所、または組織に関する豊富で構造化された情報を見つけます。
* [**AcronymLinker**](Text/AcronymLinker/README.md): 既知の頭字語の定義を提供します。
* [**ImageStore**](Vision/ImageStore/README.md): base64でエンコードされた画像をblobストレージとの間で保存およびフェッチします。
* [**HocrGenerator**](Vision/HocrGenerator/README.md): OCRの結果をhOCR形式に変換します。
* [**AnalyzeForm**](Vision/AnalyzeForm/README.md): 文書内のフォームフィールドを認識します。
* [**CustomEntityLookup**](/Text/CustomEntitySearch): テキスト内のカスタムエンティティ名を検索します。
* [**Tokenizer**](Text/Tokenizer/README.md): テキストからノンストップワードを抽出します。
* [**Distinct**](Text/Distinct/README.md): 用語のリストを重複排除します。
* [**GetFileExtension**](Utils/GetFileExtension/README.md): ファイル名と拡張子を個別の値として返し、ドキュメントタイプでフィルタリングできます。

## Getting Started

### 前提条件

このプロジェクトの機能を使用するには、アクティブなAzureサブスクリプションが必要です。ほとんどの機能は、迅速な評価と実験のために単独で使用できますが、[Azure Cognitive Searchパイプライン](https://docs.microsoft.com/azure/search/cognitive-search-quickstart-blob)の一部として使用することを目的としています。各機能は、利用するサービスのAPIキーなど、独自の特定の要件を追加する場合もあります。

[Visual Studio 2019](https://visualstudio.microsoft.com/)をお勧めしますが、必須ではありません。最新バージョンのC＃コンパイラが必要です。[Postman](https://www.getpostman.com/)は、スキルを実験およびテストする方法として強く推奨されます。

### インストールとデプロイ

AzureワークロードがインストールされたVisual Studioを使用する場合、インストールは不要であり、機能はF5を使用してローカルで実行することができます。

Azureへの機能のデプロイは、[Visual Studioを通じて](https://docs.microsoft.com/azure/azure-functions/deployment-zip-push)、[Azureにデプロイ]ボタン、または[継続的デプロイメント](https://docs.microsoft.com/azure/azure-functions/functions-continuous-deployment)で可能です。

一部の機能では、環境変数または構成エントリの設定が必要になる場合があります。 機能のディレクトリにあるREADMEファイルを参照してください。

### クイックスタート

1. リポジトリをクローンする
2. Visual StudioでPower Skillsソリューションを開く
3. テストする機能のプロジェクトをスタートアッププロジェクトとして設定する
4. F5を押す
5. Postmanを使用して機能を呼び出す実験をする

[私たちのHello Worldテンプレートスキル](Template/HelloWorld/README.md)を開始点として使用して、独自のスキルを作成することもできます。

## リソース

- [Contribution guidelines](CONTRIBUTING.md)
- [Azure Search](https://azure.microsoft.com/services/search/)
- [Azure Functions](https://azure.microsoft.com/services/functions/)
- [JFK Files](https://github.com/microsoft/AzureSearch_JFK_Files)
- [Knowledge Mining Solution Accelerator Guide](https://github.com/nohanaga/azure-search-knowledge-mining)
