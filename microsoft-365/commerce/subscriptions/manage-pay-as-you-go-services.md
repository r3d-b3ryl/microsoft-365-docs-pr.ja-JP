---
title: Microsoft 365 管理センターでサブスクリプションの従量課金制を有効にする
f1.keywords:
- MACBillingPurchasePDPPayG
- MACBillingPurchaseIDPPayG
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: nalinkla, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- okr_smb
search.appverid: MET150
ROBOTS: noindex, nofollow
description: 通話プランでサブスクリプションを購入し、Microsoft Teams通話の超過分を有効にする方法について説明します。
ms.date: 07/15/2022
ms.openlocfilehash: ba0dd763d106a3f9147fae8ce22fbcd5d2f63017
ms.sourcegitcommit: adc4e5707aa074fc4aa0cb9e8c2986fc8b88813c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67112001"
---
# <a name="enable-pay-as-you-go-for-your-subscription"></a>サブスクリプションの従量課金制を有効にする

既定では、通話プランを持つサブスクリプションを購入すると、プランに含まれる分数に制限されます。 これらの分を使い切った後、ユーザーは次の請求期間まで Teams を呼び出すことはできません。 従量課金制オプションをオンにした場合、ユーザーはプランに含まれる分数 ( *超過と* 呼ばれる) を引き続き呼び出すことができます。 次の請求書には、従量課金制の追加料金が表示されます。

## <a name="before-you-begin"></a>はじめに

通話プランでサブスクリプションを購入し、従量課金オプションを有効にするには、課金アカウントの所有者または課金アカウントの共同作成者である必要があります。 詳細については、「 [課金アカウントについて」](../manage-billing-accounts.md)を参照してください。

## <a name="buy-a-pay-as-you-go-product-in-the-microsoft-365-admin-center-and-enable-overage"></a>Microsoft 365 管理センターで従量課金制の製品を購入し、超過分を有効にする

サブスクリプションが既にある場合は、通話プランを持つ新しいプランを購入し、そのプランの超過オプションを有効にすることができます。

1. Microsoft 365 管理センターで、[**課金**]  >  [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購入とサービス</a>] ページに移動します。
2. 購入する従量課金制の製品 (Office 365 E5など) を検索し、[詳細] を選択 **します**。 従量課金制の製品には、 **PAY-AS-YOU-GO AVAILABLE** タグがあります。
3. 製品の詳細ページで、製品の利用可能なプランを確認し、 **PAY-AS-YOU-GO** タグが付いているプランを選択します。
4. 購入するライセンスの数を入力し、**サブスクリプションの長さと****請求頻度** を選択して、[**購入**] を選択します。
5. 注文の詳細を確認し、[ **注文**] を選択します。
6. 確認ウィンドウで、 **通話プランで [超過分を有効にする**] を選択します。 このリンクをクリックすると、サブスクリプションのインベントリの詳細ページに移動します。
7. [ **従量課金制サービス** ] セクションで、製品名を選択します。 従 **量課金制の変更オプション ウィンドウが** 開きます。
8. [ **従量課金制の変更] オプション** ウィンドウで、[ **オン**] を選択し、[ **保存**] を選択します。

## <a name="manage-pay-as-you-go-for-an-existing-subscription"></a>既存のサブスクリプションの従量課金制を管理する

従量課金制サービスを含むサブスクリプションが既にある場合は、必要に応じてオンまたはオフを切り替えることができます。

1. Microsoft 365 管理センターで、**[課金]**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページに移動します。
2. [ **製品** ] タブで、従量課金制サービスを管理するサブスクリプションを選択します。
3. **[従量課金制サービス]** で、製品名または状態を選択します。
4. [ **従量課金制の変更] オプション** ウィンドウで、[ **オン** ] または [ **オフ]** を選択し、[保存] を選択 **します**。

## <a name="view-current-overage-charges"></a>現在の超過料金を表示する

管理センターの <a href="https://go.microsoft.com/fwlink/p/?linkid=2201187" target="_blank">[コスト管理]</a> ページを使用して、組織の超過料金を追跡できます。 コスト管理の詳細については、[Microsoft 365 管理センターのコスト管理の使用に関するページを](../use-cost-mgmt.md)参照してください。

## <a name="track-teams-call-history-for-your-organization"></a>組織の Teams 通話履歴を追跡する

Microsoft Teams管理センターの **[使用状況レポート** ] ページを使用して、組織の Teams 通話履歴を追跡できます。 ページを表示するには、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2066851" target="_blank">Microsoft Teams管理センター</a>に移動し、[ **Analytics & レポート**] を選択し、[ <a href="https://admin.teams.microsoft.com/analytics/reports" target="_blank">利用状況レポート</a>] を選択します。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 管理センターでコスト管理を使用する](../use-cost-mgmt.md) (記事)
