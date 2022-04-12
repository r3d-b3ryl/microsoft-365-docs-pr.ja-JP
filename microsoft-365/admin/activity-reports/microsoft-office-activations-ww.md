---
title: Microsoft 365 管理センター Officeライセンス認証レポート
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
description: Officeライセンス認証レポートを取得して、どのユーザーがOfficeサブスクリプションをアクティブ化したかを把握し、追加のヘルプが必要な可能性があるユーザーを特定する方法について説明します。
ms.openlocfilehash: 02d397aaaa254ffe9745832682e5e60b0917e23a
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781799"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>管理センターでレポートをMicrosoft 365する - ライセンス認証をMicrosoft Officeする

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
[Office ライセンス認証] レポートでは、Office サブスクリプションのライセンス認証を行ったユーザーを少なくとも 1 台のデバイスで確認できます。 Microsoft 365 Apps for enterprise、Project、Visio Pro for Office 365サブスクリプションのライセンス認証の内訳と、デスクトップとデバイス間のアクティブ化の内訳が提供されます。 このレポートは、Office サブスクリプションのライセンス認証について、追加のヘルプやサポートが必要なユーザーを特定するときにも役立ちます。
  
## <a name="how-to-get-to-the-office-activations-report"></a>Office ライセンス認証レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、Officeライセンス認証カードの [**その他の表示**] ボタンをクリックします。
  
## <a name="interpret-the-office-activations-report"></a>Office ライセンス認証レポートを解釈する
  
[アクティブ化] タブを選択すると、Office 365 レポートで **アクティブ化** を表示できます。<br/>![Microsoft 365 レポート - アクティブ化Microsoft Office 365。](../../media/e1df82a2-3336-4b38-b66c-b286c44b82ee.png)

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> ![アクティブ化レポートOffice 365 - 列を選択します。](../../media/d11a0efa-a067-4440-a4f3-71b618a90301.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|Username  <br/> |ユーザーの電子メール アドレス。  <br/> |
|表示名  <br/> |ユーザーの完全な名前。  <br/> |
|製品のライセンス  <br/> |このユーザーに割り当てられている製品。  <br/> |
|最後にアクティブ化された日付 (UTC)  <br/> |ユーザーがデスクトップまたはデバイスでOfficeアクティブ化した日付。  <br/> |
|Windows コンピューターでのアクティブ化  <br/> |ユーザーがアクティブ化Office Windows デスクトップの数。  <br/> |
|Mac コンピューターでのアクティブ化 <br/> |ユーザーがアクティブ化した Mac デスクトップの数Office。|
|Windows 10スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーがアクティブ化したモバイル デバイスのWindows 10数Office。  <br/> |
|iOS スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーがアクティブ化した iOS デバイスの数Office。|
|Android スマートフォンとタブレットでのアクティブ化  <br/> |ユーザーがアクティブ化した Android デバイスの数Office。  <br/> |
|共有コンピューターのライセンス認証を使用しました |これは、ユーザーが共有コンピューターのライセンス認証を通じてOfficeを使用した場合に当てはまります。|
|||
   