---
title: E4 サブスクリプションOffice 365アップグレードする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- customer-email
- commerce_subscriptions
- admindeeplinkMAC
search.appverid: MET150
description: E4 サブスクリプションからアップグレードするOffice 365します。
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 1b909a6a40359e5d3f73b79bfd28ddff1037ea53
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151280"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>E4 サブスクリプションOffice 365アップグレードする

この記事では、E4 から新しいサブスクリプションへのアップグレードOffice 365手順を説明します。 E4 からアップグレードするときに使用できるオプションの詳細については、「E4 のお客様Office 365重要[な情報」Office 365 を参照してください](important-information-e4.md)。

> [!IMPORTANT]
> この記事は、Office 365または請求書のみを通じて Microsoft から直接購入された E4 サブスクリプションに適用されます。 サブスクリプションがパートナー経由やボリューム ライセンス サービス センター経由など、別の方法で購入された場合は、Microsoft アカウント担当者またはパートナーに連絡して、プランのアップグレードを支援してください。

## <a name="what-are-my-options-for-how-to-upgrade"></a>アップグレード方法に関するオプションは何ですか?

プランをアップグレードする最も簡単な方法は、プランの [アップグレード] タブを<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">使用Microsoft 365 管理センター。</a> ただし、[アップグレード] **タブの** 使用は、すべての状況でサポートされるわけではありません。 シナリオがサポートされていない場合は、プランを手動でアップグレードできる場合があります。

## <a name="what-is-the-upgrade-tab"></a>[アップグレード] タブとは

[ **アップグレード] タブ** では、次のタスクを実行します。

- 新しいプランの購入手続きを、順に実行します。
- すべてのユーザー ライセンスを現在のプランから新しいプランに再割り当てします。
- 以前のプランをキャンセルします。

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>プランを手動でアップグレードするとはどういう意味ですか?

プランを手動でアップグレードする場合は、[アップグレード] タブを使用する代わりに、次の個別の手順 **を完了** します。

- ライセンス数が適切な新しいサブスクリプションを購入します。
- 新しいサブスクリプションを使用する準備ができていることを確認します。
- ユーザーにライセンスを再割り当てします。
- E4 サブスクリプションの元Office 365を取り消します。

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>[アップグレード] タブを使用して新しいプランにアップグレードできる場合

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. E4 サブスクリプションOffice 365選択します。
3. [アップグレード] **タブを選択** します。他のプランが一覧表示されている場合は、プランを自動的にアップグレードできます。
4. 自動的にアップグレードできない場合は、アップグレードできない理由を示すメッセージが表示されます。

