---
title: アプリの監視&レポート - セキュリティ センター
description: 組織でのクラウド アプリの使用に関するより詳しい情報を得る方法について学習します。 さまざまな種類のアプリ、リスクのレベル、アラートが含まれます。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930524"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターでのアプリの監視とレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


これらのレポートは、クラウド アプリが組織でどのように使用されているのかについてより詳しい情報を提供します。 さまざまな種類のアプリ、リスクのレベル、アラートが含まれます。

## <a name="monitor-email-accounts-at-risk"></a>危険性の高い電子メール アカウントの監視

**メール保護は、** 危険にさらされているメール アカウントを示します。 Microsoft Defender セキュリティ センターでさらに調査するアカウントを選択できます。

![電子メール保護カード](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>ユーザーによって付与されたアプリのアクセス許可を監視する

**Cloud App Security - OAuth アプリは、Cloud** App Security によって検出され、ユーザーがアクセス許可を付与したアプリを一覧表示します。 Cloud App Security のリスク カタログには、70 以上のリスク要因を使用して評価される 16,000 を超えるアプリが含まれています。

リスク要因は、アプリの発行元などの一般的な情報から始まるものになります。 その後、アプリが保存中の暗号化をサポートするかどうかや、ユーザー アクティビティの監査ログを提供するかどうかなどのセキュリティ対策と制御に移動します。

![Cloud App Security OAuth アプリ カード](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>クラウド アプリのユーザー アカウントを監視する

**注意が必要なレビュー リスト アカウント** 用のクラウド アプリ アカウント。

![レビュー カード用のクラウド アプリ アカウント](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>使用されているクラウド アプリを理解する

**検出されたクラウド アプリ (カテゴリ) は** 、組織で使用されているアプリの種類を示します。 Cloud App Security の Cloud Discovery ダッシュボードにリンクします。 詳細については、「クイック スタート: 検出されたアプリ [を使用する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。  

![検出されたクラウド アプリカテゴリ カード](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>ユーザーがクラウド アプリにアクセスする場所を監視する

**クラウド アプリ アクティビティの場所には、** ユーザーがクラウド アプリにアクセスしている場所が表示されます。

![クラウド アプリ アクティビティの場所カード](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>インフラストラクチャ ワークロードの正常性を監視する

**インフラストラクチャの正常性は** 、Azure Defender のインフラストラクチャ ワークロードに関する正常性状態のアラートを示します。

Azure Defender は、オンプレミスとクラウドのワークロードOffice 365 をサポートする統合セキュリティ管理と Defender を提供します。 ファイアウォールや他のパートナー ソリューションなど、さまざまなソースからセキュリティ データを収集、検索、分析できます。

詳細については [、Azure Defender のドキュメントを参照してください](https://docs.microsoft.com/azure/security-center/)。

![インフラストラクチャ正常性カード](../../media/infrastructure-health.png)
