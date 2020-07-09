---
title: Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する
description: Microsoft 365 セキュリティセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
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
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087923"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する

[Microsoft 365 セキュリティセンター](overview-security-center.md)は、ServiceNow のチケットをネイティブに作成および追跡する機能によって強化されました。 [ServiceNow の詳細情報](https://www.servicenow.com/)

セキュリティセンターでは、セキュリティ管理者が Microsoft のセキュリティ[で保護されたスコア](microsoft-secure-score.md)向上アクションを ServiceNow に直接送信して、チケットを作成することができます。 インシデント管理チケットと変更管理チケットの両方を作成できます。 その後、セキュリティセンターのホームページと ServiceNow で追跡できます。

- [**前提条件、データ交換、およびトラブルシューティングについて説明します。**](tickets.md)
- **コンプライアンスセンターで ServiceNow チケットを管理する**(近日中)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Microsoft 365 セキュリティセンターを ServiceNow に接続する

Microsoft 365 セキュリティセンターのホームページに移動して、ServiceNow 接続カードを表示します。

![ServiceNow を使用していますか](../../media/do-you-use-servicenow-250.png)

[ServiceNow に接続] を選択して、[ServiceNow セットアップ] ページに移動します。 指示に従って、Microsoft 365 Connector アプリを承認します。

> [!NOTE]
> Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。 個人の資格情報は使用しないでください。

指示に従って接続を承認した後、Microsoft 365 セキュリティセンター接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの両方の接続状態を表示します。 これで、タスクの作成を開始するための設定が完了しました。

### <a name="troubleshooting"></a>トラブルシューティング

接続プロセスで発生する可能性のある一般的なエラーと、それらを軽減する方法については、 [「トラブルシューティング」](tickets.md#troubleshooting)を参照してください。

## <a name="create-a-task-and-share-it-to-servicenow"></a>タスクを作成して ServiceNow に共有する

統合がセットアップされたら、特定の Microsoft セキュリティスコア向上アクションに基づいて ServiceNow タスクを作成します。 Microsoft 365 セキュリティセンターポータルで、[セキュリティで保護されたスコア] のすべての改善アクションに移動し、[共有] アイコンを選択します。 ドロップダウンオプションの1つは ServiceNow です。

![セキュリティで保護されたスコアでの ServiceNow 共有](../../media/servicenow-share.png)

タスクが生成され、優先度を設定して、名前、説明、または期限を編集できます。 すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信します。

タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。

## <a name="track-tickets"></a>チケットを追跡する

ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。 これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。

![ServiceNow 変更管理チケット](../../media/change-management-375.png)  ![ServiceNow インシデント管理チケット](../../media/incident-management-375.png)

Microsoft 365 セキュリティセンターで ServiceNow 統合を再プロビジョニングまたは管理するには、いずれかのカードで**servicenow 構成を管理**するを選択します。 そこから、現在の ServiceNow 接続を削除し、チケットの状態名をカスタマイズします。

Microsoft 365 セキュリティセンターで ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および操作できる場所に存在します。

## <a name="resources"></a>リソース

- [前提条件、データ交換、およびトラブルシューティングについて説明します。](tickets.md)
- [Microsoft セキュア スコア](microsoft-secure-score.md)