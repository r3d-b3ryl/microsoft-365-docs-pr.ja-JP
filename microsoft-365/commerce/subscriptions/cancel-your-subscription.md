---
title: サブスクリプションをキャンセルする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: Microsoft 365 管理センターで、Dynamics 365、Intune、Power Platform、および一般法人向け Microsoft 365 の試用版または有料サブスクリプションをキャンセルする方法について説明します。
ms.date: 01/20/2022
ms.openlocfilehash: 2d800fbba8ce2290de395179589b1d4110cd1345
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322580"
---
# <a name="cancel-your-subscription"></a>サブスクリプションをキャンセルする

サブスクリプションは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 356 管理センター</a>でいつでもキャンセルできます。 ただし、払い戻しを受けるには、特定の払い戻しの適格性要件を満たしている必要があります。 詳細については、「[払い戻しの適格性を理解する](#understand-refund-eligibility)」を参照してください。

Microsoft 365 Business Premium など、同じ製品に対して複数のサブスクリプションがある場合、1 つのサブスクリプションをキャンセルしても、他の購入したライセンスやサービスに影響はありません。

> [!IMPORTANT]
> この記事は、Dynamics 365、Intune、Power Platform、および一般法人向け Microsoft 365 サブスクリプションにのみ適用されます。 Microsoft 365 Family または Personal をお持ちの場合は、「[Microsoft 365 サブスクリプションのキャンセル](https://support.microsoft.com/office/cancel-a-microsoft-365-subscription-46e2634c-c64b-4c65-94b9-2cc9c960e91b?OCID=M365_DocsCancel_Link)」を参照してください。

## <a name="before-you-begin"></a>開始する前に

この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」をご覧ください。

## <a name="understand-refund-eligibility"></a>払い戻しの適格性を理解する

### <a name="if-you-have-a-billing-profile"></a>請求プロファイルがある場合

既に支払った未使用時間の日割り払いを受け取るには、有料サブスクリプションの開始から 72 時間以内にキャンセルする必要があります。 72 時間後の払い戻しはできません。

たとえば、1 つのライセンスに対して毎月 $20 を支払う 1 年間のサブスクリプションを購入したとします。 サブスクリプションを 2022 年 2 月 1 日の午前 11 時に購入し、2022 年 2 月 3 日の午前 11 時にキャンセルすることにしました。 サブスクリプションを保持した 2 日間で $1.43 が差し引かれ、$18.57 の日割り払いを受け取ります。

**請求プロファイルがあるかどうかわかりませんか?** 請求プロファイルがあるかどうかを確認する方法については、「[請求プロファイルの表示](../billing-and-payments/manage-billing-profiles.md#view-my-billing-profiles)」を参照してください。

### <a name="if-you-dont-have-a-billing-profile"></a>請求プロファイルがない場合

次の表を使用して、サブスクリプションを自分でキャンセルできるかどうかを判断してください。

|サブスクリプションがある場合  |できます  |
|--------------|--------------|
|25 個以下のライセンス  | 試用版または有料サブスクリプションは、いつでも <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 356 管理センター</a>でオンラインでキャンセルできます。        |
|25 個を越えるライセンス   | ライセンスの数を 25 以下に減らして再試行するか、[サポートに連絡してサブスクリプションをキャンセルしてください](../../admin/get-help-support.md)。        |

請求プロファイルがないサブスクリプションの場合、サブスクリプションを購入または更新した後、限られた時間枠内でのみキャンセルできます。 キャンセル期間が過ぎた場合は、[定期的な請求をオフにして](renew-your-subscription.md)、期間の終了時にサブスクリプションをキャンセルします。

限られた時間枠内でキャンセルした場合、日割りのクレジットは次の請求期間内に返金されます。

## <a name="steps-to-cancel-your-subscription"></a>サブスクリプションをキャンセルする手順

サブスクリプションで使用する独自のドメイン名を追加した場合、サブスクリプションをキャンセルする前に、ドメインを削除する必要があります。詳細については、「[ドメインを削除する](../../admin/get-help-with-domains/remove-a-domain.md)」を参照してください。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

2. キャンセルするサブスクリプションを見つけて、3 つのドット (その他の操作) を選択してから、**[サブスクリプションのキャンセル]** を選択します。

3. **[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。必要に応じて、フィードバックを提供します。

4. **[保存]** を選択します。

これでサブスクリプションは **[無効]** 状態で表示され、削除されるまで機能が制限されます。一般法人向け Microsoft 365 の有料サブスクリプションをキャンセルした場合に予期される動作の詳細については、「[一般法人向け Microsoft 365 のサブスクリプションが終了したとき、データとアクセスはどうなりますか?](what-if-my-subscription-expires.md)」を参照してください。

> [!NOTE]
> サブスクリプションを明示的に削除すると、期限切れや無効なステージはスキップされ、OneDrive を含む SharePoint Online のデータやコンテンツは直ちに削除されます。

## <a name="what-happens-when-you-cancel-a-subscription"></a>サブスクリプションをキャンセルした場合

有効期限が終了する前にサブスクリプションをキャンセルすると、サブスクリプションは無効状態に直接移行します。無効状態は、ほとんどのサブスクリプションおよびほとんどの国と地域で 90 日間です。サブスクリプションが無効な状態でも、管理者は引き続き組織のデータにアクセスしてバックアップすることができます。ただし、特にお持ちのサブスクリプションが 1 つしかない場合は、サブスクリプションをキャンセルする前に、[データをバックアップする](back-up-data-before-switching-plans.md)ことをお勧めします。管理者は、サブスクリプションが無効状態の場合でも再度有効にすることもできます。

90 日後、サブスクリプションの状態は削除済みになります。 残されたデータは 90 日後に削除され、キャンセル後、180 日以内に削除されます。 削除済みの状態になるまで、キャンセルしたサブスクリプションから支払い方法を削除することはできません。

### <a name="what-to-expect-for-you-and-your-users-if-you-cancel-a-subscription"></a>サブスクリプションをキャンセルした場合に想定される動作
  
- **管理者アクセス:** 管理者は、サインインして管理センターにアクセスでき、必要に応じて、他のサブスクリプションを購入できます。全体管理者または課金管理者の場合は、すべてのデータを維持したまま [サブスクリプションを再アクティブ化](reactivate-your-subscription.md)できる期間が 90 日間あります。

- **ユーザー アクセス** ユーザーは、OneDrive for Business などのサービスの使用や、顧客データ (チーム サイトのメール、ドキュメントなど) へのアクセスができなくなります。Word、Excel などの Office アプリケーションは、最終的に読み取り専用の機能制限モードになり、 [ライセンスのない製品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。

詳細については、「[サブスクリプションが終了したとき、データとアクセスはどうなりますか?](what-if-my-subscription-expires.md)」を参照してください。

> [!IMPORTANT]
> 一般的な無効期間が終了する前にサブスクリプション データを削除する場合は、[アカウントの使用を停止する](../close-your-account.md)ことができます。

## <a name="other-steps-you-might-have-to-take"></a>必要になる可能性のあるその他の手順

### <a name="change-custom-domain-settings"></a>カスタム ドメインの設定を変更する

サブスクリプションでカスタム ドメインを使用している場合、サブスクリプションをキャンセルする前に、いくつかの追加手順を実行する必要があります。カスタム ドメインがない場合は、先に進んで[データを保存](#save-your-data)します。

#### <a name="change-your-domain-nameserver-records-if-needed"></a>ドメインのネームサーバー レコードを変更する (必要な場合)

カスタム ドメインをセットアップすると、ドメインが Microsoft 365 サービスで機能するように、DNS レコードが追加されます。ドメインを削除する前に、DNS ホストでドメインの MX レコードなどの DNS レコードを更新してください。

たとえば、DNS ホストで MX レコードを変更します。ドメインに送信される電子メールは、Microsoft アドレスに送信されなくなり、代わりに新しいメール プロバイダーに送信されます。(MX レコードは、ドメインの電子メールがどこに送信されるかを決定します。)

- ネームサーバー (NS) レコードが [Microsoft 365 ネームサーバーをポイントしている](../../admin/setup/add-domain.md)場合、新しい DNS ホストをポイントするように NS レコードを変更するまでは、MX レコードの変更は有効になりません (手順 2 を参照)。

- MX レコードを更新する前に、電子メールを切り替える日付、使う予定の新しいメール プロバイダーをユーザーに通知します。 また、ユーザーが既存の Microsoft メールを新しいプロバイダーに移行する場合は、追加の手順を実行する必要があります。

- MX レコードを変更する日に、この記事の残りの手順に従います。

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>(カスタム ドメインを使用している場合) ドメイン MX レコードとその他の DNS レコードを更新する

ドメインをセットアップするときに、ネームサーバー (NS) レコードを Microsoft 365 に切り替えた場合は、MX レコード、および使用する予定の DNS ホストの他の DNS レコードを設定または更新してから、NS レコードをその DNS ホストに変更する必要があります。

ドメインをセットアップするときに NS レコードを切り替えなかった場合は、MX レコードを変更すると、電子メールがすぐに新しいアドレスに送信されます。

NS レコードを変更する方法については、「[ドメインを削除する](../../admin/get-help-with-domains/remove-a-domain.md)」を参照してください。

### <a name="save-your-data"></a>データを保存する

キャンセルが有効になると、ユーザーはデータにアクセスできなくなります。サブスクリプションをキャンセルする前に、ユーザーに OneDrive for Business または SharePoint Online ファイルを別の場所に保存するよう伝えます。残された顧客データは 30 日を過ぎると削除される可能性があり、キャンセル後、180 日以内に削除されます。

- メール、連絡先、タスク、予定表などの情報を別のアカウントに移動するには、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)」を参照してください。

- SharePoint Online 環境 (OneDrive for Business またはチーム サイト) からドキュメント ライブラリやリスト コンテンツ (連絡先など) を保存するには、「[SharePoint Online コンテンツの手動移行に関する情報](/sharepoint/troubleshoot/migration-tool/content-manual-migration)」を参照してください。

### <a name="uninstall-office-optional"></a>Office をアンインストールする (省略可能)

サブスクリプションをキャンセルし、Microsoft 365 を含む[別のサブスクリプションにユーザーを移動](move-users-different-subscription.md)しなかった場合、Microsoft 365 は機能制限モードで実行されます。このような場合、ユーザーはドキュメントの読み取りおよび印刷だけを実行でき、Microsoft 365 アプリケーションに[ライセンスのない製品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。混乱を避けるために、ユーザーのコンピューターから [Office をアンインストールする](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)よう伝えます。

## <a name="next-steps"></a>次の手順

Microsoft でのアカウントの使用を完全に停止する場合は、「[アカウントの使用を停止する](../close-your-account.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションを更新する](renew-your-subscription.md) (記事)
[サブスクリプションを再度有効にする](reactivate-your-subscription.md) (記事)
[ユーザーを別のサブスクリプションに移動する](move-users-different-subscription.md) (記事)
