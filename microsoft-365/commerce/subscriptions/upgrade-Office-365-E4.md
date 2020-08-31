---
title: Office 365 E4 サブスクリプションからのアップグレード
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
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
ms.custom: customer-email
search.appverid:
- MET150
description: Office 365 E4 サブスクリプションからアップグレードする方法について説明します。
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2587732a6c4092dcb7b53daf9493e7cee2f1987c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308007"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>Office 365 E4 サブスクリプションからのアップグレード

この記事では、Office 365 E4 から新しいサブスクリプションにアップグレードするプロセスについて手順を追って説明します。 Office 365 E4 からアップグレードする際に使用可能なオプションの詳細については、「 [office 365 e4 のお客様向けの重要情報](important-information-e4.md)」を参照してください。

> [!IMPORTANT]
> この記事は、クレジットカードまたは請求書のみから Microsoft から直接購入した Office 365 E4 サブスクリプションに適用されます。 パートナーまたはボリュームライセンスサービスセンターを通じてサブスクリプションを別の方法で購入した場合は、プランのアップグレードに役立つ Microsoft アカウント担当者またはパートナーにお問い合わせください。

## <a name="what-are-my-options-for-how-to-upgrade"></a>アップグレード方法について、どのようなオプションがありますか?

計画をアップグレードする最も簡単な方法は、Microsoft 365 管理センターの [ **アップグレード** ] タブを使用することです。 ただし、[ **アップグレード** ] タブの使用は、すべての状況でサポートされているわけではありません。 シナリオがサポートされていない場合は、手動でプランをアップグレードできます。

## <a name="what-is-the-upgrade-tab"></a>[アップグレード] タブとは

[ **アップグレード** ] タブでは、次のタスクを実行できます。

- 新しいプランの購入手続きを、順に実行します。
- すべてのユーザー ライセンスを現在のプランから新しいプランに再割り当てします。
- 以前のプランをキャンセルします。

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>プランを手動でアップグレードすることを意味します。

手動によるプランのアップグレードとは、[ **アップグレード** ] タブを使用する代わりに、次の手順を実行することを意味します。

- 適切なライセンス数で新しいサブスクリプションを購入します。
- 新しいサブスクリプションを使用する準備ができていることを確認します。
- ユーザーにライセンスを再割り当てします。
- 元の Office 365 E4 サブスクリプションをキャンセルします。

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>[アップグレード] タブを使用して新しいプランにアップグレードできるかどうかを確認する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. Office 365 E4 サブスクリプションを選択します。
3. [ **アップグレード** ] タブを選択します。他のプランが表示されている場合は、プランを自動的にアップグレードできることを意味します。
4. 自動的にアップグレードできない場合は、アップグレードできない理由を説明するメッセージが表示されます。

