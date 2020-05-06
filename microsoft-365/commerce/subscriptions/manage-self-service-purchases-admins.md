---
title: セルフサービス購入を管理する (管理者)
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
- commerce
search.appverid:
- MET150
description: 管理者は、組織内のユーザーによって作成されたセルフサービスの購入を管理する方法について説明します。
ms.openlocfilehash: 7074a829bed3e65a160a9a33afb4f2b130f6c8d1
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046182"
---
# <a name="manage-self-service-purchases-admin"></a>セルフサービスによる購入を管理する (管理者)

管理者は、組織内のユーザーによって作成されたセルフサービスの購入を表示できます。 セルフサービスの各購入について、製品、購入者名、購入したサブスクリプション、有効期限、購入価格、割り当てられたユーザーを確認できます。 組織に必要な場合は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。 セルフサービス購入または一元的に購入した製品に対して、同じデータ管理とアクセスポリシーを使用できます。

組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。 詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="view-self-service-subscriptions"></a>セルフサービスサブスクリプションを表示する

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品</a>の**請求** > ] ページに移動します。

2. [**結果の絞り込み**] の横にある [**アカウントの種類**] ドロップダウンから、[**セルフサービス**] を選択します。

3. サブスクリプションの詳細を表示するには、一覧から1つを選択します。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>セルフサービス購入サブスクリプションのライセンスを持っているユーザーを表示する

1. 管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。

2. [フィルター] アイコンを選択し、[**セルフサービス**] を選択します。

3. ユーザーに割り当てられているライセンスを確認するには、製品を選択します。

    > [!NOTE]
    > 製品に対して複数の購入がある場合、その製品は一度だけ表示され、[**利用可能な数量**] 列には、その製品に対して購入されたすべてのサブスクリプションの合計が表示されます。

4. **ユーザー**リストは、セルフサービス購入を行ったユーザーの名前によってグループ化されます。

5. これらのサブスクリプションのライセンスを持つユーザーの一覧をエクスポートするには、エクスポートするサブスクリプションを選択し、[**ユーザーのエクスポート**] を選択します。

## <a name="disable-or-enable-self-service-purchases"></a>セルフサービス購入を無効または有効にする

組織内のユーザーに対してセルフサービス購入を無効または有効にすることができます。 **MSCommerce** PowerShell モジュールには、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御できる、 **Allowselfservicepurchase**の**policyid**パラメーターの値が含まれています。

**MSCommerce** PowerShell モジュールを使用して、次のことを行うことができます。

- **Allowselfservicepurchase**パラメーター値&mdash;の既定の状態を表示する (製品によって有効または無効にする)
- 適用可能な製品の一覧、およびセルフサービス購入が有効か無効かを表示する
- 特定の製品の現在の設定を表示または変更して、有効にするか無効にするかを指定します。

詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

## <a name="centralize-licenses-under-a-single-subscription"></a>1つのサブスクリプションでライセンスを一元管理する

セルフサービス購入に割り当てられているユーザーの既存のライセンスを割り当てたり、既存の契約を使用して追加のサブスクリプションを購入したりすることができます。 これらの集中的に購入したライセンスを割り当てた後、purchasers に既存のサブスクリプションをキャンセルするよう要求することができます。

1. グローバル管理者または課金管理者アカウントを使用して、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。

2. [**請求** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">書サービス</a>] ページに移動します。

3. 購入する製品を見つけて選択し、[**購入**] を選択します。

4. 残りの手順を実行して、購入を完了します。

5. 手順6で参照するユーザーの一覧をエクスポートするには、「[セルフサービスで購入したサブスクリプションのライセンスを表示](#view-who-has-licenses-for-a-self-service-purchase-subscription)する」の手順を実行します。

6. 他のサブスクリプションにライセンスを持つすべてのユーザーにライセンスを割り当てます。 詳細な手順については、「[ユーザーへのライセンスの割り当て](../../admin/manage/assign-licenses-to-users.md)」を参照してください。

7. セルフサービス購入サブスクリプションを購入したユーザーに連絡して、それを取り消すように依頼します。

## <a name="need-help-contact-us"></a>サポートが必要な場合 ご連絡ください。

セルフサービス購入に関してよく寄せられる質問については、「[セルフサービス購入](self-service-purchase-faq.md)に関する FAQ」を参照してください。

ご質問がある場合やセルフサービス購入に関するヘルプが必要な場合は、[サポートにお問い合わせください](../../admin/contact-support-for-business-products.md)。
