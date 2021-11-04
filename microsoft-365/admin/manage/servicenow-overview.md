---
title: Microsoft 365 サポートと ServiceNow 構成の統合の概要
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow のスコープ認定アプリケーションのインストールと構成ガイド。
ms.openlocfilehash: 28b156cc9f9062863868550f2aac216b8d92a403
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754201"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Microsoft 365 サポートと ServiceNow 構成の統合の概要

**Microsoft 365統合を使用** すると、ヘルプMicrosoft 365、サービス正常性を ServiceNow インスタンスと統合できます。 Microsoft の既知および報告された問題を調査し、インシデントを解決し、Microsoft 推奨ソリューションを使用してタスクを完了し、必要に応じて Microsoft の人間支援サポートにエスカレートすることができます。

ServiceNow **ストアMicrosoft 365** 統合アプリをサポートするには [、ServiceNow ストアに移動します](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

## <a name="key-features"></a>主な機能

ServiceNow インスタンスの統合アプリをサポートするMicrosoft 365主な機能を次に示します。

- サービス正常性インシデント: 既知の Microsoft サービス正常性インシデントに関する情報 (ユーザーの影響、スコープ、現在の状態、次に予期される更新プログラムなど)。 機械学習を使用して、ServiceNow インシデントは、短い説明フィールドに基づいて Microsoft サービス正常性インシデントと一致します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="[サービス正常性インシデント] の説明フィールド。":::

- 推奨されるソリューション: タスクとインシデントの説明は、機械学習を利用した Microsoft の正確なターゲットソリューションと関連記事を推奨するために使用されます。 必要に応じて、検索を使用して他のソリューションを検索できます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="[推奨されるソリューションの説明] フィールド。":::

- Microsoft サービス要求: Microsoft サポート エージェントに問題をエスカレートし、ケースの状態更新プログラムを受け取る。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="サービス要求フォーム。":::

## <a name="prerequisites"></a>前提条件

### <a name="permissions-requirements"></a>アクセス許可の要件

このガイドを続行するには、プロセス全体で環境に対して次のアクセス許可が使用可能で構成されていることを確認します。

- Azure Active DirectoryアプリケーションをAADできる管理者 (AAD)

- ServiceNow 管理者

- Microsoft 365管理者

### <a name="configuration-highlights"></a>構成のハイライト

サポート統合を **Microsoft 365するには**、

- 送信 API 呼び出しMicrosoft Azure Active Directory両方AAD認証用に、アプリケーションを (AAD) に登録します。

- 送信データ フローと受信データ フローの両方AADアプリケーションを使用して ServiceNow エンティティを作成します。

- ServiceNow インスタンスを Microsoft サポートと統合するには、Microsoft 365を使用します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow 統合図。":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow 環境でのアプリケーションの依存関係

必要なアクセス許可:

- oauth \_ エンティティ

- oauth \_ エンティティ \_ プロファイル

サポート統合Microsoft 365がインストールされると、2 つのアプリケーションクロススコープ アクセスが作成されます。 正常に作成されない場合は、手動で作成します。

## <a name="what-features-will-work-for-your-organization-based-on-your-configuration"></a>構成に基づいて組織でどのような機能が機能しますか?

サポート統合用に構成をMicrosoft 365前に、次の質問に対する回答を確認してください。

**質問 \# 1**: ServiceNow 環境では、受信 Web サービス呼び出しに対して基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) を許可していますか?

**質問 \# 2**: 複数のテナントがある場合は、ServiceNow 環境と統合された 1 つのテナントを使用して、サポート統合Microsoft 365しますか?

上記の質問に対する回答に応じて、次の表に、使用可能な機能と、サポート統合の設定方法Microsoft 365示します。 各機能の説明については、「サポート[統合Microsoft 365参照してください](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

| 質問 \# 1 回答 | 質問 \# 2 回答 | 利用できる機能は何ですか? | 構成の手順 |
|---------------------|---------------------|-----------|----------------|
| はい                 | はい/いいえ              | サービス正常性インシデント推奨ソリューション Microsoft サービス要求 | [ServiceNow Microsoft 365認証との統合をサポートする方法を設定する](servicenow-basic-authentication.md) |
| いいえ                  | はい                 | サービス正常性インシデント推奨ソリューション Microsoft サービス要求 | [OAuth トークンMicrosoft 365サポート統合AAD設定する](servicenow-aad-oauth-token.md)                 |
| いいえ                  | いいえ                  | サービス正常性インシデント推奨ソリューション                           | [サポート統合Microsoft 365のセットアップのみインサイトする](servicenow-service-health-incidents-solutions-only.md)                    |