プランを自動的にアップグレードできない理由は複数あります。 問題のほとんどは、サービス正常性の問題などの一時的な問題であり、解決することができます。 詳細については、「なぜプランをアップグレード [できないのか」を参照してください。](upgrade-to-different-plan.md#why-cant-i-upgrade-plans) アップグレードに関するサポートが必要な場合は、サポート [にお問い合わせください](../../business-video/get-help-support.md)。

## <a name="will-a-credit-check-be-required"></a>クレジット チェックが必要ですか?

新しいプランの支払いを請求書で行う場合、または購入金額が一定の金額を超えた場合、クレジット カードの与信審査が必要になることがあります。 クレジット チェックが必要な場合、アップグレードには最大 2 営業日かかる場合があります。 管理者は、クレジット チェックが完了するまでMicrosoft 365 管理センターにアクセスできます。 ただし、アップグレードが完了するまで、ユーザーは引き続き E4 プランにフル アクセスできます。

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してプランをアップグレードする

### <a name="before-you-begin"></a>はじめに

ここでは、操作を始める前に知っておく必要がある重要な点について説明します。

- **管理のダウンタイムを計画します。** 管理者は、プランのアップグレード中Microsoft 365 管理センターを使用することはできません。 ユーザーの数に応じて、アップグレードには数分から数時間かかる場合があります。 更新プログラムを使用して更新を行う必要がない場合は、アップグレードを行うMicrosoft 365 管理センター。

    ユーザーは、プランのアップグレード中にサービスの中断が発生しない - アップグレード プロセス中に E4 サブスクリプションにフル アクセスし続ける。 アップグレードが完了すると、ユーザーは新しいプランにアクセスできます。
- **ユーザー、ライセンス、課金、およびカスタム ドメイン。** アップグレード中にユーザーとライセンスがどのように処理されるのか、プランのアップグレードが請求にどのように影響するのか、カスタム ドメインを処理する方法を理解するには、「プランをアップグレードするとサービスと課金に対して何が行われるか」を参照 [してください。](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)
- **ユーザー ライセンスの数を変更します。** プランのアップグレードの一環としてライセンスを削除できない。 ただし、プランを [アップグレードする前またはアップグレード](../licenses/buy-licenses.md) 後にライセンスの数を減らすことはできます。

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してアップグレードを開始する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. E4 サブスクリプションOffice 365選択します。
3. [サブスクリプションの詳細] ページで、[アップグレード] タブ **を選択** します。
4. 購入するサブスクリプションを見つけて、[アップグレード] を **選択します**。
5. [カート **] ページ** で、すべてが正しいか確認します。 月払いまたは年払いを選択し、[数量] でライセンス数を **確認します**。
    > [!NOTE]
    > E4 サブスクリプションに関連付けられているアドオン サブスクリプション (Office 365 ファイルの追加などOffice 365がStorage表示されます。 ただし、アップグレードするサブスクリプションに含まれるアドオン サブスクリプションがある場合は、そのサブスクリプションを削除します。
6. 注文を確認した後、[チェックアウトに移動] **を選択します**。
7. [チェックアウト **] ページで** 、[ **販売済み]**、[ **請求** 済み] 、および [アイテム] を **この順序で確認します**。 これらの **項目の** 横にある [変更] を選択して、情報を編集します。
    > [!NOTE]
    > 支払い方法として請求書を使用するオプションは、一定のコスト金額を超える注文でのみ使用できます。 請求書支払いオプションを選択すると、クレジット チェックが必要な場合、アップグレード プロセスが最大 2 営業日遅れることがあります。
8. 完了したら、[注文の配置] **を選択します**。

> [!NOTE]
> プランのアップグレードには、通常、エラーや問題がない場合は 10 分未満かかります。 アップグレードの状態を確認するには、古いサブスクリプションまたは新しいサブスクリプションを確認します。

## <a name="upgrade-your-plan-manually"></a>プランを手動でアップグレードする

ユーザーを別のサブスクリプションに手動でアップグレードするには、次に示す順序で手順を実行します。

- [手順 1: 新しいサブスクリプションを購入する](#step-1-buy-a-new-subscription)
- [手順 2: サブスクリプションのライセンス数が正しいか確認する](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [手順 3: ユーザーにライセンスを再割り当てする](#step-3-reassign-licenses-to-users)
- [手順 4: E4 サブスクリプションOffice 365キャンセルする](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>手順 1: 新しいサブスクリプションを購入する

まだ新しいサブスクリプションを持っていない場合は、ビジネス サブスクリプション用に別Microsoft 365[購入できます](../try-or-buy-microsoft-365.md)。

サブスクリプションが既にある場合は、次の手順に進みます。

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>手順 2: サブスクリプションのライセンス数が正しいか確認する

次の手順に進む前に、新しいサブスクリプション内のすべてのサービスがセットアップされている必要があります。 最初に確認するときにサブスクリプションの準備ができていない場合は、後でやり直してください。

> [!NOTE]
> 請求書で新しいサブスクリプションの支払いを選択した場合は、クレジット チェックが必要になる場合があります。 サブスクリプションを利用するには、最大 2 営業日かかる場合があります。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [サブスクリプションの **状態] ドロップダウン** から、[アクティブ] を **選択します**。
3. 新しいサブスクリプションが表示され、ライセンス数が E4 のライセンス数と同じOffice 365してください。
4. ライセンスを購入する必要がある場合は、「サブスクリプション ライセンスを購入または削除 [する」の手順に従います](../licenses/buy-licenses.md)。

### <a name="step-3-reassign-licenses-to-users"></a>手順 3: ユーザーにライセンスを再割り当てする

一度に最大[20 Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)ライセンスを再割り当てする場合は、このツールを使用できます。 方法については、「ユーザーを別の [サブスクリプションに移動する」を参照してください](move-users-different-subscription.md)。

> [!TIP]
> ユーザーが多い場合は、PowerShell を使用してOffice 365[ライセンスを一括で割り当てできます](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)。

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>手順 4: E4 サブスクリプションOffice 365キャンセルする

すべてのユーザーが新しいサブスクリプションに再割り当てされた後[、E4 サブスクリプションOffice 365取り消します](cancel-your-subscription.md)。

## <a name="related-content"></a>関連コンテンツ

[別のプランにアップグレード](upgrade-to-different-plan.md) する (記事)\
[サブスクリプション ライセンスを購入または削除する](../licenses/buy-licenses.md) (記事)\
[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)
