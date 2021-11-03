---
title: テストベース API & SDK
description: テストベース API & SDK
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9e2c52d23c0e0c949059dc37eee4c1a59b35964e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677296"
---
# <a name="manage-your-resource-with-sdk--apis"></a>SDK および API を使用して&管理する
オートメーションは、開発とアジャイル開発DevOps重要な側面です。 テスト ベースのリソースを管理しMicrosoft 365テスト結果をプログラムで取得し、CI ツールと統合しますか? テストベース API/SDK は、これらすべての達成に役立ちます。 

これらの API/SDK を使用すると、IT 担当者とアプリ開発者は次の機能を使用できます。 
- 作成、更新、オフボードなどのテストベース アカウントを管理します。 
- パッケージの作成、更新、削除、ダウンロードなど、アプリケーション パッケージを管理します。 
- テストの概要、詳細なテスト結果、および分析結果を取得します。 分析結果には、CPU 回帰分析、CPU 使用率分析、メモリ回帰分析、メモリ使用率分析が含まれます。 
- テスト結果とテスト実行ビデオ録画をダウンロードします。  

以下の手順の概要を参照して、Test Base for Microsoft 365 サービスのこの新しい機能にアクセスする方法を確認してください。

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>Python SDK を使用した Test Base アカウント作成のステップ バイ ステップの例

1. 前提条件: 

- 以下の必須コンポーネントをインストールします。 

    [サブスクリプションを持ってない場合は、](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) アクティブなサブスクリプションを持つ Azure アカウント<br>
    [Python 2.7+ または 3.6+](https://www.python.org/downloads)<br>
    [Azure Command-Line インターフェイス (CLI)](/cli/azure/install-azure-cli) <br>

- コンソールからピップ インストールを使用してライブラリ パッケージをインストールする 

```
pip install azure-identity 
pip install azure-mgmt-testbase  
```

- 開発環境での認証 

コードをローカルでデバッグして実行する場合、開発者が Azure サービスの呼び出しを認証するために独自のアカウントを使用するのが一般的です。 Azure-IDENTITY パッケージは、ローカル開発を簡素化するために Azure CLI による認証をサポートします。 Azure CLI にサインインするには、を実行します ```az login ``` 。 既定の Web ブラウザーを使用するシステムでは、Azure CLI がブラウザーを起動してユーザーを認証します。 

[「Azure サービスを使用して Python アプリケーションを認証する方法」を参照してください|Microsoft Docs](/azure/developer/python/azure-sdk-authenticate)および [https://pypi.org/project/azure-identity/](https://pypi.org/project/azure-identity/) 他のサポートされている認証方法。 

 - 次の手順で使用する必要な名前のリソース グループを作成します。 

2. 以下のコード スニペットでは、テストベース アカウントを作成するフローについて説明します。 

- Azure との対話のために Azure CLI を介して資格情報を要求する 
- 後の操作の資格情報とサブスクリプション ID を使用してテストベース SDK クライアントを初期化する 
- テスト begin_createモデルtest_base_accounts呼び出して、テスト ベース アカウントを作成する 

コードを Python 開発環境にコピーし、"subscription-id" を Azure サブスクリプション ID と "resource-group-name" に置き換え、上記で作成したリソース グループに置き換えます。 

 
```python

from azure.identity import AzureCliCredential
from azure.mgmt.testbase import TestBase
from azure.mgmt.testbase.models import TestBaseAccountResource
from azure.mgmt.testbase.models import TestBaseAccountSKU

# requesting token from Azure CLI for request
# For other authentication approaches, please see: https://pypi.org/project/azure-identity/
credential = AzureCliCredential()
subscription_id = "<subscription-id>"
resource_group = "<resource-group-name>"
testBaseAccount_name = "contoso-testbaseAccount"
testBaseAccount_location = "global"
sku_name = "S0"
sku_tier = "Standard"
sku_locations = {"global"}

# Create client
testBase_client = TestBase(credential, subscription_id)

# Create sku for test base account
sku = TestBaseAccountSKU(name=sku_name, tier=sku_tier, locations=sku_locations)

# Create test base account
parameters = TestBaseAccountResource(location=testBaseAccount_location, sku=sku)
testBaseAccount = testBase_client.test_base_accounts.begin_create(resource_group, testBaseAccount_name, parameters).result()
print("Create test base account:\n{}".format(testBaseAccount))

```


## <a name="learn-more"></a>詳細情報 

SDK および API の詳細については、以下のリンク&してください。 

**Azure サブスクリプション** 

- [アクティブなサブスクリプションを持つ Azure アカウント](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) 

**Python SDK** 

- [テストベースの Python SDK ドキュメント](/python/api/overview/azure/mgmt-testbase-readme?view=azure-python-preview)
- [基本 Python SDK のテストサンプル](https://aka.ms/testbase-sample-py) 
- [Python SDK の Azure の一般的な使用パターン](/azure/developer/python/azure-sdk-overview#provision-and-manage-azure-resources-with-management-libraries) 

**REST API**  

- [REST API のドキュメント](https://aka.ms/testbase-api)  
