---
title: アプリケーション監視 & レポート作成-セキュリティセンター
description: 組織でクラウドアプリを使用する方法について詳しく説明します。 には、さまざまな種類のアプリ、リスクレベル、およびアラートが含まれています。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、アプリ
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e5f41eef243bbd5f475dc719071833c4c21111d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199723"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターでのアプリの監視とレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


これらのレポートでは、組織内でのクラウドアプリの使用方法についての洞察が得られます。 には、さまざまな種類のアプリ、リスクレベル、およびアラートが含まれています。

## <a name="monitor-email-accounts-at-risk"></a>危険性の高い電子メール アカウントの監視

**電子メール保護** は、危険にさらされている電子メールアカウントを示します。 Microsoft Defender セキュリティセンターでさらに調査するアカウントを選択することができます。

![電子メール保護カード](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>ユーザーによって付与されるアプリのアクセス許可を監視する

**Cloud App security-OAuth アプリ** は、ユーザーによってアクセス許可が付与されている Cloud app security によって検出されたアプリを一覧表示します。 Cloud App Security のリスクカタログには、16000 70 を超えるリスク要因を使用して評価されるのアプリが含まれています。

リスク要因は、アプリ発行者などの一般的な情報から開始されます。 その後、アプリが rest での暗号化をサポートしているかどうかや、ユーザーアクティビティの監査ログを表示するかどうかなど、セキュリティの測定およびコントロールに移動します。

![Cloud App Security OAuth アプリカード](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Cloud app のユーザーアカウントを監視する

**確認のためのクラウドアプリアカウントに** は、注意が必要なアカウントが一覧表示されます。

![レビューカード用の Cloud App アカウント](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>使用されているクラウドアプリを理解する

検出された**クラウドアプリ (カテゴリ)** は、組織で使用されているアプリの種類を示します。 Cloud App Security の Cloud Discovery dashboard にリンクします。 詳細については、「 [クイックスタート: 検出されたアプリの操作](https://docs.microsoft.com/cloud-app-security/discovered-apps)」を参照してください。  

![検出されたクラウドアプリのカテゴリカード](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>ユーザーがクラウドアプリにアクセスする監視を監視する

**クラウドアプリのアクティビティの場所** は、ユーザーがクラウドアプリにアクセスする場所を示しています。

![クラウドアプリのアクティビティの場所カード](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>インフラストラクチャの負荷の状態を監視する

**インフラストラクチャの状態** Azure セキュリティセンターのインフラストラクチャワークロードの正常性状態アラートを表示します。

Azure セキュリティセンターでは、オンプレミスとクラウドのワークロード全体にわたる統合セキュリティ管理と高度な脅威保護が提供されます。 ファイアウォールやその他のパートナーソリューションを含む、さまざまなソースからのセキュリティデータを収集、検索、および分析することができます。

詳細については、「 [Azure セキュリティセンターのドキュメント](https://docs.microsoft.com/azure/security-center/)」を参照してください。

![インフラストラクチャ正常性カード](../../media/infrastructure-health.png)
