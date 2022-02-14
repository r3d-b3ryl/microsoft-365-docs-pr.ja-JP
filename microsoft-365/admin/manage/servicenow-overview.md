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
ms.openlocfilehash: 0629b322a52702ef293ff1f73661359b410f2d69
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806014"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Microsoft 365 サポートと ServiceNow 構成の統合の概要

**Microsoft 365サポート統合** を使用すると、ヘルプMicrosoft 365、サービス正常性を ServiceNow インスタンスと統合できます。 Microsoft の既知および報告された問題を調査し、インシデントを解決し、Microsoft 推奨ソリューションを使用してタスクを完了し、必要に応じて Microsoft の人間支援サポートにエスカレートすることができます。

ServiceNow **Microsoft 365統合** アプリをサポートするには、[ServiceNow ストアに移動します](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

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

- Azure Active DirectoryアプリケーションをAADできる管理者 (Azure AD)

- ServiceNow 管理者

- Microsoft 365管理者

### <a name="configuration-highlights"></a>構成のハイライト

サポート統合を **Microsoft 365するには、次の方法を実行します**。

- 送信 API 呼び出しMicrosoft Azure Active Directory両方AAD認証用に、アプリケーションを (AAD) に登録します。

- 送信データ フローと受信データ フローの両方Microsoft Azure ADアプリケーションを使用して ServiceNow エンティティを作成します。

- ServiceNow インスタンスを Microsoft サポートと統合するには、Microsoft 365を使用します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow 統合図。":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow 環境でのアプリケーションの依存関係

必要なアクセス許可:

- oauthentity\_

- oauthentityprofile\_\_

サポート統合Microsoft 365がインストールされると、2 つのアプリケーションクロススコープ アクセスが作成されます。 正常に作成されない場合は、手動で作成します。

## <a name="what-configuration-is-right-for-your-organization"></a>組織に適切な構成は何ですか?

サポート統合用に構成をMicrosoft 365前に、ServiceNow 環境のセットアップ方法を理解してください。

- ServiceNow 環境で、受信 Web サービス呼び出しに対して基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) が許可されている場合は、「[Set up Microsoft 365 ServiceNow Basic Authentication](servicenow-basic-authentication.md) との統合をサポートする」の手順に従います。
- ServiceNow 環境で受信 Web サービス呼び出しに対して基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) が許可されていない場合は、「Microsoft 365 のセットアップ」の手順に従って、Azure AD [認証トークンとの統合を](servicenow-aad-oauth-token.md)サポートします。
  - この構成では、認証トークンが正しく動作AAD SSO テナントが必要になります。

各機能を理解するには、「サポート[統合Microsoft 365参照してください](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。
