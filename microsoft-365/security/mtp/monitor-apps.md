---
title: Microsoft 365 セキュリティセンターでのアプリの監視とレポート
description: 組織でクラウドアプリを使用する方法について詳しく説明します。
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
ms.openlocfilehash: f0f436e2b4e9a26f10ec134718796624c9496e81
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600154"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターでのアプリの監視とレポート

これらのレポートでは、組織でクラウドアプリがどのように使用されているかについて、より多くの洞察を得ることができます。これには、アプリの種類、リスクレベル、アラートなどがあります。

## <a name="monitor-email-accounts-at-risk"></a>危険性の高い電子メール アカウントの監視

**電子メール保護**は、危険にさらされている電子メールアカウントを示します。 Microsoft Defender セキュリティセンターでは、アカウントをクリックしてさらに調査することができます。

![電子メール保護カード](../images/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>ユーザーによって付与されるアプリのアクセス許可を監視する

**Cloud App security-OAuth アプリ**は、ユーザーによってアクセス許可が付与されている Cloud app security によって検出されたアプリを一覧表示します。 Cloud App Security のリスクカタログには、16000 70 を超えるリスク要因を使用して評価されるのアプリが含まれています。

リスク要因は、アプリの発行元などの一般的な情報から、アプリケーションが rest での暗号化をサポートしているかどうか、またはユーザーアクティビティの監査ログを提供するかどうかなど、一般的な情報から始めて、セキュリティ対策や統制を開始します。

![Cloud App Security OAuth アプリカード](../images/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Cloud app のユーザーアカウントを監視する

**確認のためのクラウドアプリアカウントに**は、注意が必要なアカウントが一覧表示されます。

![レビューカード用の Cloud App アカウント](../images/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>使用されているクラウドアプリを理解する

検出された**クラウドアプリ (カテゴリ)** は、組織で使用されているアプリの種類と、Cloud App Security でのクラウド検出ダッシュボードへのリンクを示しています。 詳細については、「[クイックスタート: 検出されたアプリの操作](https://docs.microsoft.com/cloud-app-security/discovered-apps)」を参照してください。  

![検出されたクラウドアプリのカテゴリカード](../images/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>ユーザーがクラウドアプリにアクセスする監視を監視する

**クラウドアプリのアクティビティの場所**は、ユーザーがクラウドアプリにアクセスする場所を示しています。

![クラウドアプリのアクティビティの場所カード](../images/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>インフラストラクチャの負荷の状態を監視する

**インフラストラクチャの状態**Azure セキュリティセンターのインフラストラクチャワークロードの正常性状態アラートを表示します。

Azure セキュリティセンターでは、オンプレミスとクラウドのワークロード全体にわたる統合セキュリティ管理と高度な脅威保護が提供されます。 ファイアウォールやその他のパートナーソリューションを含む、さまざまなソースからのセキュリティデータを収集、検索、および分析することができます。

詳細については、「 [Azure セキュリティセンターのドキュメント](https://docs.microsoft.com/azure/security-center/)」を参照してください。

![インフラストラクチャ正常性カード](../images/infrastructure-health.png)
