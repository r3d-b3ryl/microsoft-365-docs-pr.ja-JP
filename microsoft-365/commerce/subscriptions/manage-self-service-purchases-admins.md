---
title: セルフサービス購入の管理 (管理者)
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, pablom
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
description: 管理者は、組織内のユーザーが行ったセルフサービス購入を管理する方法について学習できます。
ms.date: 03/26/2021
ms.openlocfilehash: 19f276107de7b1dd1053e500d249950a8700ac41
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319729"
---
# <a name="manage-self-service-purchases-admin"></a>セルフサービスによる購入を管理する (管理者)

管理者は、組織内のユーザーが行ったセルフサービス購入を確認できます。 セルフサービス購入ごとに、製品名、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーが表示されます。 組織で必要な場合は、PowerShell を介して製品ごとにセルフサービス購入をオフにできます。 セルフサービス購入または一般購入で購入した製品と同じデータ管理ポリシーとアクセス ポリシーがあります。

組織内のユーザーがセルフサービス購入を行うかどうかを制御することもできます。 詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="view-self-service-subscriptions"></a>セルフサービス サブスクリプションの表示

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[お使いの製品]</a> ページの順に移動します。
::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. サブスクリプションの詳細を表示するには、一覧から 1 つを選択します。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する

> [!NOTE]
> 管理者は、組織内のユーザーが購入したセルフサービス購入サブスクリプションのライセンスを割り当てたり割り当て解除したりすることはできません。 [セルフサービス購入サブスクリプションを引き継ぐと](#take-over-a-self-service-purchase-subscription)、ライセンスの割り当てまたは割り当て解除を行うことができるようになります。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。

::: moniker-end

2. フィルター アイコンを選択し、[セルフサービス **] を選択します**。
3. 製品を選択すると、ユーザーに割り当てられたライセンスが表示されます。
    > [!NOTE]
    > 製品に複数の購入がある場合、その製品は 1 回だけ表示され、[利用可能な数量] 列には、その製品に対して購入されたサブスクリプションの合計が表示されます。
4. [ **ユーザー]** リストは、セルフサービス購入を行ったユーザーの名前でグループ化されます。
5. これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[ユーザーのエクスポート] **を選択します**。

## <a name="disable-or-enable-self-service-purchases"></a>セルフサービス購入を無効または有効にする

組織内のユーザーに対してセルフサービス購入を無効または有効にできます。 **MSCommerce** PowerShell モジュールには **AllowSelfServicePurchase** の **PolicyID** パラメーター値が含まれています。

**MSCommerce** PowerShell モジュールを使用すると以下のことができます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態を表示する (製品によって有効または無効になっているかどうか)
- 利用可能な製品の一覧およびセルフサービス購入の有効または無効を表示する
- 特定の製品の現在の設定を表示または変更し、有効または無効にする

詳細については、「[MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="centralize-licenses-under-a-single-subscription"></a>1 つのサブスクリプションでライセンスを一元化する

セルフサービス購入に割り当てられたユーザーに対して、既存のライセンスを割り当てたり、既存の契約を通じて追加のサブスクリプションを購入することができます。 これらの一般購入ライセンスを割り当てると、購入者に既存のサブスクリプションのキャンセルを要求できます。

::: moniker range="o365-worldwide"

1. 管理センターで、[課金の購入サービス **] ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>課金の購入サービス **] ページ** > **に移動** します。

::: moniker-end

2. 購入する製品を見つけて選択し、[購入] を選択 **します**。
3. 残りの手順を完了して購入を完了します。
4. 「セルフサービス購入サブスクリプション[](#view-who-has-licenses-for-a-self-service-purchase-subscription)のライセンスを持っているユーザーを表示する」の手順に従って、次の手順で参照するユーザーのリストをエクスポートします。
5. 他のサブスクリプションでライセンスを持っているすべてのユーザーにライセンスを割り当てる。 完全な手順については、「ユーザーにライセンスを [割り当てる」を参照してください](../../admin/manage/assign-licenses-to-users.md)。
6. セルフサービス購入サブスクリプションを購入したユーザーに問い合わせ、キャンセルを [求める](manage-self-service-purchases-users.md#cancel-a-subscription)。

## <a name="take-over-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションの引き継ぎ

組織内のユーザーが作成したセルフサービス購入サブスクリプションを引き継ぐ方法があります。 セルフサービス購入サブスクリプションを引き継ぐ場合は、次の 2 つのオプションがあります。

1. ユーザーを別のサブスクリプションに移動し、元のサブスクリプションをキャンセルします。
2. セルフサービス購入サブスクリプションをキャンセルし、割り当てられたユーザーからライセンスを削除します。

### <a name="move-users-to-a-different-subscription"></a>ユーザーを別のサブスクリプションに移動する

ユーザーを別のサブスクリプションに移動すると、古いサブスクリプションは自動的に取り消されます。 最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたというメールを受信します。

> [!NOTE]
> ユーザーを移動するサブスクリプションで移動するユーザーごとに使用可能なライセンスが必要です。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>製品の請求] **ページ** > **に移動** します。

::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. 引き継ぐサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[このサブスクリプションを制御 **する] を選択します**。
5. 右側のウィンドウで、[ユーザーの移動 **] を選択します**。
6. ユーザーを移動する製品を選択し、[ユーザーの移動] **を選択します**。
7. [ユーザーの **移動] ボックスで** 、[ユーザーの移動 **] を選択します**。 移動プロセスには数分かかる場合があります。 プロセスの実行中にブラウザーを閉じない。
8. 移動プロセスが完了したら、[完了した移動] **ウィンドウを閉じます**。
9. サブスクリプションの詳細ページで **、セルフサービス購入** サブスクリプションのサブスクリプションの状態が [削除済み] と **表示されます**。

### <a name="cancel-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションをキャンセルする

セルフサービス購入サブスクリプションをキャンセルすると、ライセンスを持つユーザーは製品へのアクセスを失います。 最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたというメールを受信します。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センター <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">で、[</a>製品の請求] **ページ** > **に移動** します。

::: moniker-end

2. **[製品]** タブで、フィルター アイコンを選択し、**[セルフサービス]** を選択します。
3. キャンセルするサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと設定** ] セクションで、[このサブスクリプションを制御 **する] を選択します**。
5. 右側のウィンドウで、[サブスクリプションのキャンセル] **を選択します**。
6. ドロップダウン リストからキャンセルの理由を選択し、[サブスクリプションのキャンセル] **を選択します**。
7. [キャンセル **しますか? ] ボックスで** 、[サブスクリプションのキャンセル] **を選択します**。
8. 右側のウィンドウを閉じます。
9. [サブスクリプションの詳細] ページで、[サブスクリプションの状態 **] が [** 削除済み] **と表示されます**。

## <a name="need-help-contact-us"></a>お困りの際は、 お問い合わせください。

セルフサービスでの購入に関するよく寄せられる質問については、「[セルフサービスでの購入に関する FAQ](self-service-purchase-faq.yml)」を参照してください。

ご質問がある場合や、セルフサービスでのご購入については、[サポートにお問い合わせ](../../admin/get-help-support.md)ください。
