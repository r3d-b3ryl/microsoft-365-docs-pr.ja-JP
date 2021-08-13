---
title: Microsoft 365管理センターのレポート - Microsoft Officeアクティブ化
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 87c24ae2-82e0-4d1e-be01-c3bcc3f18c60
description: ライセンス認証レポートを取得して、Officeサブスクリプションをアクティブ化したユーザーを知り、追加のOffice必要なユーザーを特定する方法について学習します。
ms.openlocfilehash: ee803dece4e66ede794677b99b3d27de29b53aed11ab590486b1a7bcd1a6c78b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53797890"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>Microsoft 365管理センターのレポート - Microsoft Officeアクティブ化

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
[Office ライセンス認証] レポートでは、Office サブスクリプションのライセンス認証を行ったユーザーを少なくとも 1 台のデバイスで確認できます。 このサービスは、Microsoft 365 Apps for enterprise、Project、Visio Pro for Office 365サブスクリプションのライセンス認証の内訳と、デスクトップとデバイス全体のライセンス認証の内訳を提供します。 このレポートは、Office サブスクリプションのライセンス認証について、追加のヘルプやサポートが必要なユーザーを特定するときにも役立ちます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル閲覧者、レポート閲覧者、または Exchange、SharePoint、Skype for Business の管理者である必要があります。  
  
## <a name="how-to-get-to-the-office-activations-report"></a>Office ライセンス認証レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、[アクティブ化]**カードの**[その他の表示] Officeクリックします。
  
## <a name="interpret-the-office-activations-report"></a>Office ライセンス認証レポートを解釈する
  
[ライセンス認証] タブを選択すると、Office 365レポートでライセンス認証 **を表示** できます。<br/>![Microsoft 365レポート - ライセンス認証Microsoft Office 365します。](../../media/e1df82a2-3336-4b38-b66c-b286c44b82ee.png)

[列 **の選択]** を選択して、レポートの列を追加または削除します。  <br/> ![Office 365アクティブ化レポート - 列を選択する](../../media/d11a0efa-a067-4440-a4f3-71b618a90301.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。  <br/> |
|表示名  <br/> |ユーザーの完全な名前。  <br/> |
|製品のライセンス  <br/> |このユーザーに割り当てられている製品。  <br/> |
|最後にアクティブ化された日付(UTC)  <br/> |ユーザーがデスクトップまたはデバイスOfficeユーザーがアクティブ化した日付。  <br/> |
|コンピューターでのWindowsアクティブ化  <br/> |ユーザーがアクティブWindowsデスクトップの数Officeします。  <br/> |
|Mac コンピューターでのライセンス認証 <br/> |ユーザーがアクティブ化した Mac デスクトップの数Officeします。|
|携帯電話とタブレットWindows 10ライセンス認証  <br/> |ユーザーがアクティブWindows 10モバイル デバイスの数Officeします。  <br/> |
|iOS 電話とタブレットでのライセンス認証  <br/> |ユーザーがアクティブ化した iOS デバイスの数Officeします。|
|Android スマートフォンとタブレットでのライセンス認証  <br/> |ユーザーがアクティブ化した Android デバイスのOfficeします。  <br/> |
|使用された共有コンピューターのライセンス認証 |これは、ユーザーが共有コンピューターのライセンス認証をOffice場合に当てはまる。|
|||
   