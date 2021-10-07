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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービス のパスワードリセット ツールを使用して、ユーザーが自分のパスワードをリセットできるポリシーを設定する方法について学習します。
ms.openlocfilehash: a30c32239cb1c995beaaf725aaf5dc3821beec8e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161776"
---
# <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

管理者Microsoft 365、ユーザーがセルフサービス のパスワードリセット ツールを使用[](https://go.microsoft.com/fwlink/p/?LinkId=522677)して、パスワードをリセットする必要がなさそう。 仕事が少ない!
  
## <a name="before-you-begin"></a>はじめに
  
- クラウド ユーザーのセルフサービス パスワード リセットは、ビジネス、教育、または非営利の有料プランMicrosoft 365無料で取得できます。 この機能は、試用版ではMicrosoft 365しません。

- この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。

- **オンプレミスの Active Directory を使用** している場合、上記の 2 つの点は適用されません。 むしろ、これを設定できますが、この設定には有料サブスクリプションが **必要** Azure AD Premium。

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../../business-video/admin-center-overview.md)

これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。

## <a name="watch-let-users-reset-their-own-passwords"></a>ウォッチ: ユーザーが自分のパスワードをリセットする

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。

## <a name="steps-let-people-reset-their-own-passwords"></a>手順: ユーザーが自分のパスワードをリセットする

次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">で、[</a>組織の設定]**ページ設定**  >  **移動** します。

2. [組織の設定] ページ **の上部で** 、[セキュリティ] タブ **&選択** します。
  
3. [セルフサービス **パスワードのリセット] を選択します**。

4. [ **セルフサービス パスワードのリセット] で**、[Azure portal に移動] を選択してセルフサービス **パスワードのリセットを有効にします**。

5. [プロパティ **] ページで** 、[ **すべて** ] を選択して、ビジネスのすべてのユーザーに対して有効にし、[保存] を **選択します**。
  
6. ユーザーがサインインすると、今後のパスワードのリセットに役立つ追加情報を入力するように求められます。

## <a name="related-content"></a>関連コンテンツ

[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)\
[個別のユーザーのパスワードを無期限に設定する](set-password-to-never-expire.md) (記事)\
[Microsoft 365 ビジネス トレーニング ビデオ](../../business-video/index.yml)(リンク ページ)
