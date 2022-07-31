---
title: Microsoft 365 アプリの監視
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: mediumn
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
f1.keywords:
- NOCSH
description: Microsoft 365 Appsに関連するインシデントまたはアドバイザリに関する情報については、アプリの監視を使用します。
ms.openlocfilehash: 5d1b930d7dec33c05234a5349c881355e2574120
ms.sourcegitcommit: 0ae89b71b202aceabd5061f0d5b46d030d93e931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "66993716"
---
# <a name="microsoft-365-apps-monitoring"></a>Microsoft 365 アプリの監視

Microsoft 365 Apps監視では、Access、Excel、OneNote、Outlook、PowerPoint、Publisher、Word というデスクトップ Office アプリケーションの組織レベルのシナリオがサポートされています。

- **過剰なクライアント ランタイム エラー**。 特定の Office アプリケーションのランタイム エラー率は、過去 24 時間で大幅に増加しました。

- **ローカル ファイルの読み込み時間が長い**。 ローカル ストレージからの平均ファイル読み込み時間が、過去 24 時間の推奨しきい値を超えています。

- **アプリケーションの読み込み時間が長い**。 アプリケーションの平均読み込み時間が、過去 24 時間の推奨しきい値を超えています。

- **過剰なマクロ エラー**。 マクロ エラー率が、過去 24 時間の推奨しきい値を超えています。

- **過剰なアドイン エラー**。 アドインエラー率が、過去 24 時間の推奨しきい値を超えています。

- **SharePoint ファイルの読み込み時間が長い**。 SharePoint からの平均ファイル読み込み時間が、過去 24 時間の推奨しきい値を超えています。

アプリ監視ダッシュボードの例を次に示します。

![Microsoft 365 Apps監視のための組織レベルのシナリオ。](../media/microsoft-365-exchange-monitoring/M365AppsMonitoring1.png)

Microsoft がエラー状態を検出すると、テナント管理者に通知する投稿が作成され、Microsoft 365 App Health ダッシュボードに移動して問題を修復するための詳細が表示されます。 詳細については、「[Microsoft 365 Apps の正常性](/deployoffice/admincenter/microsoft-365-apps-health)」を参照してください。
