---
title: Office ライセンス認証レポートをMicrosoft 365 管理センターする
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Office ライセンス認証レポートを取得して、Office サブスクリプションをアクティブ化したユーザーを確認し、追加のヘルプが必要なユーザーを特定する方法について説明します。
ms.openlocfilehash: b859aace7ee0c71fb6d162b27ec7b7bc81a00208
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66663154"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>管理センターの Microsoft 365 レポート - Microsoft Office ライセンス認証

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
[Office ライセンス認証] レポートでは、Office サブスクリプションのライセンス認証を行ったユーザーを少なくとも 1 台のデバイスで確認できます。 Microsoft 365 Apps for enterprise、Project、Visio Pro for Office 365サブスクリプションのライセンス認証の内訳と、デスクトップとデバイス間のアクティブ化の内訳が提供されます。 このレポートは、Office サブスクリプションのライセンス認証について、追加のヘルプやサポートが必要なユーザーを特定するときにも役立ちます。
  
## <a name="how-to-get-to-the-office-activations-report"></a>Office ライセンス認証レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Office ライセンス認証カードの [ **その他の表示** ] ボタンをクリックします。
  
## <a name="interpret-the-office-activations-report"></a>Office ライセンス認証レポートを解釈する
  
[アクティブ化] タブを選択すると、Office 365 レポートで **アクティブ化** を表示できます。<br/>![Microsoft 365 レポート - アクティブ化Microsoft Office 365。](../../media/e1df82a2-3336-4b38-b66c-b286c44b82ee.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  

![アクティブ化レポートOffice 365 - 列を選択します。](../../media/d11a0efa-a067-4440-a4f3-71b618a90301.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。  <br/> |
|表示名  <br/> |ユーザーの完全な名前。  <br/> |
|製品のライセンス  <br/> |このユーザーに割り当てられている製品。  <br/> |
|最後にアクティブ化された日付 (UTC)  <br/> |ユーザーがデスクトップまたはデバイスで Office をアクティブ化した日付。  <br/> |
|Windows コンピューターでのアクティブ化  <br/> |ユーザーが Office をアクティブ化した Windows デスクトップの数。  <br/> |
|Mac コンピューターでのアクティブ化 <br/> |ユーザーが Office をアクティブ化した Mac デスクトップの数。|
|Windows 10スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーが Office をアクティブ化したモバイル デバイスWindows 10数。  <br/> |
|iOS スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーが Office をアクティブ化した iOS デバイスの数。|
|Android スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーが Office をアクティブ化した Android デバイスの数。  <br/> |
|共有コンピューターのライセンス認証を使用しました |これは、ユーザーが共有コンピューターのライセンス認証を通じて Office を使用した場合に当てはまります。|
|||
   