---
title: Microsoft 365 Lighthouseでエンタープライズ クラウド PC のネットワーク接続に失敗したを表示する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: katmartin
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、エンタープライズ クラウド PC でネットワーク接続に失敗したことを確認する方法について説明します。
ms.openlocfilehash: 273e0737cbe59d9ecae40fad0c114f58881a5d05
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66823403"
---
# <a name="view-an-enterprise-cloud-pc-failed-network-connection-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでエンタープライズ クラウド PC のネットワーク接続に失敗したを表示する

Microsoft 365 Lighthouseは、顧客テナントと Azure Active Directory (Azure AD) の間の接続状態を提供します。 クラウド PC でネットワーク接続に失敗した場合は、Microsoft エンドポイント マネージャー管理センターで詳細情報を表示できます。

## <a name="before-you-begin"></a>はじめに

- パートナー テナントのグローバル管理者である必要があります。
- 接続の問題を表示するには、Cloud PC 管理者または Cloud PC 閲覧者のアクセス権が必要です。

## <a name="view-a-failed-network-connection"></a>失敗したネットワーク接続を表示する

1. Lighthouse の左側のナビゲーション ウィンドウで、**デバイス** > **Windows 365** を選択します。

2. [ **Azure ネットワーク接続** ] タブを選択します。

3. [接続の概要] セクションで、[ **失敗した接続**] を選択します。

4. フィルター処理された一覧から、調査する **接続の横にある [Microsoft エンドポイント マネージャーで** 接続の詳細を表示する] を選択します。

5. Microsoft エンドポイント マネージャー管理センターで、[**詳細の表示**] を選択してエラーの詳細を確認します。

## <a name="next-steps"></a>次の手順

接続の問題のトラブルシューティングについては、「 [オンプレミスネットワーク接続のトラブルシューティング](/windows-365/enterprise/troubleshoot-on-premises-network-connection)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[クラウド PC ロールベースのアクセス制御 ](/windows-365/enterprise/role-based-access)(記事)\
[Active Directory ドメインへの参加](/windows-365/enterprise/troubleshoot-on-premises-network-connection#active-directory-domain-join) (記事)\
[Azure Active Directory デバイス同期](/windows-365/enterprise/troubleshoot-on-premises-network-connection#azure-active-directory-device-sync) (記事)
