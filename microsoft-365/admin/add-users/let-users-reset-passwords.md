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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスのパスワードリセットツールを使用してパスワードをリセットする方法について説明します。
ms.openlocfilehash: 40f094489a1981302e97043b019e8c90a52ffc55
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678684"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

パスワードのリセットを求められるユーザーとの間でクラッシュしますか? Microsoft 365 管理者は、[セルフサービスのパスワードリセットツール](https://go.microsoft.com/fwlink/p/?LinkId=522677)を使用して、ユーザーのパスワードをリセットする必要がないようにすることができます。 作業が少なくてすみます。 
  
以下の点を知っておく必要があります。
  
- Microsoft 365 business、エデュケーション、または非営利**団体の有料プランを使用し**て、クラウドユーザーのセルフサービスのパスワードリセットを利用できます。 Microsoft 365 の試用版では動作しません。

- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。

- **オンプレミスの Active Directory を使用している場合**は、上の2つのポイントは適用されません。 代わりに、これを設定できますが、 **AZURE AD Premium への有料サブスクリプションが必要**です。

ユーザーが自分のパスワードをリセットできるようにするための短いビデオをご覧ください。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

このビデオがお役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="let-people-reset-their-own-passwords"></a>ユーザーが自分のパスワードをリセットできるようにする

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。
  
::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、[設定] [ **Settings** > **組織の設定**] ページに移動します。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**設定** \> **セキュリティ &amp; プライバシー** ] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**設定**の設定] [ \> **Settings** \> **セキュリティ &amp; プライバシー** ] ページに移動します。

::: moniker-end

2. [**組織の設定**] ページの上部で、[**セキュリティ & プライバシー** ] タブを選択します。
  
3. [**セルフサービスのパスワードのリセット**] を選択します。

4. [**セルフサービスのパスワードのリセット**] で、[ **Azure portal に移動] を選択して、セルフサービスのパスワードのリセットを有効**にします。

5. 左側のナビゲーションウィンドウで [**ユーザー**] を選択し、[**ユーザー |[すべてのユーザー** ] ページで、[**パスワードのリセット**] を選択します。
  
6. [**プロパティ**] ページで、[**すべて**] を選択して、会社のすべてのユーザーに対して有効にし、[**保存**] を選択します。
  
7. ユーザーがサインインすると、今後、パスワードを再設定するのに役立つ追加の連絡先情報を入力するように求めるメッセージが表示されます。

## <a name="related-articles"></a>関連記事

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)
  
[有効期限が切れないように個別のユーザーのパスワードを設定する](set-password-to-never-expire.md)

[Microsoft 365 Business のトレーニング ビデオ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
