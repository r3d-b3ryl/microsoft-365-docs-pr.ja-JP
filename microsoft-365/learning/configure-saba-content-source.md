---
title: サーバーのコンテンツ ソースとして Saba を構成Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: サーバーの学習コンテンツ ソースとして Saba を構成するMicrosoft Viva ラーニング。
ms.openlocfilehash: 1f8c9610d9c1e747af6e0804bbd7c133de4351cf
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755795"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>サーバーのコンテンツ ソースとして Saba を構成Microsoft Viva ラーニング

この記事では、サバをサードパーティの学習コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。 これらの手順を実行するには、サバ システム管理者またはスーパー ユーザーである必要があります。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Saba コンテンツおよび関連するサービスは、Saba のプライバシーおよびサービス条件の対象です。

>[!NOTE]
>Viva ラーニングサバとの統合では、1 か月あたりの API 呼び出しのバケットから API が使用され、スロットル制限にカウントされます。

## <a name="configure-in-your-saba-portal"></a>サバ ポータルで構成する

>[!NOTE]
>次の手順を実行するには、サバで管理者のアクセス許可を持っている必要があります。

### <a name="clients-host-url"></a>クライアントのホスト URL

1. プライマリ サバ クラウド URL ("org.sabacloud.com" など) を識別します。 API ダッシュボードの URL が org-api.sabacloud.com、ホスト URL が org.sabacloud.com。
2. 「Saba **Cloud** Admin System Admin Manage  >    >    >  **Integrations** API Dashboard」に移動して  >  **、API ダッシュボードの URL を特定します**。 API ダッシュボードの URL を見つけて、"https://" と "-api" を削除してホスト URL を取得します。

    ![API ダッシュボードのイメージ。](../media/learning/saba-a.png)

### <a name="client-id-and-client-secret"></a>クライアント ID とクライアント シークレット

1. ホスト URL を取得したのと同じ画面で、クライアント ID とクライアント シークレットが既に生成されている場合はコピーします。

2. クライアント シークレットがまだない場合は **、[GENERATE] ボタンを選択して** 生成します。

    ![[生成] ボタンの上にカーソルを置く API ダッシュボードのイメージ。](../media/learning/saba-b.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>サーバーで構成Microsoft 365 管理センター

サーバーで構成を完了する必要Microsoft 365 管理センター。

>[!NOTE]
>これらの手順を実行するには、管理者のアクセス許可Microsoft 365必要があります。

1. 自分のアカウントに[ログインMicrosoft 365 管理センター。](https://admin.microsoft.com)
2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ ラーニング] を選択し、パネルからサバ クラウドを有効にします。
3. サバ ポータルから得た詳細を入力します。
    >[!NOTE]
    >表示名は、組織内のビバ グループ内のユーザーに対して、サバ学習コンテンツが表示されるカルーセルラーニング。 新しい名前を入力しない場合は、既定の名前 "Saba Cloud" が表示されます。
4. [保存 **] を** 選択して、サーバーでサバ クラウド コンテンツをMicrosoft Viva ラーニング。 コンテンツがビバ モードで表示されるのに最大で 24 時間かかる場合ラーニング。

> [!Note]
> Saba Cloud 統合では、ホスト URL に sabacloud.com ドメインが必要です。 ドメイン名が異なる場合は、ドメイン名を許可するためにサポート チケットを引き上げる必要があります。

>[!NOTE]
>テナント のメタデータは、データ ストアに集中して格納され、地域固有のデータ ストアには格納されません。

>[!NOTE]
>現在、組織内のすべてのユーザーは、テナント固有のすべてのコースを検出できますが、アクセスできるコースのみを使用できます。 ロールとアクセス許可に基づくユーザー固有のコンテンツ検出は、今後のリリースに向け計画されています。