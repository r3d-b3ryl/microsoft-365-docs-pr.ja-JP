---
title: Base API & SDK をテストする
description: Base API & SDK をテストする
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
ms.openlocfilehash: 6ae0fdf9cc49faaaff84eb3f96e076d1efba8a4c
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077440"
---
# <a name="manage-your-resource-with-sdk--apis"></a>SDK & API を使用してリソースを管理する

自動化は、DevOpsとアジャイル開発の重要な側面です。 Microsoft 365 リソースの Test Base を管理し、プログラムによってテスト結果を取得し、それらを CI ツールと統合することを探していますか? 基本 API/SDK のテストは、これらすべてを実現するのに役立ちます。

これらの API/SDK を使用すると、IT プロフェッショナルとアプリ開発者は次の機能を利用できます。

- 作成、更新、オフボードなど、Test Base アカウントを管理します。
- パッケージの作成、更新、削除、ダウンロードなど、アプリケーション パッケージを管理します。
- テストの概要、詳細なテスト結果、および分析結果を取得します。 分析結果には、CPU 回帰分析、CPU 使用率分析、メモリ回帰分析、およびメモリ使用率分析が含まれます。
- テスト結果とテスト実行ビデオの記録をダウンロードします。

Test Base for Microsoft 365 サービスでこの新しい機能にアクセスする方法については、以下のステップ バイ ステップの概要をご覧ください。

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>Python SDK を使用した Test Base アカウントの作成のステップ バイ ステップの例

1. 前提条件:

   - 必要なコンポーネントを以下にインストールします。

     - [サブスクリプションがない場合は、アクティブなサブスクリプションを持つ Azure アカウント](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup)
     - [Python 2.7 以降または 3.6 以降](https://www.python.org/downloads)
     - [Azure Command-Line インターフェイス (CLI)](/cli/azure/install-azure-cli)

   - コンソールからの pip インストールを使用してライブラリ パッケージをインストールする

     ```console
     pip install azure-identity
     pip install azure-mgmt-testbase
     ```

   - 開発環境での認証

     コードをローカルでデバッグして実行する場合、開発者は Azure サービスの呼び出しを認証するために独自のアカウントを使用するのが一般的です。 azure-IDENTITY パッケージは、ローカル開発を簡略化するために Azure CLI を使用した認証をサポートします。 Azure CLI にサインインするには、次を実行します `az login`。 既定の Web ブラウザーを使用するシステムでは、Azure CLI によってブラウザーが起動され、ユーザーが認証されます。

     [Azure サービスを使用して Python アプリケーションを認証する方法を確認します|Microsoft Docs](/azure/developer/python/azure-sdk-authenticate)およびその<https://pypi.org/project/azure-identity/>他のサポートされている認証方法。

   - 次の手順で使用する目的の名前でリソース グループを作成します。

2. 以下のコード スニペットでは、テスト ベース アカウントを作成するためのフローについて説明します。

   - Azure と対話するために Azure CLI を使用して資格情報を要求する
   - 後の操作のために資格情報とサブスクリプション ID を使用して Test Base SDK クライアントを初期化する
   - test_base_accounts モデルからbegin_createを呼び出して、テスト ベース アカウントを作成する

   コードを Python 開発環境にコピーし、"subscription-id" を Azure サブスクリプション ID に置き換え、"resource-group-name" を上記で作成したリソース グループに置き換えます。

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

SDK & API の詳細については、以下のリンクを参照してください。

**Azure サブスクリプション**:

- [アクティブなサブスクリプションを持つ Azure アカウント](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup)

**Python SDK**:

- [基本 Python SDK のドキュメントをテストする](/python/api/overview/azure/mgmt-testbase-readme)
- [基本 Python SDK のサンプルをテストする](https://aka.ms/testbase-sample-py)
- [Python SDK の Azure 一般的な使用パターン](/azure/developer/python/sdk/azure-sdk-library-usage-patterns)

**REST API**:

- [REST API のドキュメント](https://aka.ms/testbase-api)
