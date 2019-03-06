---
title: Microsoft マネージドデスクトップで構成可能な設定を展開する
description: Microsoft マネージドデスクトップで構成の構成変更を展開し、追跡します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、展開、段階的展開、構成可能な設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414171"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>構成可能な設定を展開および追跡する-Microsoft マネージドデスクトップ

設定カテゴリを変更し、展開をステージすると、展開の状態に応じて展開の進行状況を展開し、追跡することができます。 このページには、各構成可能な設定の概要が表示されます。 [設定] カテゴリを開き、各展開とその詳細を表示して、変更を展開します。 

## <a name="deployment-statuses"></a>展開の状態 

これらの statues は、展開ごとに表示されます。

Status  | 説明 
--- | --- 
展開 | 変更は、このリングへの展開を待機しています。
処理中 | このリングのアクティブなデバイスに変更が適用されています。 
Complete | このリングのすべてのアクティブなデバイスで変更が完了しました。 
Failed | この変更は、呼び出しが停止されたために、リング内のアクティブなデバイスの 10% で失敗しました。<br><br> 展開のトラブルシューティングを行うために、サポート要求が Microsoft マネージドデスクトップ操作を使用して自動的に開かれます。 
復帰 | 変更は、すべての展開リングに正常に展開された最後の変更に戻されました。

## <a name="deploy-changes"></a>変更を展開する

これらの手順にデスクトップの背景画像が表示されます。 展開をステージングした後、展開状態から変更を展開します。 

**変更を展開するには**

1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする
2. [**設定**] で、[**構成可能**] を選択します。
3. [**展開状態**] ワークスペースで、展開する設定を選択し、展開する段階的展開を選択します。
4. 展開リングのいずれかに変更を展開するには、[**展開**] を選択します。

![構成可能な設定の展開状態の概要](images/deploy-cs-overview.png)

Microsoft マネージドデスクトップでは、次の順序で展開リングに展開することをお勧めします。 Test、First、Fast、および広範。 

各リングで変更が完了すると、状態は [**完了**] に変わります。

![構成可能な設定の展開の完了](images/config-setting-complete.png)

## <a name="revert-deployment"></a>展開を元に戻す

これらの手順にデスクトップの背景画像が表示されます。 

変更を展開した後、**展開状態**から元に戻すことができます。 **進行**中または**完了**した変更を元に戻すと、現在の展開は停止します。 この設定は、すべてのリングに展開された最新のバージョンに戻ります。 

**変更を元に戻すには**
1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインする
2. [**設定**] で、[**構成可能**] を選択します。
3. [**展開状態**] ワークスペースで、元に戻す設定を選択してから、元に戻す段階的な展開を選択します。
4. **この変更を元に戻す必要がある**場合は、[**展開を元に戻す**] を選択します。

![構成可能な設定の展開の復元](images/config-setting-revert.png) 

## <a name="additional-resources"></a>その他の技術情報
- [構成可能な設定の概要](config-setting-overview.md)
- [構成可能な設定のリファレンス](config-setting-ref.md) 