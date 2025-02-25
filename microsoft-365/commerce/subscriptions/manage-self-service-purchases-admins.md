---
title: セルフサービス購入の管理 (管理者)
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: prlachhw, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
description: 管理者は、組織内のユーザーが行ったセルフサービス購入を管理する方法を学習できます。
ms.date: 05/24/2022
ms.openlocfilehash: 50d782052839c099f3c64e45cc82a6f2ae5ba853
ms.sourcegitcommit: 612ce4d15d8a2fdbf7795393b50af477d81b6139
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65663516"
---
# <a name="manage-self-service-purchases-admin"></a>セルフサービスによる購入を管理する (管理者)

管理者は、組織内のユーザーが行ったセルフサービス購入を確認できます。 セルフサービス購入ごとに、製品名、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーが表示されます。 組織で必要な場合は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。 セルフサービス購入または一元的に購入した製品に対して、同じデータ管理ポリシーとアクセス ポリシーを持っています。

組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。 詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="view-self-service-subscriptions"></a>セルフサービス サブスクリプションを表示する

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[お使いの製品]</a> ページの順に移動します。
::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. サブスクリプションの詳細を表示するには、一覧からサブスクリプションを選択します。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する

> [!NOTE]
> 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. フィルター アイコンを選択し、[ **セルフサービス**] を選択します。
3. 製品を選択して、ユーザーに割り当てられているライセンスを表示します。
    > [!NOTE]
    > 製品に対して複数の購入がある場合、その製品は 1 回だけ一覧表示され、[ **使用可能な数量** ] 列には、その製品に対して購入したすべてのサブスクリプションの合計が表示されます。
4. **[ユーザー]** リストは、セルフサービス購入を行ったユーザーの名前でグループ化されます。
5. これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[ **ユーザーのエクスポート**] を選択します。

## <a name="disable-or-enable-self-service-purchases"></a>セルフサービス購入を無効または有効にする

組織内のユーザーに対してセルフサービス購入を無効または有効にすることができます。 **MSCommerce** PowerShell モジュールには **AllowSelfServicePurchase** の **PolicyID** パラメーター値が含まれており、組織内のユーザーがセルフサービス購入を行うことができるかどうか、およびどの製品に対して行うことができるかを制御できます。

**MSCommerce** PowerShell モジュールを使用すると以下のことができます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態 (製品によって有効または無効になっているかどうか) を表示する
- 利用可能な製品の一覧およびセルフサービス購入の有効または無効を表示する
- 特定の製品の現在の設定を表示または変更し、有効または無効にする

> [!IMPORTANT]
> **AllowSelfServicePurchase** ポリシーを使用すると、セルフサービス購入とセルフサービス試用版の両方が有効または無効になります。 セルフサービス購入に使用できる製品の一覧については、「セルフサービス購入 [製品の一覧とその状態を表示する](allowselfservicepurchase-powershell.md#view-a-list-of-self-service-purchase-products-and-their-status)」を参照してください。 試用版サブスクリプションでは、ProjectとVisioのみが使用できます。

詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="centralize-licenses-under-a-single-subscription"></a>1 つのサブスクリプションでライセンスを一元化する

セルフサービス購入に割り当てられたユーザーに対して、既存のライセンスを割り当てたり、既存の契約を通じて追加のサブスクリプションを購入したりできます。 これらの一元的に購入したライセンスを割り当てた後、購入者に既存のサブスクリプションの取り消しを要求できます。

::: moniker range="o365-worldwide"

1. 管理センターの **[課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購入サービス</a> ] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**課金** > **購入サービス**] ページに移動します。

::: moniker-end

2. 購入する製品を見つけて選択し、[ **購入**] を選択します。
3. 残りの手順を完了して購入を完了します。
4. 次の手順で参照するユーザーの一覧をエクスポートするには [、セルフサービスで購入したサブスクリプションのライセンスを持つユーザーを表示](#view-who-has-licenses-for-a-self-service-purchase-subscription) するの手順に従います。
5. 他のサブスクリプションでライセンスを持っているすべてのユーザーにライセンスを割り当てます。 完全な手順については、「 [ユーザーにライセンスを割り当てる」を](../../admin/manage/assign-licenses-to-users.md)参照してください。
6. セルフサービス購入サブスクリプションを購入したユーザーに連絡し、 [キャンセル](manage-self-service-purchases-users.md#cancel-a-subscription)するように依頼します。

## <a name="take-over-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションを引き継ぐ

組織内のユーザーが作成したセルフサービス購入サブスクリプションを引き継ぐことができます。 セルフサービス購入サブスクリプションを引き継ぐ場合、次の 2 つのオプションがあります。

1. ユーザーを別のサブスクリプションに移動し、元のサブスクリプションをキャンセルします。
2. セルフサービス購入サブスクリプションを取り消し、割り当てられたユーザーからライセンスを削除します。

### <a name="move-users-to-a-different-subscription"></a>ユーザーを別のサブスクリプションに移動する

ユーザーを別のサブスクリプションに移動すると、古いサブスクリプションは自動的に取り消されます。 セルフサービス購入サブスクリプションを最初に購入したユーザーは、サブスクリプションが取り消されたことを示す電子メールを受け取ります。

> [!NOTE]
> ユーザーを移動するサブスクリプションで、移動するユーザーごとに使用可能なライセンスが必要です。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>の [**製品** の **課金**>] ページに移動します。

::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. 引き継ぐサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[ **このサブスクリプションを制御** する] を選択します。
5. 右側のウィンドウで、[ **ユーザーの移動**] を選択します。
6. ユーザーを移動する製品を選択し、[ **ユーザーの移動**] を選択します。
7. [ **ユーザーの移動先** ] ボックスで、[ **ユーザーの移動**] を選択します。 移動プロセスには数分かかる場合があります。 プロセスの実行中はブラウザーを閉じないでください。
8. 移動プロセスが完了したら、[ **移動の完了] ウィンドウ** を閉じます。
9. サブスクリプションの詳細ページで、セルフサービスで購入したサブスクリプションのサブスクリプション **の状態** が **[削除済** み] と表示されます。

### <a name="cancel-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションをキャンセルする

セルフサービス購入サブスクリプションを取り消す場合、ライセンスを持つユーザーは製品にアクセスできなくなります。 セルフサービス購入サブスクリプションを最初に購入したユーザーは、サブスクリプションが取り消されたことを示す電子メールを受け取ります。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>の [**製品** の **課金**>] ページに移動します。

::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. キャンセルするサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[ **このサブスクリプションを制御** する] を選択します。
5. 右側のウィンドウで、[ **サブスクリプションのキャンセル**] を選択します。
6. ドロップダウン リストから取り消しの理由を選択し、[サブスクリプションの **キャンセル**] を選択します。
7. [ **キャンセル** するかどうか] ボックスで、[ **サブスクリプションのキャンセル**] を選択します。
8. 右側のウィンドウを閉じます。
9. [サブスクリプションの詳細] ページで、[ **サブスクリプションの状態]** が **[削除済** み] と表示されます。

## <a name="need-help-contact-us"></a>お困りの際は、 お問い合わせください。

セルフサービスでの購入に関するよく寄せられる質問については、「[セルフサービスでの購入に関する FAQ](self-service-purchase-faq.yml)」を参照してください。

ご質問がある場合や、セルフサービスでのご購入については、[サポートにお問い合わせ](../../admin/get-help-support.md)ください。
