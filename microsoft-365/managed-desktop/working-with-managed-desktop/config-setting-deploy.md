---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104536"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ

設定カテゴリを変更し、展開をステージした後、[展開の状態] ページで、グループへの設定の展開を開始できます。 このページには、各構成可能な設定の概要が表示されます。 [設定] カテゴリを開くと、設定をグループに展開し、これらの展開の進行状況を追跡することができます。

## <a name="deployment-statuses"></a>展開の状態 

展開ごとに表示される状態を次に示します。

状態  | 説明 
--- | --- 
展開 | 変更は、このグループへの展開を待機しています。
処理中 | このグループ内のアクティブなデバイスに変更が適用されています。 
完了 | このグループ内のすべてのアクティブなデバイスで変更が完了しました。 
失敗 | グループ内のアクティブなデバイスの10% で変更が失敗したため、展開が停止されました。<br><br> 展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。 
復帰 | 変更は、すべての展開グループに正常に展開された最後の変更に戻されました。

## <a name="deploy-changes"></a>変更を展開する

これらの手順にデスクトップの背景画像が表示されます。 展開をステージングした後、[展開の状態] ページから変更を展開します。 

**変更を展開するには**

1. [Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)にサインインして、[**デバイス**] メニューに移動します。
2. [Microsoft Managed Desktop] セクションを探し、[ **設定**] を選択します。
3. [ **展開状態** ] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。
4. 展開グループのいずれかに変更を展開するには、[ **展開** ] を選択します。

> [!NOTE] 
> オレンジ色の警告アイコンは、展開に使用できる前のグループがあることを示しています。これは、順序どおりに展開することをお勧めします。 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

展開グループへの展開は、次の順序で行うことをお勧めします。 Test、First、Fast、および広義です。 

各グループで変更が完了すると、状態が [ **完了**] に変わります。

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>展開を元に戻す

変更を展開した後、 **展開状態**から元に戻すことができます。 **進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。 この設定は、すべてのグループに展開された最新のバージョンに戻ります。 

デスクトップの背景画像を使用して変更を元に戻す手順を示します。 

**変更を元に戻すには**
1. [Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)にサインインして、[**デバイス**] メニューに移動します。
2. [Microsoft Managed Desktop] セクションを探し、[ **設定**] を選択します。
3. [ **展開状態** ] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。
4. [ **この変更を元に戻す必要がありますか?**] で、[ **展開の取り消し**] を選択します。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>その他のリソース
- [構成可能な設定の概要](config-setting-overview.md)
- [構成可能な設定のリファレンス](config-setting-ref.md) 
