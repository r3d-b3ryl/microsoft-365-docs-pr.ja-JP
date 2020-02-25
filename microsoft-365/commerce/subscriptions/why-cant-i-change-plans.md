---
title: ビジネスプランで Office 365 を変更できないのはなぜですか?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ROBOTS: NOINDEX
description: 変更プランを手動で行うか、サポートに連絡しなければならない理由について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 4f193db074dccb8146615b72febc62f47a44b7d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243137"
---
# <a name="why-cant-i-upgrade-plans"></a>プランをアップグレードできないのはなぜですか?

[**アップグレード**] タブにプランが表示されない場合は、プランを自動的にアップグレードできないことを意味します。 場合によっては、アップグレード可能なプランを表示できるように問題を解決したり、代わりにプランを手動でアップグレードまたは変更したりすることができる場合があります。

> [!NOTE]
> この記事は、新しい管理センターに適用されます。 新しい管理センターは、Microsoft 365 のすべての管理者が利用でき、ホームページの上部にある [**新しい管理センター**の切り替え] を選択して選択することができます。 詳細については、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md)」を参照してください。 以前の管理センターに関する記事を表示するには、「 [Office 365 を「ビジネスプラン用に切り替えることができない理由](why-can-t-i-switch-plans.md)」を参照してください。

## <a name="why-are-there-no-plans-listed-to-upgrade"></a>アップグレードする計画が表示されないのはなぜですか?

### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a>ライセンス数を超えるユーザーがいるため、今はサブスクリプションをアップグレードできません。

プランを自動的にアップグレードするには、すべてのユーザーに有効なライセンスが割り当てられている必要があります。 購入した数より多くのライセンスを割り当てている場合は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに、解決する必要があるライセンスの競合があるという警告が表示されます。 [ライセンスの競合を解決する方法について説明](../../admin/manage/resolve-license-conflicts.md)します。 ライセンスの競合を解決した後、[**アップグレード**] タブに [プラン] が表示されます。サポートされていない場合は、[手動でプランを変更](change-plans-manually.md)するか、[サポート] を[呼び出す](../../admin/contact-support-for-business-products.md)ことができます。

### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a>このサブスクリプションは完全に設定されていないか、サービス\'が使用できないため、今すぐサブスクリプションをアップグレードすることはできません。

たとえば、いずれかのサービスにインシデントがある場合は、すべてのサービスが正常な状態になるまでアップグレードできません。 プロビジョニングまたはサービスの正常性の問題があるかどうかを確認するには、管理センターで、**ヘルス** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">サービスの正常</a>性ページに移動します。

サービスが完全にはプロビジョニングされていないか、サービス正常性に問題があることがわかった場合は、サービスが利用可能になるまで数時間待ってから、もう一度試してください。 それでも問題が解決しない場合は、サポートにお[問い合わせ](../../admin/contact-support-for-business-products.md)ください。

### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a>別のプランがアップグレード中であるか、与信審査が保留中であるため、プランをアップグレードできません。

プランをアップグレードする前に、与信審査が完了するまで待機します。 与信審査の完了には、最大で 2 営業日かかる場合があります。

### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a>現時点では、このサブスクリプションはアップグレード対象にはなりません。

プランを[手動で変更](change-plans-manually.md)するか、[サポートに連絡](../../admin/contact-support-for-business-products.md)することができます。

### <a name="i-see-a-different-message-than-whats-listed-here"></a>ここで挙がっているものとは別のメッセージが表示されます。

プランを[手動で変更](change-plans-manually.md)するか、[サポートに連絡](../../admin/contact-support-for-business-products.md)することができます。

## <a name="additional-reasons-you-cant-upgrade"></a>アップグレードできないその他の理由

### <a name="you-have-two-or-more-plans-for-the-same-product"></a>同じ製品に対して2つ以上のプランがある。

[**アップグレード**] タブは、すべてのユーザーが同じプランを購読している場合にのみ使用できます。 たとえば、2つの Office 365 Business Premium プランがある場合は、そのうちの1つを別のプランに自動的にアップグレードすることはできません。

### <a name="you-have-a-prepaid-plan"></a>プリペイド (先払い) プランを使用している

サブスクリプションを事前に購入している場合は、[プランを手動で変更](change-plans-manually.md)することができます。 ただし、現在のプランの期限が切れる前にプランをアップグレードする場合は、現在のサブスクリプションに残っている未使用期間のクレジットを受け取ることはありません。

ヘルプの[サポートを呼び出す](../../admin/contact-support-for-business-products.md)こともできます。

### <a name="you-have-a-government-or-non-profit-plan"></a>政府機関向けプランまたは非営利団体向けプランに加入している

政府機関または非営利団体のプランをご利用の場合は、[プランを手動で変更](change-plans-manually.md)するか、[サポートに問い合わせ](../../admin/contact-support-for-business-products.md)てください。

### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a>アップグレードの対象となるサブスクリプションに一時的な問題がある

サービスが大量のプランをアップグレードする過程にあるため、[**アップグレード**] タブにプランが表示されない場合があります。 最初の試行から 1 時間ほど待って、もう一度試してください。

### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a>アップグレード先のプランがサポートされていません

プランをアップグレードすると、現在のプランのサービスに基づいて、アップグレードに使用できるプランが表示されます。 アップグレードできるのは、Exchange Online や SharePoint Online などのデータ関連サービスを持つプランのみです。または、それより上位のバージョンにアップグレードすることもできます。 これにより、ユーザー\'はアップグレード中にこれらのサービスに関連するデータを失うことがなくなります。

プランが自動的にアップグレードされない場合は、代わりにプランを[手動で変更](change-plans-manually.md)することができます。 ヘルプの[サポートを呼び出す](../../admin/contact-support-for-business-products.md)こともできます。

### <a name="your-subscription-has-an-add-on"></a>サブスクリプションにアドオンがあります

サブスクリプションにアドオンがある場合は、[プランを手動で変更](change-plans-manually.md)できる場合があります。

### <a name="your-subscription-has-an-unpaid-balance"></a>サブスクリプションに未払い残高があります

これを解決するには、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> ] ページでサブスクリプションを検索し、[**課金**] セクションの [**今すぐ購入**] リンクを選択します。 支払いを行った後で、[**アップグレード**] タブをもう一度確認してください。

## <a name="call-support-to-help-you-change-plans"></a>プランを変更するためのサポートへのお問い合わせ
[Microsoft サポートに連絡する](../../admin/contact-support-for-business-products.md)