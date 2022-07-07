---
title: 課金プロファイルを使用したサブスクリプションの支払い
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
search.appverid: MET150
description: 課金プロファイルを使用してサブスクリプションの支払いに使用できる支払い方法について説明します。
ms.custom:
- commerce_billing
- okr_SMB
- AdminSurgePortfolio
ms.date: 05/26/2022
ms.openlocfilehash: cb7d4bec9ae41d05be5b588f78a5197ed9ccbac0
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66685637"
---
# <a name="how-to-pay-for-your-subscription-with-a-billing-profile"></a>課金プロファイルを使用してサブスクリプションに対して支払う方法

サブスクリプションを購入すると、課金プロファイルを使用してサブスクリプションに対して支払いを行います。 課金プロファイルは特定の支払い方法にリンクされ、クレジット カードまたはデビット カード、または請求書を指定できますが、銀行口座にはリンクされません。

アカウントに課金プロファイルがあるかどうかわからない場合は、「[課金プロファイルを理解する](manage-billing-profiles.md)」をご覧ください。 課金プロファイルがない場合は、「 [サブスクリプションの支払い方法」を参照してください](pay-for-your-subscription.md)。

## <a name="paying-with-recurring-billing-turned-on-or-off"></a>定期的な課金を有効または無効にして支払う

既定では、定期的な課金を使用するすべての有料サブスクリプションに対して、定期的な課金が自動的に有効になります。 課金期間ごとに、課金プロファイルに関連付けられている支払い方法に自動的に課金され、その課金プロファイルを使用するすべてのサブスクリプションに対して支払いが行われます。 支払い方法が拒否された場合は、請求書の [ **今すぐ支払う** ] ボタンを使用して、サブスクリプションの 1 回限りの支払いを行うことができます。

課金プロファイルで定期的な課金がオフになっている場合は、課金プロファイルにリンクされている支払い方法に関係なく、請求書の [ **今すぐ** 支払う] ボタンを使用して、請求期間ごとに支払いを行うことができます。 小切手または電子送金 (EFT) で支払うこともできます。 その方法については、請求書の PDF コピーに記載されています。

## <a name="new-regulations-from-the-reserve-bank-of-india"></a>インド準備銀行の新しい規制

2021 年 10 月 1 日以降、インドでの自動支払いでは、一部のクレジット カード取引 (特に 5,000 INR を超えるトランザクション) がブロックされる可能性があります。 この規制のため、Microsoft 365 管理センターで手動で支払いを行う必要がある場合があります。 これらの規制は、使用量に対して請求される合計金額には影響しません。

[定期的な支払いに関するインド準備銀行の規制の詳細については、こちらをご覧ください](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=11668&Mode=0)。

2022 年 9 月 30 日に、Microsoft およびその他のオンライン マーチャントはクレジット カード情報を保存しなくなります。 この規制に準拠するために、Microsoft は保存されているすべてのカードの詳細をMicrosoft 365 管理センターから削除します。 サービスの中断を回避するには、支払い方法を追加し、すべてのサブスクリプションと課金プロファイルに対して 1 回限りの支払いを行う必要があります。

[カードの保存に関するインド準備銀行の規制について説ついては、こちらをご覧ください](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=12211)。

## <a name="paying-by-invoice"></a>請求書での支払い

請求書による支払いが設定されている課金プロファイルがある場合は、小切手または EFT を使用してサブスクリプションの料金を支払うことができます。 また、請求書の [ **今すぐ支払** う] ボタンを使用して、クレジット カードを使用してオンライン支払いを行うこともできます。

請求書で支払う資格を得るには、次のことを行う必要があります。

- 既存の顧客になる
- サブスクリプション代金が特定の金額を超えている (この金額はサービスの場所によって異なります)
- 信用調査に合格する

与信審査が必要な場合、サブスクリプションの購入時に、その必要性がお客様に知らされます。Microsoft からの連絡にご同意いただいた場合、クレジット カードの承認申請に関して詳細な情報が記載されたメールがお客様宛てに送信されます。与信審査は、通常 2 営業日以内で完了します。

課金プロファイルが請求書によってサポートされている場合は、請求明細書を表示する準備が整ったときに電子メールが届きます。 このメールには、請求明細書のコピーは含まれません。 ただし[組織の請求書をメールの添付ファイルとして受け取る](manage-billing-notifications.md#receive-your-organizations-invoices-as-email-attachments)こともできます。 請求明細書には、支払いに関するオプションとその送付先の詳細が記載されています。 課金プロファイルに発注書 (PO) 番号を入力すると、その番号が請求明細書に表示されます。 請求明細書へのアクセスの詳細については、「[課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。

## <a name="where-do-i-send-my-check-or-eft-payment"></a>小切手または EFT の送信はどこでできますか?

お住まいの国または地域で利用できるお支払い方法については、[請求書をご確認ください](view-your-bill-or-invoice.md)。未払い額がわからない場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求書と支払い]</a> ページの **[請求書]** タブで、請求書と請求履歴をオンラインで確認できます。

> [!NOTE]
> 小切手による支払いはいくつかの国のみで利用可能です。

## <a name="can-i-pay-my-invoice-online"></a>請求書をオンラインで支払うことはできますか?

課金プロファイルで定期的な課金がオフになっている場合は、クレジット カードを使用してオンラインで請求書を支払うことができます。 支払いを行うには、Microsoft 365 管理センターの請求書の [**今すぐ支払う**] ボタンを使用します。 請求書を見つけるには、「 [請求書または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。

## <a name="can-i-change-from-my-current-payment-method-to-paying-by-invoice"></a>現在の支払い方法から請求書による支払いに変更できますか?

課金プロファイルがクレジット カードまたはデビット カードでサポートされている場合は、支払い方法を別のクレジット カードまたはデビット カードに変更することしかできません。 請求書による支払いには変更できません。

## <a name="can-i-change-from-paying-by-invoice-to-using-a-different-payment-method"></a>請求書による支払いから別の支払い方法の使用に変更できますか?

請求プロファイルが請求書の支払いによってサポートされている場合、支払い方法を変更することはできません。 請求書の [ **今すぐ支払う** ] ボタンを使用して、クレジット カードまたはデビット カード、または小切手または EFT で支払うことができます。

## <a name="related-content"></a>関連コンテンツ

[支払方法を管理する](manage-payment-methods.md) (article)\
[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)\
[課金内容または請求書の内容を理解する](understand-your-invoice.md) (article)\
