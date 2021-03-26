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
description: セルフサービス のパスワード リセット ツールを使用してパスワードをリセットする方法について学習します。
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222125"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

Microsoft 365 管理者は、セルフサービス のパスワード[](https://go.microsoft.com/fwlink/p/?LinkId=522677)リセット ツールを使用して、パスワードをリセットする必要がなさそう。 仕事が少ない!
  
## <a name="before-you-begin"></a>はじめに
  
- Microsoft 365 のビジネス、教育、または非営利の有料プランで、クラウド ユーザーのセルフサービス パスワードリセットを無料で受け取る。 Microsoft 365 試用版では動作しません。

- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。

- **オンプレミスの Active Directory を使用** している場合、上記の 2 つの点は適用されません。 むしろ、これを設定できますが、 **有料のサブスクリプションが必要** です Azure AD Premium .

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。

## <a name="watch-let-users-reset-their-own-passwords"></a>ウォッチ: ユーザーが自分のパスワードをリセットする

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="steps-let-people-reset-their-own-passwords"></a>手順: ユーザーが自分のパスワードをリセットする

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。
  
::: moniker range="o365-worldwide"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">で、[</a>設定組織の設定 **]** > **ページに移動** します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>設定セキュリティのプライバシー **]** \> **ページ &amp; に移動** します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>設定] [セキュリティのプライバシー **]** \>  \> **ページ &amp; に移動** します。

::: moniker-end

2. [組織の設定] ページ **の上部で** 、[セキュリティ] タブ **&選択** します。
  
3. [セルフサービス **パスワードのリセット] を選択します**。

4. [ **セルフサービス パスワードのリセット] で**、[Azure portal に移動] を選択してセルフサービス **パスワードのリセットを有効にします**。

5. 左側のナビゲーション ウィンドウで、[ **ユーザー**] を選択し、[ユーザー] ウィンドウ **で [ユーザー] |[すべてのユーザー]** ページで、[パスワードの **リセット] を選択します**。
  
6. [プロパティ **] ページで** 、[ **すべて** ] を選択して、ビジネスのすべてのユーザーに対して有効にし、[保存] を **選択します**。
  
7. ユーザーがサインインすると、今後のパスワードのリセットに役立つ追加情報を入力するように求められます。

## <a name="related-content"></a>関連コンテンツ

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)

[有効期限が切れないように個別のユーザーのパスワードを設定する](set-password-to-never-expire.md)

[Microsoft 365 Business のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
