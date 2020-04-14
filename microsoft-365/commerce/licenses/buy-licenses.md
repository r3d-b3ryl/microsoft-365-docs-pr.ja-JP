---
title: サブスクリプション ライセンスを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: Office 365 for business サブスクリプションのライセンスを追加および削除する方法について説明します。
ms.openlocfilehash: abfa479d991bac72bd3e9e5c1c422368758b17a7
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240289"
---
# <a name="manage-subscription-licenses"></a>サブスクリプション ライセンスを管理する

次の手順を使用して、サブスクリプションのライセンスを追加または削除できます。

ユーザーに割り当てられているライセンスは、サブスクリプションから削除することはできません。 現在他のユーザーに割り当てられているライセンスを削除する場合は、サブスクリプションからライセンスを削除する前に、[ユーザーからライセンスを削除](../../admin/manage/remove-licenses-from-users.md)する必要があります。

## <a name="add-or-remove-licenses-for-your-business-subscription"></a>ビジネス向けサブスクリプションのライセンスを追加または削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品とサービス]</a> ページに移動します。

2. [ **Products & services** ] ページで、ライセンスを追加または削除するサブスクリプションを検索し、[ライセンスの**追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [**ライセンスの総数**] ボックスにこのサブスクリプション用に必要なライセンスの総数を入力し、[**変更の送信**] を選択します。 たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。 5個を削除する場合は、95と入力します。

新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。

2. [**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [**ライセンスの総数**] ボックスに、このサブスクリプションに必要なライセンスの合計数を入力し、[ **Submit** \> **閉じる**の送信] を選択します。 たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。 5個を削除する場合は、95と入力します。

新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。

2. [**サブスクリプション**] ページで、ライセンスを追加または削除するサブスクリプションを選択し、[ライセンスの**追加/削除**] を選択します。

    [[ライセンスの追加/削除] のリンクが表示されない場合](#what-if-i-dont-see-the-addremove-licenses-link)

3. [**ライセンスの総数**] ボックスに、このサブスクリプションに必要なライセンスの合計数を入力し、[ **Submit** \> **閉じる**の送信] を選択します。 たとえば、100 のライセンスがあり、さらに 5 つ追加する必要がある場合は、105 と入力します。 5個を削除する場合は、95と入力します。

新しいライセンスを購入したら、必ず[ユーザーにライセンスを割り当て](../../admin/manage/assign-licenses-to-users.md)てください。

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>[ライセンスの追加/削除] のリンクが表示されない場合

次の表に、[**ライセンスの追加/削除**] リンクが使用できない可能性がある理由と、その方法について説明します。

|理由  |説明  |解決方法  |
|---------|---------|---------|
|信用度チェックが保留中です。 |与信審査が保留中の場合、"与信審査待ち" のメッセージが表示され、その与信審査が完了するまで、ライセンスの購入ができません。  | 後で、与信審査が完了しているかどうかを確認します。 通常、与信審査が完了するまで 2 営業日かかります。<br>与信審査が完了したら、[ **ユーザー**] セクションに [ **ライセンスの追加/削除**] のリンクが表示されます。 その場合は、「[サブスクリプションライセンスの管理](#manage-subscription-licenses)」にアクセスしてください。 |
|プロダクトキーを使用してサブスクリプションをアクティブ化しました。| サブスクリプションを購入し、25 桁のプロダクト キーでライセンス認証を行っていると、"プリペイド" と表示されます。  |[プロダクトキーを使用して有料のサブスクリプションにライセンスを追加する](add-licenses-using-product-key.md)を参照してください。 |
|パートナーを通じてサブスクリプションを購入した場合。 | サブスクリプションがパートナー経由で購入されている場合、ボリューム ライセンス サービス センター (VLSC) のリンクが表示されます。 | [ボリュームライセンスサービスセンター経由で購入したサブスクリプションにライセンスを追加するを](add-licenses-bought-through-vlsc.md)参照してください。 |
|販売店からサブスクリプションを購入した場合。|| クラウド ソリューション プロバイダー (CSP) パートナーを介してサブスクリプションを購入した場合、ライセンスを追加購入するには、その CSP パートナーに連絡する必要があります。        |
|試用版サブスクリプションがあります。 |Office 365 の試用版では、"試用版" というテキストが表示されます。 | 最初に試用版サブスクリプションを購入する必要があります。その後、ライセンスを追加することができます。 [無料の試用版から、「Office 365 for business のサブスクリプションを購入する](../buy-a-subscription-from-your-free-trial.md)」を参照してください。|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>お客様のビジネス向けサブスクリプションのためのライセンス購入について知っておくべきこと

### <a name="buying-licenses"></a>ライセンスを購入する

- ライセンスを購入するには、グローバル管理者または課金管理者である必要があります。 詳細については、「[管理者の役割につい](../../admin/add-users/about-admin-roles.md)て」を参照してください。
- ライセンスを購入し、同時にサブスクリプションに新しいユーザーを追加するには、「[Office 365 にユーザーを個別に、またはまとめて追加する - 管理者向けヘルプ](../../admin/add-users/add-users.md)」を参照してください。

### <a name="license-availability"></a>ライセンスの可用性

- サブスクリプションの支払いにクレジット カードまたは銀行口座を使用している場合、購入した新しいライセンスは注文確認の受け取り直後に使用可能になります。請求書支払いの場合は、与信審査を待機する必要があり、その後で新しいライセンスが使用可能になります。

  > [!NOTE]
  > 一部の国または地域では、銀行口座引き落としによる支払いを利用できません。

- プロダクトキーを使用してサブスクリプションを前払いした場合は、新しいライセンスの追加コストをカバーするクレジットカードまたは銀行口座を追加することによって、ライセンスを追加できます。 新しいライセンスを購入すると、追加した新しいライセンスの数を含む 2 つ目のサブスクリプションが追加されます。 たとえば、5 ライセンスのサブスクリプションを前払いしていて、その後さらに 10 ライセンスを購入した場合は、5 個の前払いライセンスを含むサブスクリプションと、10 個の新しいライセンスを含むサブスクリプションの 2 個のサブスクリプションを所有することになります。

### <a name="billing-statements"></a>請求明細書

- クレジット カードまたは銀行口座で支払う場合、新しいライセンスの購入に対する請求は 2 日後にクレジット カードの明細に表示されます。
- 請求書で支払い場合、新しいライセンスの購入に対する請求は次の請求明細に表示されます。
- 請求期間の途中で新しいライセンスを購入した場合、最初の請求明細で一部だけ請求されることがあります。残りの金額は次の請求明細に含まれます。

## <a name="related-articles"></a>関連記事

[サブスクリプションとライセンスを理解する](subscriptions-and-licenses.md)

[サブスクリプションのライセンスを購入する](buy-licenses.md)

[別のサブスクリプションを購入する](../buy-another-subscription.md)

[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md)

[Yammer ユーザー ライセンスを管理する](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)