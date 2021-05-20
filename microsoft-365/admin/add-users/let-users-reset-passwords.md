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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスパスワードリセットツールを使用して、ユーザーが自分のパスワードをリセットできるようにポリシーを設定する方法について説明します。
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571855"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

管理者Microsoft 365、[セルフサービスのパスワードリセットツール](https://go.microsoft.com/fwlink/p/?LinkId=522677)を使用してパスワードをリセットする必要がないようにすることができます。 あなたのために少ない仕事!
  
## <a name="before-you-begin"></a>始める前に
  
- クラウドユーザーのセルフサービスパスワードリセットは、ビジネス、教育、または非営利団体の有料プランMicrosoft 365 **無料** で取得できます。 それはMicrosoft 365トライアルでは動作しません。

- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。

- **オンプレミスの Active Directory を使用している場合、** 上記の 2 つのポイントは適用されません。 代わりに、これを設定できますが **、Azure AD プレミアム への有料サブスクリプションが必要です**。

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../../business-video/admin-center-overview.md)

これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。

## <a name="watch-let-users-reset-their-own-passwords"></a>ウォッチ: ユーザーが自分のパスワードをリセットできるようにする

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。

## <a name="steps-let-people-reset-their-own-passwords"></a>手順: ユーザーが自分のパスワードをリセットできるようにする

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>の [組織の **設定設定]**  >  ページ **に** 移動します。

2. [ **組織の設定]** ページの上部にある [ **セキュリティ&プライバシー** ] タブを選択します。
  
3. [ **セルフサービスパスワードのリセット]** を選択します。

4. [ **セルフサービス パスワードのリセット**] で **、[Azure Portal に移動してセルフサービス パスワードのリセットを有効にする**] を選択します。

5. 左側のナビゲーション ウィンドウで [ **ユーザー**] を選択し、[ユーザー] **|[すべてのユーザー** ] ページで、[ **パスワードのリセット**] を選択します。
  
6. [ **プロパティ]** ページで [ **すべて** ] を選択して、ビジネスのすべてのユーザーに対して有効にし、[ **保存**] を選択します。
  
7. ユーザーがサインインすると、将来パスワードをリセットするのに役立つ追加の連絡先情報を入力するよう求められます。

## <a name="related-content"></a>関連コンテンツ

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)

[個別のユーザーのパスワードを無期限に設定する](set-password-to-never-expire.md) (記事)

[Microsoft 365 Businessトレーニングビデオ](../../business-video/index.yml)(リンクページ)
