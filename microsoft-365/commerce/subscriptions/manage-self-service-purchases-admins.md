---
title: セルフサービス購入を管理する (管理者)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 管理者は、組織内のユーザーが行ったセルフサービス購入を管理する方法について学習できます。
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114695"
---
# <a name="manage-self-service-purchases-admin"></a>セルフサービスによる購入を管理する (管理者)

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

管理者は、組織内のユーザーによるセルフサービス購入を確認できます。 セルフサービス購入ごとに、製品名、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーが表示されます。 組織で必要な場合は、PowerShell を使用して製品ごとにセルフサービス購入をオフにできます。 セルフサービス購入を通じて購入した製品に対して、同じデータ管理ポリシーとアクセス ポリシーを使用できます。

組織内のユーザーがセルフサービス購入を行うかどうかを制御することもできます。 詳細については [、MSCommerce PowerShell モジュールの AllowSelfServicePurchase の使用に関するページを参照してください](allowselfservicepurchase-powershell.md)。

## <a name="view-self-service-subscriptions"></a>セルフサービス サブスクリプションを表示する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。
3. サブスクリプションの詳細を表示するには、一覧から 1 つを選択します。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションのライセンスを持つユーザーを表示する

1. 管理センターで、[課金ライセンス]ページ  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。
2. フィルター アイコンを選択し、[セルフサービス] **を選択します**。
3. 製品を選択して、ユーザーに割り当てられているライセンスを表示します。
    > [!NOTE]
    > 1 つの製品に対して複数の購入がある場合、その製品は 1回だけ表示され、[利用可能な数量] 列には、その製品で購入したサブスクリプションの合計が表示されます。
4. Users **リスト** は、セルフサービス購入を行ったユーザーの名前によってグループ化されます。
5. これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[ユーザーのエクスポート] を **選択します**。

## <a name="disable-or-enable-self-service-purchases"></a>セルフサービス購入を無効または有効にする

組織内のユーザーのセルフサービス購入を無効または有効にできます。 **MSCommerce** PowerShell モジュールには **、AllowSelfServicePurchase** の **PolicyID** パラメーター値が含まれています。これにより、組織内のユーザーがセルフサービス購入を行えるかどうか、およびどの製品を購入できるのかを制御できます。

MSCommerce PowerShell **モジュールを使用すると** 、次の目的に使用できます。

- **AllowSelfServicePurchase** パラメーター値の既定の状態 (製品によって有効または無効になっているかどうか) を表示する
- 該当する製品の一覧と、セルフサービス購入が有効か無効かを表示する
- 特定の製品の現在の設定を表示または変更して有効または無効にする

詳細については [、MSCommerce PowerShell モジュールの AllowSelfServicePurchase の使用に関するページを参照してください](allowselfservicepurchase-powershell.md)。

## <a name="centralize-licenses-under-a-single-subscription"></a>1 つのサブスクリプションでライセンスを集中管理する

セルフサービス購入に割り当てられたユーザーの既存の契約を通じて、既存のライセンスを割り当てたり、追加のサブスクリプションを購入することができます。 一般に購入したライセンスを割り当てると、購入者に既存のサブスクリプションの取り消しを要求できます。

1. 管理センターで、[課金サービス]  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">ページに移動</a>します。
2. 購入する製品を見つけて選択し、[購入] を選択 **します**。
3. 購入を完了するには、残りの手順を実行します。
4. セルフサービス購入 [サブスクリプションのライセンス](#view-who-has-licenses-for-a-self-service-purchase-subscription) を持つユーザーを表示する手順に従って、次の手順で参照するユーザーの一覧をエクスポートします。
5. 他のサブスクリプションのライセンスを持つすべてのユーザーにライセンスを割り当てる。 完全な手順については、「ライセンスをユーザーに [割り当てる」を参照してください](../../admin/manage/assign-licenses-to-users.md)。
6. セルフサービス購入サブスクリプションを購入したユーザーに問い合わせ、キャンセル [を求める](manage-self-service-purchases-users.md#cancel-a-subscription)。

## <a name="take-over-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションを引き継ぐ

組織内のユーザーが作成したセルフサービス購入サブスクリプションを引き継ぐ場合があります。 セルフサービス購入サブスクリプションを引き継ぐには、次の 2 つのオプションがあります。

1. ユーザーを別のサブスクリプションに移動し、元のサブスクリプションをキャンセルします。
2. セルフサービス購入サブスクリプションをキャンセルし、割り当てられたユーザーからライセンスを削除します。

### <a name="move-users-to-a-different-subscription"></a>ユーザーを別のサブスクリプションに移動する

ユーザーを別のサブスクリプションに移動すると、古いサブスクリプションは自動的に取り消されます。 最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたという電子メールを受信します。

> [!NOTE]
> ユーザーを移動するサブスクリプションに移動するユーザーごとに、利用可能なライセンスが必要です。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。
3. 引き継ぐサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの[サブスクリプションと設定] セクションで、[このサブスクリプションを制御する **] を選択します**。
5. 右側のウィンドウで、[ユーザーの移動] **を選択します**。
6. ユーザーを移動する製品を選択し、[ユーザーの移動] **を選択します**。
7. [ユーザーの **移動] ボックスで、[** ユーザーの移動] **を選択します**。 移動プロセスには数分かかる場合があります。 プロセスの実行中にブラウザーを閉じない。
8. 移動処理が完了したら、[移動完了] **ウィンドウを閉じます**。
9. サブスクリプションの詳細ページで **、セルフサービスで** 購入したサブスクリプションのサブスクリプションの状態が [削除済み] と **表示されます**。

### <a name="cancel-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションをキャンセルする

セルフサービス購入サブスクリプションを取り消す場合、ライセンスを持つユーザーは製品へのアクセス権を失います。 最初にセルフサービス購入サブスクリプションを購入したユーザーは、サブスクリプションがキャンセルされたという電子メールを受信します。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、フィルター アイコンを選択し、[セルフサービス] **を選択します**。
3. キャンセルするサブスクリプションを選択します。
4. [サブスクリプションの詳細] ページの[サブスクリプションと設定] セクションで、[このサブスクリプションを制御する **] を選択します**。
5. 右側のウィンドウで、[サブスクリプションのキャンセル] **を選択します**。
6. ドロップダウン リストから取り消しの理由を選択し、[サブスクリプションのキャンセル] を **選択します**。
7. In the **Are you sure you want to cancel?** box, select Cancel **subscription**.
8. 右側のウィンドウを閉じます。
9. サブスクリプションの詳細ページで、[サブスクリプションの状態] **が [削除済** み] **と表示されます**。

## <a name="need-help-contact-us"></a>サポートが必要な場合 お問い合わせください。

セルフサービス購入に関する一般的な質問については、セルフサービス購入に関する [FAQ を参照してください](self-service-purchase-faq.md)。

セルフサービス購入に関する質問やサポートが必要な場合は、サポートにお [問い合わせください](../../admin/contact-support-for-business-products.md)。