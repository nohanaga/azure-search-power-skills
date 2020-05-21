---
page_type: sample
languages:
- csharp
products:
- azure
- azure-search
azureDeploy: https://raw.githubusercontent.com/nohanaga/azure-search-power-skills/master/Template/HelloWorld/azuredeploy.json
name: "Hello World sample skill for cognitive search"
description: "このHello Worldカスタムスキルは、独自のスキルを作成するためのテンプレートとして使用できます。"
---

# Hello World (テンプレート)

この「Hello World」カスタムスキルは、独自のスキルを作成するためのテンプレートとして使用できます。

## 必要条件

このスキルには、[ルート`README.md`](../../README.md) に記載されているもの以外の要件はありません。

## 設定

この機能は、アプリケーション設定を必要としません。

## デプロイ

[![Deploy to Azure](https://azuredeploy.net/deploybutton.svg)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnohanaga%2Fazure-search-power-skills%2Fmaster%2FTemplate%2FHelloWorld%2Fazuredeploy.json)

## hello-world

### サンプルインプット

```json
{
    "values": [
        {
            "recordId": "r1",
            "data":
            {
            	"name": "World"
            }
        }
    ]
}
```

### サンプルアウトプット:

```json
{
    "values": [
        {
            "recordId": "r1",
            "data": {
                "greeting": "Hello, World"
            },
            "errors": [],
            "warnings": []
        }
    ]
}
```

## スキルセット統合の例

このスキルをCognitive Searchパイプラインで使用するには、スキル定義をスキルセットに追加する必要があります。
この例のスキル定義の例を次に示します（特定のシナリオとスキルセット環境を反映するように入力と出力を更新する必要があります）。

```json
{
    "@odata.type": "#Microsoft.Skills.Custom.WebApiSkill",
    "description": "Hello world",
    "uri": "[AzureFunctionEndpointUrl]/api/hello-world?code=[AzureFunctionDefaultHostKey]",
    "batchSize": 1,
    "context": "/document/merged_content/people/*",
    "inputs": [
        {
            "name": "name",
            "source": "/document/merged_content/people/*"
        }
    ],
    "outputs": [
        {
            "name": "greeting",
            "targetName": "greeting"
        }
    ]
}
```
