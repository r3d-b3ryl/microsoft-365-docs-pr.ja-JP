---
title: サーバーのコンテンツ ソースとして Saba を構成Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/07/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: サーバーの学習コンテンツ ソースとして Saba を構成するMicrosoft Viva ラーニング。
ROBOTS: NOINDEX
ms.openlocfilehash: 26af97604b071e621794937d45882c98fdef0d31
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557162"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>サーバーのコンテンツ ソースとして Saba を構成Microsoft Viva ラーニング

この記事では、サバをサードパーティの学習コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。 これらの手順を実行するには、サバ システム管理者またはスーパー ユーザーである必要があります。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Saba コンテンツおよび関連するサービスは、Saba のプライバシーおよびサービス条件の対象です。

## <a name="clients-host-url"></a>クライアントのホスト URL

1. プライマリ サバ クラウド URL ("org.sabacloud.com" など) を識別します。 API ダッシュボードの URL が org-api.sabacloud.com、ホスト URL が org.sabacloud.com。

2. 「Saba **Cloud** Admin System Admin Manage  >    >    >  **Integrations** API Dashboard」に移動して  >  **、API ダッシュボードの URL を特定します**。 API ダッシュボードの URL を見つけて、"https://" と "-api" を削除してホスト URL を取得します。

<!--![Image of the API dashboard.](../media/learning/saba-1.png)-->

## <a name="client-id-and-client-secret"></a>クライアント ID とクライアント シークレット

1. ホスト URL を取得したのと同じ画面で、クライアント ID とクライアント シークレットが既に生成されている場合はコピーします。

2. クライアント シークレットがまだない場合は **、[GENERATE] ボタンを選択して** 生成します。

    <!--![Image of the button to generate the Client secret.](../media/learning/saba-2.png)-->

## <a name="username-and-password"></a>ユーザー名とパスワード

REST API を介してサバ クラウドからコースMicrosoft Viva関連情報を取得するために使用する管理者アカウントのユーザー名とパスワードを指定します。 このアカウントは、理想的にはスーパー ユーザーである必要があります。 アカウントがスーパー ユーザーではない場合は、少なくとも ラーニング Admin **-** カタログ ビルダーと Human **Capital Admin** の役割 (または同等のカスタム セキュリティ ロール) がサバに含されている必要があります。

## <a name="last-steps"></a>最後の手順

サーバーで構成を完了する必要Microsoft 365 管理センター。

1. 自分のアカウントに[ログインMicrosoft 365 管理センター。](https://admin.microsoft.com)
2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ ラーニング] を選択し、パネルからサバ クラウドを有効にします。
3. サバ ポータルから得た詳細を入力します。
    >[!NOTE]
    >表示名は、組織内のビバ グループ内のユーザーに対して、サバ学習コンテンツが表示されるカルーセルラーニング。 新しい名前を入力しない場合は、既定の名前 "Saba Cloud" が表示されます。

    <!--![Image of where you post configuration details in the admin center.](../media/learning/saba-3.png)-->

4. [保存 **] を** 選択して、サーバーでサバ クラウド コンテンツをMicrosoft Viva ラーニング。 コンテンツがビバ モードで表示されるのに最大で 24 時間かかる場合ラーニング。

> [!Note]
> Saba Cloud 統合では、ホスト URL に sabacloud.com ドメインが必要です。 ドメイン名が異なる場合は、ドメイン名を許可するためにサポート チケットを引き上げる必要があります。

## <a name="data-residency"></a>データ所在地

テナント のメタデータは、データ ストアに集中して格納され、地域固有のデータ ストアには格納されません。

## <a name="roles-and-permissions"></a>ロールと権限

現在、組織内のすべてのユーザーは、テナント固有のすべてのコースを検出できます。 ただし、アクセスできるコースのみを使用できます。 ユーザー固有のコンテンツ検出 (役割とアクセス許可に基づく) は、今後展開される予定です。
