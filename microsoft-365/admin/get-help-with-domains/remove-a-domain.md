---
title: ドメインを削除する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: ユーザーから古いドメインを削除し、Microsoft 365別のドメインに移動するか、サブスクリプションをキャンセルする方法について学習します。
ms.openlocfilehash: 6b572adb5d1ed45be473552e74adb25c54b3cae7
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775422"
---
# <a name="remove-a-domain"></a>ドメインを削除する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

別のサブスクリプション プランにドメインを追加する場合、ドメインをMicrosoft 365しますか? それとも、サブスクリプションをキャンセルするためですか? [プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。

### <a name="step-1-move-users-to-another-domain"></a>手順 1: ユーザーを別のドメインに移動する

#### <a name="move-users"></a>ユーザーの移動

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

2. **[ユーザー]** > **[アクティブ ユーザー]** の順に選択します。

3. 移動するすべてのユーザーの名前の横にあるボックスを選択します。

4. ページの上部で、[ドメインの変更] **を選択します**。

5. [ドメイン **の変更] ウィンドウで** 、別のドメインを選択します。

削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。

#### <a name="move-yourself"></a>自分を移動する

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

2. [ユーザーの **アクティブ** \> **なユーザー]** に移動し、一覧からアカウントを選択します。

3. [アカウント **] タブで** 、[ユーザー名の **管理] を選択** し、別のドメインを選択します。

4. 上部でアカウント名を選択し、[サインアウト] **を選択します**。

5. 新しいドメインと同じパスワードでサインインします。

また、PowerShell を使用してユーザーを別のドメインに移動することもできます。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。

### <a name="step-2-move-groups-to-another-domain"></a>手順 2: グループを別のドメインに移動する

::: moniker range="o365-worldwide"

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

::: moniker-end
::: moniker range="o365-germany"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>グループ グループ] **ページ** > **に移動** します。

::: moniker-end

2. グループ名を選択し、[メール アドレス] の [全般] タブの **[** プライマリ] で、[編集] を **選択します**。

3. ドロップダウン リストを使用して別のドメインを選択します。

4. [**保存**]、[**閉じる**] の順に選びます。 削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。

### <a name="step-3-remove-the-old-domain"></a>手順 3: 古いドメインを削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。

::: moniker-end

2. [ドメイン **] ページ** で、削除するドメインを選択します。

3. 右側のウィンドウで、[削除] を **選択します**。

4. 追加のプロンプトに従って、[閉じる] を **選択します**。

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>ドメインが削除されるまで、どれくらいかかりますか?

Microsoft 365 がセキュリティ グループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するにはわずか 5 分かかります。 ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。

数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。

## <a name="still-need-help"></a>さらにヘルプが必要ですか?

::: moniker range="o365-worldwide"

> [!NOTE]
> アカウントから [".onmicrosoft.com"](../setup/domains-faq.yml) ドメインを削除することはできません。 ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.com" アドレスに戻されます。

それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md)、お手伝いいたします。

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> アカウントから [".onmicrosoft.de"](../setup/domains-faq.yml) ドメインを削除することはできません。 ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.de" アドレスに戻されます。

それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true)、お手伝いいたします。

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> アカウントから [".partner.onmschina.cn"](../setup/domains-faq.yml) ドメインを削除することはできません。 ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".partner.onmschina.cn" アドレスに戻されます。

それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true)、お手伝いいたします。

::: moniker-end

## <a name="related-content"></a>関連コンテンツ

[ドメインの FAQ](../setup/domains-faq.yml) (記事)

[ビジネス プランの別のMicrosoft 365に切り替える](../../commerce/subscriptions/switch-to-a-different-plan.md)(記事)

[サブスクリプションをキャンセルする](../../commerce/subscriptions/cancel-your-subscription.md) (記事)
