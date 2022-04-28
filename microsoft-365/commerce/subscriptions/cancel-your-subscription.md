---
title: 一般法人向けサブスクリプションをキャンセルします。
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
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
- commerce_subscriptions
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: Microsoft 365 管理センターで、Dynamics 365、Intune、Power Platform、および一般法人向け Microsoft 365 の試用版または有料サブスクリプションをキャンセルする方法について説明します。
ms.date: 04/22/2022
ms.openlocfilehash: 5dbf455b2c90a51aadd5d2e93b0739f93d138841
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092571"
---
# <a name="cancel-your-business-subscription"></a>一般法人向けサブスクリプションをキャンセルします。

> [!IMPORTANT]
> - この記事は、Dynamics 365、Intune、Power Platform、および一般法人向け Microsoft 365 サブスクリプションにのみ適用されます。 Microsoft 365 Family または Personal をお持ちの場合は、「[Microsoft 365 サブスクリプションのキャンセル](https://support.microsoft.com/office/cancel-a-microsoft-365-subscription-46e2634c-c64b-4c65-94b9-2cc9c960e91b?OCID=M365_DocsCancel_Link)」を参照してください。
> - Microsoft の担当者またはリセラー パートナーを通じてサブスクリプションを購入した場合、日割り計算による払い戻しを取り消すための 7 日間があります。 サブスクリプションをキャンセルするには、販売者またはパートナーにお問い合わせください。 [パートナーについての詳細情報](../manage-partners.md#what-can-a-partner-do-for-my-organization-or-school)をご覧ください。
> - 組織がチリに所在し、チリのパートナーを通じてサブスクリプションを購入した場合、日割り計算による払い戻しを取り消すための 10 日間があります。

サブスクリプションをキャンセルする場合は、[継続請求をオフにする](renew-your-subscription.md)のが最も簡単な方法です。 継続請求をオフにした場合、サブスクリプション期間の最後に有効期限が切れるまで、サブスクリプションを引き続き使用できます。 直ちにキャンセルする場合は、この記事の情報と手順を使用します。

## <a name="before-you-begin"></a>開始する前に

- この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」をご覧ください。
- サブスクリプションをキャンセルする前に、ユーザーが確実に[データを保存](#save-your-data)することを確認してください。
- サブスクリプションで使用する独自のドメイン名を追加した場合、サブスクリプションをキャンセルする前に、[そのドメインを削除](../../admin/get-help-with-domains/remove-a-domain.md)する必要があります。
- ドメイン サブスクリプションがある場合は、そのサブスクリプションの他の料金を防ぐために、[継続請求をオフにします](renew-your-subscription.md)。

## <a name="determine-your-cancellation-options"></a>キャンセル オプションを決定する

> [!IMPORTANT]
> 続行する前に、[請求プロファイルを持っているかどうかを確認します](../billing-and-payments/manage-billing-profiles.md#view-my-billing-profiles)。

### <a name="if-you-have-a-billing-profile"></a>請求プロファイルがある場合

サブスクリプションの開始または更新後 7 日以内にキャンセルした場合にのみ、キャンセルして日割り計算されたクレジットを受け取るか、払い戻しを受けることができます。 この限られた時間枠内にキャンセルした場合、日割り計算された金額は次の請求書に含められるか、次の請求サイクルで返金されます。

サブスクリプションの開始または更新後 7 日以内にキャンセルする必要がある場合は、この記事で後述する「[サブスクリプションをキャンセルする手順](#steps-to-cancel-your-subscription)」を参照してください。

7 日以上経過した場合は、[継続請求を無効にします](renew-your-subscription.md)。これにより、サブスクリプションに対してもう一度課金されるのを防ぎ、サブスクリプションの残りの期間、製品とサービスへのアクセスを維持できます。

### <a name="if-you-dont-have-a-billing-profile"></a>請求プロファイルがない場合

サブスクリプションを開始または更新した後にキャンセルした場合は、日割り計算されたクレジットまたは払い戻しを受け取ります。 日割り計算された金額は次の請求書に含められるか、次の請求サイクルで返金されます。

試用版または有料サブスクリプションをキャンセルする手順は、サブスクリプションのライセンスの数によって異なります。 次の表に、ライセンスの数に基づいて実行できる手順を示します。

|サブスクリプションがある場合  |できます  |
|--------------|--------------|
|25 個以下のライセンス  | <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>でオンラインでの試用版または有料サブスクリプションを[キャンセルするには、以下の手順を使用します](#steps-to-cancel-your-subscription)。        |
|25 個を越えるライセンス   | ライセンスの数を 25 個以下に減らしてから、[以下の手順を使用してキャンセルします](#steps-to-cancel-your-subscription)。      |

ライセンスの数を減らすことができない場合は、[継続請求をオフにします](renew-your-subscription.md)。これにより、サブスクリプションに対してもう一度課金されるのを防ぎ、サブスクリプションの残りの期間、製品とサービスへのアクセスを維持できます。

サブスクリプションをキャンセルできない場合は、[サポートにお問い合わせください](../../admin/get-help-support.md)。

## <a name="steps-to-cancel-your-subscription"></a>サブスクリプションをキャンセルする手順

> [!NOTE]
> Microsoft 365 Business Premium など、同じ製品に対して複数のサブスクリプションがある場合、1 つのサブスクリプションをキャンセルしても、他の購入したライセンスやサービスに影響はありません。

::: moniker range="o365-worldwide"

1. Microsoft 365 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">お使いの製品</a>] ページの順に移動します。

::: moniker-end

2. キャンセルするサブスクリプションを見つけて、3 つのドット (その他の操作) を選択してから、**[サブスクリプションのキャンセル]** を選択します。

3. **[サブスクリプションのキャンセル]** ウィンドウで、キャンセルする理由を選択します。必要に応じて、フィードバックを提供します。

4. **[保存]** を選択します。

これでサブスクリプションは **[無効]** 状態で表示され、削除されるまで機能が制限されます。一般法人向け Microsoft 365 の有料サブスクリプションをキャンセルした場合に予期される動作の詳細については、「[一般法人向け Microsoft 365 のサブスクリプションが終了したとき、データとアクセスはどうなりますか?](what-if-my-subscription-expires.md)」を参照してください。

> [!IMPORTANT]
> サブスクリプションを明示的に削除すると、**期限切れ** や **無効** な状態はスキップされ、OneDrive を含む SharePoint Online のデータやコンテンツは直ちに削除されます。

## <a name="save-your-data"></a>データを保存する

キャンセルが有効になると、ユーザーはデータにアクセスできなくなります。サブスクリプションをキャンセルする前に、ユーザーに OneDrive for Business または SharePoint Online ファイルを別の場所に保存するよう伝えます。残された顧客データは 30 日を過ぎると削除される可能性があり、キャンセル後、180 日以内に削除されます。

- メール、連絡先、タスク、予定表などの情報を別のアカウントに移動するには、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)」を参照してください。
- SharePoint Online 環境 (OneDrive for Business またはチーム サイト) からドキュメント ライブラリやリスト コンテンツ (連絡先など) を保存するには、「[SharePoint Online コンテンツの手動移行に関する情報](/sharepoint/troubleshoot/migration-tool/content-manual-migration)」を参照してください。

## <a name="next-steps"></a>次の手順

### <a name="uninstall-office-optional"></a>Office をアンインストールする (省略可能)

サブスクリプションをキャンセルし、Microsoft 365 を含む[別のサブスクリプションにユーザーを移動](move-users-different-subscription.md)しなかった場合、Microsoft 365 は機能制限モードで実行されます。このような場合、ユーザーはドキュメントの読み取りおよび印刷だけを実行でき、Microsoft 365 アプリケーションに[ライセンスのない製品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)が表示されます。混乱を避けるために、ユーザーのコンピューターから [Office をアンインストールする](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)よう伝えます。

### <a name="close-your-account-optional"></a>アカウントの使用を停止する (省略可能)

Microsoft でのアカウントの使用を完全に停止する場合は、「[アカウントの使用を停止する](../close-your-account.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションを更新する](renew-your-subscription.md) (記事)
[サブスクリプションを再度有効にする](reactivate-your-subscription.md) (記事)
[ユーザーを別のサブスクリプションに移動する](move-users-different-subscription.md) (記事)
