---
title: Microsoft 365 サポートと ServiceNow 構成の統合の概要
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: dc69f6210eda4ba04dfd0aecf9795bfcba2efe22
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324327"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Microsoft 365 サポートと ServiceNow 構成の統合の概要

次のコンテンツは、最小バージョン **1.0.7** のMicrosoft 365 サポート統合アプリに適用されます。

**Microsoft 365サポート統合** を使用すると、Microsoft 365ヘルプ、サポート、およびサービスの正常性を ServiceNow インスタンスと統合できます。 Microsoft の既知の問題と報告された問題を調査し、インシデントを解決し、Microsoft 推奨ソリューションを使用してタスクを完了し、必要に応じて Microsoft の人間支援サポートにエスカレートすることができます。

ServiceNow ストアから **Microsoft 365サポート統合** アプリについては、[ServiceNow ストア](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)に移動します。

## <a name="key-features"></a>主な機能

ServiceNow インスタンスの統合アプリをサポートするMicrosoft 365で得られる主な機能は次のとおりです。

- Service Health Incidents: ユーザーの影響、スコープ、現在の状態、次に予想される更新プログラムなど、既知の Microsoft サービス正常性インシデントに関する情報。 機械学習を使用して、ServiceNow インシデントは、簡単な説明フィールドに基づいて Microsoft サービス正常性インシデントと照合されます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="[Service Health Incidents description]\(サービス正常性インシデントの説明\) フィールド。":::

- 推奨される解決策: タスクとインシデントの説明は、機械学習を利用した Microsoft の正確なターゲットソリューションと関連記事を推奨するために使用されます。 必要に応じて、Search を使用して他のソリューションを検索することもできます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="推奨されるソリューションの説明フィールド。":::

- Microsoft サービス要求: Microsoft サポート エージェントに問題をエスカレートし、ケースの状態更新プログラムを受け取ります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="サービス要求フォーム。":::

## <a name="prerequisites"></a>前提条件

### <a name="permissions-requirements"></a>アクセス許可の要件

このガイドに進むには、プロセス全体で環境に対して次のアクセス許可が使用可能で構成されていることを確認します。

- Azure AD アプリケーションを作成できるAzure Active Directory (AAD) 管理者

- ServiceNow 管理者

- テナント管理者Microsoft 365

### <a name="configuration-highlights"></a>構成の強調表示

**Microsoft 365サポート統合を** 設定するには:

- 送信 API 呼び出しと受信 API 呼び出しの両方の認証のために、Microsoft Azure Active Directory (AAD) にアプリケーションを登録します。

- 送信データ フローと受信データ フローの両方に対して、Microsoft Azure AD Application を使用して ServiceNow エンティティを作成します。

- Microsoft 365管理ポータルを使用して、ServiceNow インスタンスを Microsoft サポートと統合します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow 統合図。":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow 環境でのアプリケーションの依存関係

必要なアクセス許可:

- oauthentity\_

- oauthentityprofile\_\_

Microsoft 365サポート統合アプリがインストールされると、2 つのアプリケーション クロススコープ アクセスが作成されます。 正常に作成されない場合は、手動で作成します。

## <a name="setup-the-integration"></a>統合をセットアップする

アプリをダウンロードしたら、SNOW 環境のMicrosoft 365セットアップ ウィザードに移動してセットアップ プロセスを完了します。
:::image type="content" source="../../media/154124985-76e13e7d-b32e-4741-830b-bbb110d3ecbf.png" alt-text="Snow セットアップ ウィザード":::

手順の詳細については、次のページを参照してください。
- ServiceNow 環境で受信 Web サービス呼び出しの基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) が許可されている場合は、「[ServiceNow Basic Authentication との統合をサポートMicrosoft 365セットアップ](servicenow-basic-authentication.md)する」の手順に従います。
- ServiceNow 環境で受信 Web サービス呼び出しの基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) が許可されていない場合は、「[Azure AD認証トークンとの統合をサポートMicrosoft 365セットアップ](servicenow-aad-oauth-token.md)する」の手順に従います。
  - この構成では、AAD認証トークンが正しく動作するために SSO テナントが必要になります。

各機能について理解するには、「[Microsoft 365サポート統合](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)」を参照してください。

> [!NOTE]
> このアプリは、規制または制限された環境ではサポートされていません。
