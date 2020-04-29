---
title: ユーザーが自分でパスワードをリセットできるようにする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスのパスワードリセットツールを使用してパスワードをリセットする方法について説明します。
ms.openlocfilehash: 9d9a1f97f9f6fc59b54f2f9bdce9c337c7d57b13
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919437"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

パスワードのリセットを求められるユーザーとの間でクラッシュしますか? Microsoft 365 管理者は、[セルフサービスのパスワードリセットツール](https://go.microsoft.com/fwlink/p/?LinkId=522677)を使用して、ユーザーのパスワードをリセットする必要がないようにすることができます。 作業が少なくてすみます。 
  
以下の点を知っておく必要があります。
  
- Microsoft 365 business、エデュケーション、または非営利**団体の有料プランを使用し**て、クラウドユーザーのセルフサービスのパスワードリセットを利用できます。 Microsoft 365 の試用版では動作しません。 
    
- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。 
    
- **オンプレミスの Active Directory を使用している場合**は、上の2つのポイントは適用されません。 代わりに、これを設定できますが、 **AZURE AD Premium への有料サブスクリプションが必要**です。 

ユーザーが自分のパスワードをリセットできるようにするための短いビデオをご覧ください。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="let-people-reset-their-own-passwords"></a>ユーザーが自分のパスワードをリセットできるようにする 

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。
  
::: moniker range="o365-worldwide"
1.  管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**設定** \> **セキュリティ&amp;プライバシー** ] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**設定** \>の**設定** \> ] [**セキュリティ&amp;プライバシー** ] ページに移動します。

::: moniker-end

   
2. [**セルフサービスのパスワードのリセット**] を選択し、[ **Azure portal に移動**] のリンクを選択して、セルフサービスのパスワードのリセットを有効にします。 無料で Azure を取得できます。
  
3. 左側のナビゲーションで [**ユーザー** ] を選択し、[**パスワードのリセット**] を選択します。
  
4. [プロパティ] ページで、[**すべて**] を選択して、会社のすべてのユーザーに対して有効にし、[**保存**] を選択します。
  
5. Office 365 にサインインするユーザーは、将来自分のパスワードを再設定する場合に役立つ追加の連絡先情報を入力するように求められます。

## <a name="related-articles"></a>関連記事

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)
  
[有効期限が切れないように個別のユーザーのパスワードを設定する](set-password-to-never-expire.md)

[Microsoft 365 Business のトレーニング ビデオ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
