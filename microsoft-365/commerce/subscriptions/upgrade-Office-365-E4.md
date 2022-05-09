---
title: Office 365 E4 サブスクリプションからのアップグレード
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
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
- commerce_subscriptions
- customer-email
- admindeeplinkMAC
search.appverid: MET150
description: Office 365 E4 サブスクリプションからアップグレードする方法について説明します。
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 60e7cb7c97255f3588c99a0eb66bc7c8379de8b9
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316339"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>Office 365 E4 サブスクリプションからのアップグレード

この記事では、Office 365 E4 から新しいサブスクリプションにアップグレードするプロセスについて説明します。 Office 365 E4 からアップグレードするときに使用できるオプションの詳細については、「Office 365 [E4 のお客様に関する重要な情報](important-information-e4.md)」を参照してください。

> [!IMPORTANT]
> この記事は、クレジット カードまたは請求書を使用して Microsoft から直接購入された E4 サブスクリプションOffice 365に適用されます。 パートナーやボリューム ライセンス サービス センターなどの別の方法でサブスクリプションを購入した場合は、Microsoft アカウントの担当者またはパートナーに問い合わせて、プランをアップグレードしてください。

## <a name="what-are-my-options-for-how-to-upgrade"></a>アップグレード方法のオプションは何ですか?

プランをアップグレードする最も簡単な方法は、Microsoft 365 管理センターの [**アップグレード**] タブを使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">することです</a>。 ただし、[ **アップグレード** ] タブの使用は、すべての状況でサポートされているわけではありません。 シナリオがサポートされていない場合は、プランを手動でアップグレードできる可能性があります。

## <a name="what-is-the-upgrade-tab"></a>[アップグレード] タブとは

[ **アップグレード** ] タブでは、次のタスクが実行されます。

- 新しいプランの購入手続きを、順に実行します。
- すべてのユーザー ライセンスを現在のプランから新しいプランに再割り当てします。
- 以前のプランをキャンセルします。

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>プランを手動でアップグレードするとはどういう意味ですか?

プランを手動でアップグレードする場合は、[ **アップグレード** ] タブを使用する代わりに、次の個別の手順を完了することを意味します。

- 適切な数のライセンスを持つ新しいサブスクリプションを購入します。
- 新しいサブスクリプションを使用する準備ができていることを確認します。
- ライセンスをユーザーに再割り当てします。
- 元のOffice 365 E4 サブスクリプションをキャンセルします。

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>[アップグレード] タブを使用して新しいプランにアップグレードできるかどうかを確認する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. Office 365 E4 サブスクリプションを選択します。
3. [ **アップグレード** ] タブを選択します。他のプランが一覧表示されている場合は、プランを自動的にアップグレードできることを意味します。
4. 自動的にアップグレードできない場合は、アップグレードできない理由を説明するメッセージが表示されます。