プランを自動的にアップグレードできない理由はいくつかあります。 問題のほとんどは、サービス正常性の問題などの一時的な問題であり、解決することができます。 詳細については、「[プランをアップグレードできない理由](upgrade-to-different-plan.md#why-cant-i-upgrade-plans)」を参照してください。 アップグレードについてサポートが必要な場合は、 [サポートにお問い合わせ](../../admin/contact-support-for-business-products.md)ください。

## <a name="will-a-credit-check-be-required"></a>信用調査は必要ですか?

新しいプランの支払いを請求書で行う場合、または購入金額が一定の金額を超えた場合、クレジット カードの与信審査が必要になることがあります。 与信審査が必要な場合、アップグレードには最大2営業日かかることがあります。 管理者は、与信審査が完了するまで、Microsoft 365 管理センターにアクセスできません。 ただし、アップグレードが完了するまで、ユーザーは E4 プランに完全にアクセスできます。

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してプランをアップグレードする

### <a name="before-you-begin"></a>はじめに

ここでは、操作を始める前に知っておく必要がある重要な点について説明します。

- **管理のダウンタイムを計画します。** 管理者は、プランのアップグレード中に Microsoft 365 管理センターを使用することはできません。 ユーザー数に応じて、アップグレードには数分から数時間かかる場合があります。 Microsoft 365 管理センターを使用して更新を行う必要がない場合は、アップグレードを計画することをお勧めします。

    プランがアップグレードされている間、ユーザーはサービスの中断を受けませんが、アップグレードプロセス中は E4 サブスクリプションへの完全なアクセス権を持ち続けます。 アップグレードが完了すると、ユーザーは新しいプランにアクセスできるようになります。
- **ユーザー、ライセンス、課金、およびカスタムドメイン。** アップグレード中にユーザーとライセンスがどのように処理されるか、どのように課金が請求に影響するか、およびカスタムドメインを処理する方法については、「[プランをアップグレードしてサービスと課金にする](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)方法」を参照してください。
- **ユーザーライセンスの数を変更します。** プランのアップグレードの一環としてライセンスを削除することはできません。 ただし、プランをアップグレードする前または後に、 [ライセンスの数を減らす](../licenses/buy-licenses.md) ことができます。

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>[アップグレード] タブを使用してアップグレードを開始する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. Office 365 E4 サブスクリプションを選択します。
3. [サブスクリプションの詳細] ページで、[ **アップグレード** ] タブを選択します。
4. 購入するサブスクリプションを検索し、[ **アップグレード**] を選択します。
5. [ **カート** ] ページで、すべてが正しいことを確認します。 月単位または年単位で支払いを行うかどうかを選択し、[ **数量**] の下のライセンス数を確認します。
    > [!NOTE]
    > Office 365 E4 サブスクリプションに関連付けられているアドオンサブスクリプション (Office 365 の追加ファイルストレージなど) も一覧に表示されます。 ただし、アップグレードするサブスクリプションに含まれているアドオンサブスクリプションがある場合は、それらを削除します。
6. 注文を確認したら、[ **チェックアウトに移動**] を選択します。
7. [**チェックアウト**] ページで、**この順序で**の**販売先**、**請求先**、およびアイテムを確認します。 情報を編集するには、これらのアイテムの横にある [ **変更** ] を選択します。
    > [!NOTE]
    > 支払い方法として請求書を使用するオプションは、特定のコストの金額を超える注文に対してのみ使用できます。 請求書の支払オプションを選択すると、与信審査が必要な場合に、アップグレードプロセスは最大2営業日まで延期することができます。
8. 完了したら、[ **注文**] を選択します。

> [!NOTE]
> エラーや問題が発生していない場合、通常、プランのアップグレードにかかる時間は10分未満です。 アップグレードの状態を確認するには、古いサブスクリプションまたは新しいサブスクリプションのどちらかを参照してください。

## <a name="upgrade-your-plan-manually"></a>手動でプランをアップグレードする

ユーザーを別のサブスクリプションに手動でアップグレードするには、次の手順を示されている順序で実行します。

- [手順 1: 新しいサブスクリプションを購入する](#step-1-buy-a-new-subscription)
- [手順 2: サブスクリプションに適切な数のライセンスがあることを確認する](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [手順 3: ユーザーにライセンスを再割り当てする](#step-3-reassign-licenses-to-users)
- [手順 4: Office 365 E4 サブスクリプションをキャンセルする](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>手順 1: 新しいサブスクリプションを購入する

新しいサブスクリプションをまだお持ちでない場合は、 [別の Microsoft 365 for business サブスクリプションを購入](../buy-another-subscription.md)することができます。

既にサブスクリプションを所有している場合は、次の手順に進みます。

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>手順 2: サブスクリプションに適切な数のライセンスがあることを確認する

次の手順に進む前に、新しいサブスクリプション内のすべてのサービスが設定されていることを確認することが重要です。 最初に確認したときにサブスクリプションの準備ができていない場合は、後でもう一度試してください。

> [!NOTE]
> 請求書による新しいサブスクリプションの支払いを選択した場合は、与信審査が必要な場合があります。 サブスクリプションが使用可能になるまでに、最大2営業日かかることがあります。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [ **サブスクリプションの状態** ] ドロップダウンから、[ **アクティブ**] を選択します。
3. 新しいサブスクリプションが表示されていること、およびライセンスの数が Office 365 E4 のライセンス数と同じであることを確認してください。
4. 追加のライセンスを購入する必要がある場合は、「 [サブスクリプションライセンスを購入または削除](../licenses/buy-licenses.md)する」の手順を実行します。

### <a name="step-3-reassign-licenses-to-users"></a>手順 3: ユーザーにライセンスを再割り当てする

Microsoft 365 管理センターを使用して、一度に最大20人のユーザーのライセンスを再割り当てすることができます。 方法については、「 [ユーザーを別のサブスクリプションに移動する](move-users-different-subscription.md)」を参照してください。

> [!TIP]
> ユーザー数が多い場合は、 [Office 365 PowerShell を使用してユーザーライセンスを一括で割り当てる](https://docs.microsoft.com/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell)ことができます。

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>手順 4: Office 365 E4 サブスクリプションをキャンセルする

すべてのユーザーが新しいサブスクリプションに再割り当てされたら、 [Office 365 E4 サブスクリプションをキャンセル](cancel-your-subscription.md)します。

## <a name="related-content"></a>関連コンテンツ

[別のプランにアップグレードする](upgrade-to-different-plan.md) (記事) \
[サブスクリプションライセンスを購入または削除](../licenses/buy-licenses.md) する (記事) \
[ユーザーへのライセンスの割り当て](../../admin/manage/assign-licenses-to-users.md) (記事)
