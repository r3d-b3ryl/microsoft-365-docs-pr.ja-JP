---
title: 管理センターの microsoft 365 レポート-Microsoft Office のライセンス認証
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
description: Office ライセンス認証レポートを取得して、Office サブスクリプションをアクティブ化したユーザーを確認し、追加のヘルプが必要になる可能性のあるユーザーを特定する方法について説明します。
ms.openlocfilehash: 1247b3ce9b055a3e7dc9f75bee6a072787c1a890
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611927"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>管理センターの microsoft 365 レポート-Microsoft Office のライセンス認証

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
[Office ライセンス認証] レポートでは、Office サブスクリプションのライセンス認証を行ったユーザーを少なくとも 1 台のデバイスで確認できます。 エンタープライズ、プロジェクト、Visio Pro for Office 365 のサブスクリプションのライセンス認証のための Microsoft 365 アプリ、およびデスクトップとデバイス間でのライセンス認証の内訳について説明します。 このレポートは、Office サブスクリプションのライセンス認証について、追加のヘルプやサポートが必要なユーザーを特定するときにも役立ちます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、Teams サービス、Teams 通信、または Skype for Business 管理者のグローバル管理者、グローバル閲覧者またはレポート閲覧者である必要があります。  
  
## <a name="how-to-get-to-the-office-activations-report"></a>Office ライセンス認証レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページから、Office ライセンス認証カードの [ **詳細表示** ] ボタンをクリックします。
  
## <a name="interpret-the-office-activations-report"></a>Office ライセンス認証レポートを解釈する
  
[ **アクティブ** 化] タブを選択すると、Office 365 レポートのライセンス認証を表示できます。<br/>![Microsoft 365 レポート-Microsoft Office 365 ライセンス認証。](../../media/e1df82a2-3336-4b38-b66c-b286c44b82ee.png)

レポートに列を追加または削除するには、[ **列の選択** ] を選択します。  <br/> ![Office 365 ライセンス認証レポート-列の選択](../../media/d11a0efa-a067-4440-a4f3-71b618a90301.png)

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。 

|アイテム|説明|
|:-----|:-----|
|**測定基準**|**定義**|
|ユーザー名  <br/> |ユーザーの電子メール アドレス。  <br/> |
|表示名  <br/> |ユーザーの完全な名前。  <br/> |
|製品のライセンス  <br/> |このユーザーに割り当てられている製品。  <br/> |
|最後にアクティブ化された日付 (UTC)  <br/> |ユーザーがデスクトップまたはデバイスで Office をライセンス認証した日付。  <br/> |
|Windows コンピューターでのライセンス認証  <br/> |ユーザーが Office のライセンス認証を行った Windows デスクトップの数。  <br/> |
|Mac コンピューターでのライセンス認証 <br/> |ユーザーが Office のライセンス認証を行った Mac デスクトップの数。|
|Windows 10 の電話とタブレットでのライセンス認証  <br/> |ユーザーが Office のライセンス認証を行った Windows 10 モバイルデバイスの数。  <br/> |
|IOS 電話とタブレットでのライセンス認証  <br/> |ユーザーが Office のライセンス認証を行った iOS デバイスの数。|
|Android フォンおよびタブレットでのライセンス認証  <br/> |ユーザーが Office のライセンス認証を行った Android デバイスの数。  <br/> |
|共有コンピューターのライセンス認証の使用 |これは、ユーザーが共有コンピューターのライセンス認証を使用して Office を使用した場合に当てはまります。|
|||
   