---
title: ユーザーが自分でパスワードをリセットできるようにする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスパスワード リセット ツールを使用して、ユーザーが自分のパスワードをリセットできるようにポリシーを設定する方法について説明します。
ms.openlocfilehash: e72d4815be5486f8f7df362b5b93cae988b7df63
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765386"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

Microsoft 365管理者は、ユーザーが[セルフサービスパスワード リセット ツール](https://go.microsoft.com/fwlink/p/?LinkId=522677)を使用できるようにします。そのため、ユーザーのパスワードをリセットする必要はありません。 より少ない作業が必要です。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。
 
## <a name="watch-let-users-reset-their-own-passwords"></a>ウォッチ: ユーザーが自分のパスワードをリセットできるようにする

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**設定** > **Org 設定**、および <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**セキュリティ &プライバシー**</a>を選択します。
1. [**ユーザーが自分のパスワードをリセットできるようにする**] で、**管理センター Azure AD** 選択します。
1. 左側のナビゲーション ウィンドウで [ **ユーザー**] を選択し、[ **ユーザー - すべてのユーザー** ] ページで [ **パスワードリセット**] を選択します。
1. **[すべて**] を選択してセルフサービスのパスワード リセットを有効にし、[保存] を選択 **します**。

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。
 
## <a name="before-you-begin"></a>はじめに
  
- クラウド ユーザーのセルフサービス パスワード リセットは、Microsoft 365ビジネス、教育機関、非営利団体向けの有料プランで **無料** で取得できます。 Microsoft 365試用版では機能しません。

- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。

- **オンプレミスの Active Directoryを使用している場合** は、上記の 2 つの点は適用されません。 代わりに、これを設定できますが、**Azure AD Premiumには有料サブスクリプションが必要です**。

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは何ですか?(Microsoft 365 管理センターの概要](../admin-overview/admin-center-overview.md)

これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

## <a name="steps-let-people-reset-their-own-passwords"></a>手順: ユーザーが自分のパスワードをリセットできるようにする

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>で、**設定** > **Org 設定** ページに移動します。

2. **[組織の設定]** ページの上部にある [**セキュリティ&プライバシー**] タブを選択します。
  
3. **[セルフサービス パスワード リセット**] を選択します。

4. **[セルフサービス パスワード リセット**] で、[**Azure portalに移動] を選択して、セルフサービスのパスワード リセットを有効にします**。

5. **[プロパティ**] ページで、[**すべて**] を選択してビジネスのすべてのユーザーに対して有効にし、[保存] を選択 **します**。
  
6. ユーザーがサインインすると、今後パスワードをリセットするのに役立つ追加の連絡先情報を入力するように求められます。

## <a name="related-content"></a>関連コンテンツ

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)\
[個別のユーザーのパスワードを無期限に設定する](set-password-to-never-expire.md) (記事)\
[Microsoft 365 Business トレーニング ビデオ](../../business-video/index.yml) (リンク ページ)
