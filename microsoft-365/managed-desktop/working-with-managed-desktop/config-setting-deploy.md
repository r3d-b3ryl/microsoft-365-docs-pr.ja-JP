---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900286"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ

設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。 このページには、各構成可能な設定の概要が表示されます。 [設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。

## <a name="deployment-statuses"></a>展開の状態 

これらの statues は、展開ごとに表示されます。

状態  | 説明 
--- | --- 
展開 | 変更は、このグループへの展開を待機しています。
処理中 | このグループ内のアクティブなデバイスに変更が適用されています。 
完了 | このグループ内のすべてのアクティブなデバイスで変更が完了しました。 
Failed | グループ内のアクティブなデバイスの 10% で変更が失敗したため、展開が停止されました。<br><br> 展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。 
復帰 | 変更は、すべての展開グループに正常に展開された最後の変更に戻されました。

## <a name="deploy-changes"></a>変更を展開する

これらの手順にデスクトップの背景画像が表示されます。 展開をステージングした後、[展開の状態] ページから変更を展開します。 

**変更を展開するには**

1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする
2. [**設定**] で、[**構成可能**] を選択します。
3. [**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。
4. 展開グループのいずれかに変更を展開するには、[**展開**] を選択します。

![構成可能な設定の展開状態の概要](images/deploy-cs-overview.png)

Microsoft マネージドデスクトップでは、次の順序で展開グループへの展開が推奨されます。テスト、ファースト、Fast、および広範。 

各グループで変更が完了すると、状態が [**完了**] に変わります。

![構成可能な設定の展開の完了](images/config-setting-complete.png)

## <a name="revert-deployment"></a>展開を元に戻す

変更を展開した後、**展開状態**から元に戻すことができます。 **進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。 この設定は、すべてのグループに展開された最新のバージョンに戻ります。 

デスクトップの背景画像を使用して変更を元に戻す手順を示します。 

**変更を元に戻すには**
1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする
2. [**設定**] で、[**構成可能**] を選択します。
3. [**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。
4. **この変更を元に戻す必要がある**場合は、[**展開を元に戻す**] を選択します。

![構成可能な設定の展開の復元](images/config-setting-revert.png) 

## <a name="additional-resources"></a>その他のリソース
- [構成可能な設定の概要](config-setting-overview.md)
- [構成可能な設定のリファレンス](config-setting-ref.md) 
