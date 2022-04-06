---
title: ドメインを削除する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365 から古いドメインを削除し、ユーザーとグループを別のドメインに移動する方法、またはサブスクリプションをキャンセルする方法を学びます。
ms.openlocfilehash: 3da47275e090296c9b192b4bd60ad19dd8cf4149
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316829"
---
# <a name="remove-a-domain"></a>ドメインを削除する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

ドメインを削除しているのは、別の Office 365 サブスクリプション プランにドメインを追加するためですか? それとも、サブスクリプションをキャンセルするためですか? [プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

### <a name="step-1-move-users-to-another-domain"></a>手順 1: ユーザーを別のドメインに移動する

#### <a name="move-users"></a>ユーザーの移動

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

2. **[ユーザー]** > **[アクティブ ユーザー]** の順に選択します。

3. 移動するユーザー名の横のチェック ボックスを選択します。

4. ページの上部で、**[ドメインの変更]** を選択します。

5. **[ドメインの編集]** ウィンドウで、別のドメインを選択します。

削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。

#### <a name="move-yourself"></a>自分を移動する

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。

::: moniker-end

2. **[ユーザー]**\>**[アクティブユーザー]** の順に移動し、リストからアカウントを選択します。

3. **[アカウント]** タブで、**[ユーザー名の管理]** を選択し、別のドメインを選択します。

4. 上部で、自分のアカウント名を選択し、**[サインアウト]** を選択します。

5. 新しいドメインおよび同じパスワードでサインインします。

また、PowerShell を使用してユーザーを別のドメインに移動することもできます。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。

### <a name="step-2-move-groups-to-another-domain"></a>手順 2: グループを別のドメインに移動する

::: moniker range="o365-worldwide"

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センターで</a>、**[グループ]**>**[グループ]** ページの順に移動します。

::: moniker-end

2. グループ名を選択し、**[プライマリ メールアドレス]** の下にある **[全般]** タブで、**[編集]** を選択します。

3. ドロップダウン リストを使用して別のドメインを選択します。

4. **[保存]**、**[閉じる]** の順に選択します。削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。

### <a name="step-3-remove-the-old-domain"></a>手順 3: 古いドメインを削除する

::: moniker range="o365-worldwide"

> [!NOTE]
> カスタム ドメインを削除する場合は、先に進む前に「[カスタム ドメインの削除](#remove-a-custom-domain)」を参照してください。

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**セットアップ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>] ページの順に移動します。

::: moniker-end

2. [**ドメイン**] ページで、削除するドメインを選択します。

3. 右側のウィンドウで、[**削除**] を選択します。

4. 他の指示に従った後、[**閉じる**] を選択します。




### <a name="remove-a-custom-domain"></a>カスタム ドメインを削除する

サブスクリプションでカスタム ドメインを使用している場合、サブスクリプションをキャンセルする前に、いくつかの追加手順を実行する必要があります。 

#### <a name="change-your-domain-nameserver-records-if-needed"></a>ドメインのネームサーバー レコードを変更する (必要な場合)

カスタム ドメインをセットアップすると、ドメインが Microsoft 365 サービスで機能するように、DNS レコードが追加されます。ドメインを削除する前に、DNS ホストでドメインの MX レコードなどの DNS レコードを更新してください。

たとえば、DNS ホストで MX レコードを変更します。ドメインに送信される電子メールは、Microsoft アドレスに送信されなくなり、代わりに新しいメール プロバイダーに送信されます。(MX レコードは、ドメインの電子メールがどこに送信されるかを決定します。)

- ネームサーバー (NS) レコードが [Microsoft 365 ネームサーバーをポイントしている](../../admin/setup/add-domain.md)場合、新しい DNS ホストをポイントするように NS レコードを変更するまでは、MX レコードの変更は有効になりません (手順 2 を参照)。

- MX レコードを更新する前に、電子メールを切り替える日付、使う予定の新しいメール プロバイダーをユーザーに通知します。 また、ユーザーが既存の Microsoft メールを新しいプロバイダーに移行する場合は、追加の手順を実行する必要があります。

- MX レコードを変更した日は、必ず[データを保存](/microsoft-365/commerce/subscriptions/cancel-your-subscription#save-your-data)し、[必要に応じて Office をアンインストール](/microsoft-365/commerce/subscriptions/cancel-your-subscription#uninstall-office-optional)してください。

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>(カスタム ドメインを使用している場合) ドメイン MX レコードとその他の DNS レコードを更新する

ドメインをセットアップするときに、ネームサーバー (NS) レコードを Microsoft 365 に切り替えた場合は、MX レコード、および使用する予定の DNS ホストの他の DNS レコードを設定または更新してから、NS レコードをその DNS ホストに変更する必要があります。

ドメインをセットアップするときに NS レコードを切り替えなかった場合は、MX レコードを変更すると、電子メールがすぐに新しいアドレスに送信されます。

NSレコードを変更するには、「[ネーム サーバーを変更して任意のドメイン レジストラーで Microsoft 365 セットアップする](../../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)」を参照してください。



## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>ドメインが削除されるまで、どれくらいかかりますか?

セキュリティ グループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていなければ、5 分程度で Microsoft 365 からドメインが削除されます。ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。

数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](/powershell/module/msonline/set-msoldomain) を使用します。

## <a name="still-need-help"></a>さらにヘルプが必要ですか?

::: moniker range="o365-worldwide"

> [!NOTE]
> アカウントから [".onmicrosoft.com"](../setup/domains-faq.yml) ドメインを削除することはできません。 ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".onmicrosoft.com" アドレスに戻されます。

それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md)、お手伝いいたします。

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> アカウントから [".partner.onmschina.cn"](../setup/domains-faq.yml) ドメインを削除することはできません。 ドメインを削除すると、ユーザー アカウントはプライマリ SMTP/UserprincipalName として ".partner.onmschina.cn" アドレスに戻されます。

それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true)、お手伝いいたします。

::: moniker-end

## <a name="related-content"></a>関連コンテンツ

[ドメインの FAQ](../setup/domains-faq.yml) (記事)

「[別の一般法人向け Microsoft 365 プランに切り替える](../../commerce/subscriptions/switch-to-a-different-plan.md)」(記事)

[サブスクリプションを解約する](../../commerce/subscriptions/cancel-your-subscription.md) (記事)
