---
title: Microsoft Managed Desktop で構成可能な設定を展開する
description: Microsoft Managed Desktop で構成可能な設定の変更を展開および追跡します。
keywords: Microsoft Managed Desktop, Microsoft 365, サービス, ドキュメント, 展開, ステージ展開, 構成可能な設定
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 9933731fa550bc7ef5df567920e97f9f6559e7f8
ms.sourcegitcommit: 2c3b737e71038f843ef9e9ff4d5b99d6110b8ec5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2022
ms.locfileid: "62265633"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>構成可能な設定の展開と追跡 - Microsoft Managed Desktop

設定カテゴリに変更を加え、展開をステージした後、[展開状態] ページでは、グループへの設定の展開を開始できます。 このページには、構成可能な各設定の概要が表示されます。 設定カテゴリを開く場合は、グループに設定を展開し、これらの展開の進行状況を追跡できます。

## <a name="deployment-statuses"></a>展開の状態

展開ごとに表示される状態を次に示します。

状態 | 説明
--- | ---
展開 | 変更がこのグループに展開されるのを待っています。
処理中 | 変更は、このグループのアクティブ なデバイスに適用されています。
完了 | このグループ内のすべてのアクティブ なデバイスで変更が完了しました。
失敗 | グループ内のアクティブ なデバイスの 10% で変更が失敗しました。 展開が停止しました。<br><br> Microsoft Managed Desktop 操作でサポート要求が自動的に開き、展開のトラブルシューティングが行われます。
元に戻す | この変更は、すべての展開グループに正常に展開された最後の変更に戻されました。

## <a name="deploy-changes"></a>変更の展開

例として、以下の手順でデスクトップの背景画像を使用します。 展開をステージした後、[展開の状態] ページから変更を展開します。

**変更を展開するには、次の方法を実行します。**

1. サインインして[デバイス [] Microsoft エンドポイント マネージャー[](https://endpoint.microsoft.com/)デバイス] メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションで、[デスクトップ]**を設定。**
3. [展開 **状態] ワークスペース** で、展開する設定を選択します。 次に、展開するステージ展開を選択します。
4. [ **展開] を** 選択して、変更を展開グループの 1 つに展開します。

> [!NOTE]
> オレンジ色の注意アイコンは、展開に使用できる以前のグループが用意されているのを示します。順番にロールアウトする必要があります。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

この順序で展開グループに展開することをお勧めします。Test、First、Fast、次に Broad。

各グループの変更が完了すると、状態は [完了] に **変わります**。

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>展開を元に戻す

変更を展開した後、展開の状態から **元に戻します**。 [進行中] または [完了] **の変更を** 元に戻 **す** 場合、現在の展開は停止します。 この設定は、すべてのグループに展開された最後のバージョンに戻されます。

例として、デスクトップの背景画像を元に戻します。

**変更を元に戻すには、次の操作を行います。**

1. サインインして[デバイス [] Microsoft エンドポイント マネージャー[](https://endpoint.microsoft.com/)デバイス] メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションで、[デスクトップ]**を設定。**
3. [展開 **状態] ワークスペース** で、元に戻す設定を選択します。 次に、元に戻すステージ展開を選択します。
4. [ **この変更を元に戻す必要がある] で、[** 展開を元に **戻す] を選択します**。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>その他のリソース

- [構成可能な設定の概要](config-setting-overview.md)
- [構成可能な設定のリファレンス](config-setting-ref.md)