プランを自動的にアップグレードできない理由はいくつかあります。 問題のほとんどは、サービス正常性の問題などの一時的な問題であり、解決することができます。 詳細については、「[プランをアップグレードできない理由](upgrade-to-different-plan.md#why-cant-i-upgrade-plans)」を参照してください。 アップグレードに関するヘルプが必要な場合は、 [サポートにお問い合わせください](../../admin/get-help-support.md)。

## <a name="will-a-credit-check-be-required"></a>クレジット チェックは必要ですか?

新しいプランの支払いを請求書で行う場合、または購入金額が一定の金額を超えた場合、クレジット カードの与信審査が必要になることがあります。 クレジット チェックが必要な場合、アップグレードには最大 2 営業日かかる場合があります。 管理者は、クレジット チェックが完了するまでMicrosoft 365 管理センターにアクセスできません。 ただし、アップグレードが完了するまで、ユーザーは E4 プランに完全にアクセスできます。

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してプランをアップグレードする

### <a name="before-you-begin"></a>開始する前に

ここでは、操作を始める前に知っておく必要がある重要な点について説明します。

- **管理ダウンタイムを計画します。** プランのアップグレード中は、管理者はMicrosoft 365 管理センターを使用できません。 ユーザーの数によっては、アップグレードに数分から数時間かかる場合があります。 Microsoft 365 管理センターを使用して更新を行う必要がない場合は、アップグレードを行うことを計画することをお勧めします。

    プランのアップグレード中にユーザーがサービスの中断を経験することはありません。アップグレード プロセス中も E4 サブスクリプションに完全にアクセスし続けます。 アップグレードが完了すると、ユーザーは新しいプランにアクセスできます。
- **ユーザー、ライセンス、課金、カスタム ドメイン。** アップグレード中のユーザーとライセンスの処理方法、アップグレード プランが課金に与える影響、カスタム ドメインの処理方法については、「[プランのアップグレードはサービスと課金に対して行う処理」を](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)参照してください。
- **ユーザー ライセンスの数を変更します。** アップグレード 計画の一部としてライセンスを削除することはできません。 ただし、プランをアップグレードする前または後 [にライセンスの数を減らすことができます](../licenses/buy-licenses.md) 。

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してアップグレードを開始する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. Office 365 E4 サブスクリプションを選択します。
3. サブスクリプションの詳細ページで、[ **アップグレード** ] タブを選択します。
4. 購入するサブスクリプションを見つけて、[ **アップグレード**] を選択します。
5. **[カート]** ページで、すべてが正しいことを確認します。 月払いまたは年払いを選択し、[ **数量**] でライセンスの数を確認します。
    > [!NOTE]
    > Office 365 E4 サブスクリプションに関連付けられているアドオン サブスクリプション (Office 365 Extra File Storageなど) も一覧表示されます。 ただし、アップグレードするサブスクリプションに含まれているアドオン サブスクリプションがある場合は、削除されます。
6. 注文を確認したら、[ **チェックアウトに移動**] を選択します。
7. **[チェックアウト]** ページで、この順序で **[販売先**]、[**請求先**]、[**アイテム] の順に確認します**。 これらの項目の横にある **[変更** ] を選択して情報を編集します。
    > [!NOTE]
    > 請求書を支払い方法として使用するオプションは、特定のコスト金額を超える注文でのみ使用できます。 請求書の支払いオプションを選択すると、クレジット チェックが必要な場合、アップグレード プロセスが最大 2 営業日遅れる可能性があります。
8. 完了したら、[**注文**] を選択します。

> [!NOTE]
> 通常、プランのアップグレードには、エラーや問題がない場合に 10 分未満かかります。 アップグレードの状態を確認するには、古いサブスクリプションまたは新しいサブスクリプションを確認します。

## <a name="upgrade-your-plan-manually"></a>プランを手動でアップグレードする

ユーザーを別のサブスクリプションに手動でアップグレードするには、次の手順を示す順序で実行します。

- [手順 1: 新しいサブスクリプションを購入する](#step-1-buy-a-new-subscription)
- [手順 2: サブスクリプションに適切なライセンス数があることを確認する](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [手順 3: ユーザーにライセンスを再割り当てする](#step-3-reassign-licenses-to-users)
- [手順 4: Office 365 E4 サブスクリプションをキャンセルする](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>手順 1: 新しいサブスクリプションを購入する

新しいサブスクリプションをまだお持ちでない場合は、[ビジネス サブスクリプション用に別のMicrosoft 365を購入](../try-or-buy-microsoft-365.md)できます。

サブスクリプションが既にある場合は、次の手順に進みます。

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>手順 2: サブスクリプションに適切なライセンス数があることを確認する

次の手順に進む前に、新しいサブスクリプション内のすべてのサービスが設定されていることを確認することが重要です。 最初に確認したときにサブスクリプションの準備ができていない場合は、後でもう一度試してください。

> [!NOTE]
> 請求書による新しいサブスクリプションの支払いを選択した場合は、クレジット チェックが必要になる場合があります。 サブスクリプションが利用可能になるまでには、最大で 2 営業日かかる場合があります。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. **[サブスクリプションの状態]** ドロップダウンから [アクティブ] を選択 **します**。
3. 新しいサブスクリプションが表示されていること、およびライセンスの数が、Office 365 E4 のライセンス数と同じであることを確認します。
4. さらにライセンスを購入する必要がある場合は、「サブスクリプション ライセンスを [購入または削除](../licenses/buy-licenses.md)する」の手順に従います。

### <a name="step-3-reassign-licenses-to-users"></a>手順 3: ユーザーにライセンスを再割り当てする

[Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)を使用して、一度に最大 20 人のユーザーのライセンスを再割り当てできます。 方法については、「[ユーザーを別のサブスクリプションに移動する](move-users-different-subscription.md)」を参照してください。

> [!TIP]
> 多数のユーザーがいる場合は、[Office 365 PowerShell を使用してユーザー ライセンスを一括で割り当てることができます](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)。

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>手順 4: Office 365 E4 サブスクリプションをキャンセルする

すべてのユーザーが新しいサブスクリプションに再割り当てされたら、[Office 365 E4 サブスクリプションをキャンセルします](cancel-your-subscription.md)。

## <a name="related-content"></a>関連コンテンツ

[別のプランにアップグレード](upgrade-to-different-plan.md) する (記事)\
[サブスクリプション ライセンスを購入または削除する](../licenses/buy-licenses.md) (記事)\
[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)
