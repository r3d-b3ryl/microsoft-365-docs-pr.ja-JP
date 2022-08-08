---
title: サブスクリプションの支払い
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
search.appverid: MET150
description: Microsoft 365 for business サブスクリプションのお支払いには、クレジット カード、デビット カード、銀行口座をご利用ください。場合によっては、請求書によるお支払いも可能です。
ms.custom:
- commerce_billing
- VSBFY23
- okr_SMB
- fwlink 808700 for SEPA UI glink 906 for older uI
- AdminSurgePortfolio
- business_assist
- AdminTemplateSet
ms.date: 08/04/2022
ms.openlocfilehash: 74b76a8719d57cfd2caabc02ace1e80583db0821
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276593"
---
# <a name="how-to-pay-for-your-subscription"></a>サブスクリプションの支払い方法

> [!IMPORTANT]
> 2021 年 1 月 26 日をもって、ベルギー、フランス、イタリア、ルクセンブルグ、ポルトガル、スペイン、および米国のお客様に、新しい銀行口座をサポートしなくなりました。 これらの国の 1 つで既存のお客様である場合は、良好な状態にある既存の銀行口座でサブスクリプションの支払いを続けることができます。 ただし、銀行口座に新しいサブスクリプションを追加することはできません。

クレジットカード、デビットカード、または銀行口座を使用して、サブスクリプションの支払いを行うことができます。 場合によっては、小切手または銀行口座振込 (EFT) を使用して、請求書で支払うこともできます。 課金プロファイルがある場合、オプションは少し異なります。 詳細については、「[課金プロファイルを使用してサブスクリプションの支払いをする方法](pay-for-subscription-billing-profile.md)」を参照してください。 アカウントに課金プロファイルがあるかどうかわからない場合は、「[課金プロファイルを理解する](manage-billing-profiles.md)」をご覧ください。

**請求書の支払い先をお知りになりたいですか?** 小切手または銀行口座振込 (EFT) で請求書を支払う場合は、「[小切手または EFT の送信はどこでできますか?](#where-do-i-send-my-check-or-eft-payment)」を参照してください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="before-you-begin"></a>はじめに

- この記事で説明する手順を実行するには、グローバル管理者または課金管理者である必要があります。詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
- チェックアウト時に選択するお支払い方法は、今後のすべての請求期間に使用されるお支払い方法です。いつでも変更できます。

## <a name="directives-from-the-reserve-bank-of-india"></a>インド準備銀行からの規制

現在、インド準備銀行の規制により、一部のクレジット カードト取引 (特に 5,000 INR を超える取引) がブロックされています。 これは自動支払いに影響を与える可能性があります。つまり、Microsoft 365 管理センターで手動で支払いを行う必要がある場合があります。 この指令は、使用料金には影響しません。 

[定期的な支払いに関するインド準備銀行の規制の詳細については、こちらをご覧ください](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=11668&Mode=0)。

2022 年 9 月 30 日に、Microsoft およびその他のオンライン マーチャントはクレジット カード情報を保存しなくなります。 Microsoft は保存されているすべてのカードの詳細をMicrosoft 365 管理センターから削除します。 サービスの中断を回避するには、すべてのサブスクリプションと課金プロファイルに対して、支払い方法を追加して、認証する必要があります。

[カードの保存に関するインド準備銀行の規制についての詳細は、こちらをご覧ください](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=12211)。

## <a name="paying-by-credit-or-debit-card-or-bank-account"></a>クレジット カード、デビット カード、または銀行口座引き落としでの支払い

> [!IMPORTANT]
> 一部の国または地域では、銀行口座引き落としによる支払いを利用できません。

サブスクリプションはクレジット カード、デビット カード、または銀行口座引き落としでお支払いいただけます。 これらの支払い方法のいずれかでお支払いの場合、サブスクリプションの有効期限が切れるまで、またはキャンセルされるまで、その支払い方法に引き続き請求されます。 いつでも必要なときに[支払い方法を管理する](manage-payment-methods.md)ことができます。 [組織の請求書をメールの添付ファイルとして受け取る](manage-billing-notifications.md#receive-your-organizations-invoices-as-email-attachments)こともできます。

## <a name="paying-by-invoice"></a>請求書での支払い

場合によっては、小切手または EFT を使用した請求書でサブスクリプションの支払いを行うことができます。 請求書で支払う資格を得るには、次のことを行う必要があります。

- 少なくとも 6 か月間確立されたお客様であり、未払い残高がないこと
- 月に最低 6,000 米国ドルを消費するか、過去 12 か月間のうちいずれかの 3 か月で最低金額を購入する (この金額はサービスの場所によって異なる場合があります)。
- 信用調査に合格する

支払い方法を変更して小切手/電信送金を要求すると、次の 2 つの結果が発生する可能性があります。

- 自動的に承認され、会社に関する情報を求めるメッセージが表示されます。
- 自動的には承認されませんが、[サポート要求](../../admin/get-help-support.md)を送信できます。

与信審査が必要な場合、サブスクリプション購入の際に通知が送信されます。 Microsoft から連絡することをご了承いただいた場合、メールを受信します。メールには、クレジットの承認を申請するうえで詳細な情報が含まれます。 与信審査は、通常 2 営業日内に完了します。

> [!NOTE]
> ブラジルにお住まいのお客様は、Boleto Bancario でサブスクリプションの支払いを行うことができます。 このオプションを選択すると、サブスクリプションの購入により、注文日から 10 日以内に支払いについての連絡が指定のメールに送信されます。 期限は、注文日から 30 日です。 Boleto のメールを受信しない場合は、迷惑メール フォルダーを確認するか、サポートにお問い合わせください。
>
> もしくは、口座間の電子決済により支払いを行うこともできます。 銀行と口座番号は請求書の下部に記載されています。 振替 ID の欄に請求書番号を入力する必要があります。

サブスクリプションを請求書でお支払いになる場合、請求明細書が閲覧できるようになったときにメールを受信します。 このメールには、請求明細書のコピーは含まれません。 ただし[組織の請求書をメールの添付ファイルとして受け取る](manage-billing-notifications.md#receive-your-organizations-invoices-as-email-attachments)こともできます。 請求明細書には、支払いに関するオプションとその送付先の詳細が記載されています。 サブスクリプションを購入するときに発注書番号 (PO) を入力した場合、請求明細書にその番号が表示されます。 請求明細書へのアクセスの詳細については、「[課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。

## <a name="what-if-i-have-an-outstanding-balance"></a>未払額がある場合、どうなりますか。

登録されているお支払い方法に請求できない場合は、問題があることを通知するメールを送信します。 メールには、問題が何であるかが簡単に記載されており、未払いの残高を確認できるリンクが含まれています。 30 日間、数日ごとにトランザクションを再試行し続けます。その間、サブスクリプションは猶予期間中です。 トランザクションが失敗するたびに、失敗に関するメール アラートを受け取ります。

延滞金額のあるお支払い方法を個人的に追加した場合は、**決済残高** を使用して支払いを行うことができます。 延滞金額の支払いに使用する支払い方法は、拒否された支払い方法を使用したすべてのサブスクリプションの新しい支払い方法になります。

1. 管理センターで、**[課金]** > **[請求と支払い]** ページに移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払い方法]</a> タブを選択します。
1. 拒否された支払い方法を示す警告メッセージ。「**Settle balance**」を選択します。
1. 右側のウィンドウで、別の支払い方法を選択するか、**[新しい支払い方法を追加する]** を選択します。
1. お支払い方法の情報を更新したら、**[保存]** を選択します。

サブスクリプションの支払いに使用した支払い方法を追加しなかった場合は、以前に追加した支払い方法または新しい支払い方法に置き換える必要があります。

## <a name="where-do-i-send-my-check-or-eft-payment"></a>小切手または EFT の送信はどこでできますか?

お住まいの国または地域で利用できるお支払い方法については、[請求書をご確認ください](view-your-bill-or-invoice.md)。未払い額がわからない場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求書と支払い]</a> ページの **[請求書]** タブで、請求書と請求履歴をオンラインで確認できます。

> [!NOTE]
> - 小切手による支払いはいくつかの国のみで利用可能です。
> - Microsoft Partner Network (MPN) プログラム (Action Pack サブスクリプション、Silver または Gold コンピテンシー) のメンバーシップ料金を支払う必要がある場合は、[コンピテンシー料金の支払い](/partner-center/mpn-pay-fee-silver-gold-competency?tabs=workspaces-view)に関する記事で MPN の料金を支払う方法をご確認ください。

## <a name="check-or-wire-transfer-payment-processing-time"></a>小切手または電信送金による支払い処理時間

小切手による支払いは、小切手が銀行をクリアしてから 3 ~ 5 営業日後に行われます。 銀行に連絡して、小切手の状態を確認できます。

電信送金によって行われる支払は、転送の種類に応じて処理時間が異なります。

- ACH 国内転送 - 5 営業日。 到着までの 2 日から 3 日間、さらに記帳に 2 日間。
- 電信送金 (国内) - 4 営業日。 到着までの 2 日間、さらに記帳に 2 日間。
- 電信送金 (国際) - 7 営業日。 到着までの 5 日間、さらに記帳に 2 日間。

小切手または電信送金による支払いがアカウントで承認されている場合、支払いの手順は請求書に記載されています。

## <a name="can-i-pay-my-invoice-online"></a>請求書をオンラインで支払うことはできますか?

請求書をオンラインで支払うことはできません。 小切手または EFT のいずれかで送金する必要があります。

## <a name="can-i-change-from-my-current-payment-method-to-paying-by-invoice"></a>現在の支払い方法から請求書による支払いに変更できますか?

サブスクリプションの費用が特定の金額を超えている場合にのみ、請求書による支払いに変更できます。 請求書による支払いに変更する前に、まずクレジット カード、デビット カード、または銀行口座の未払い分を支払う必要があります。 支払い方法を変更する方法については、「[1 つのサブスクリプションの支払い方法を変更する](manage-payment-methods.md#change-a-payment-method-for-a-single-subscription)」を参照してください。

## <a name="can-i-change-from-paying-by-invoice-to-using-a-different-payment-method"></a>請求書による支払いから別の支払い方法の使用に変更できますか?

請求書による支払いから別の支払い方法による支払いに自動的に変更することはできません。 代わりに、クレジット カード、デビット カード、または銀行口座引き落としで支払われた[別のサブスクリプションを購入](../try-or-buy-microsoft-365.md#buy-a-different-subscription)し、[すべてのユーザーを新しいサブスクリプションに移動](../subscriptions/move-users-different-subscription.md)してから、[以前のサブスクリプションをキャンセル](../subscriptions/cancel-your-subscription.md)する必要があります。

## <a name="related-content"></a>関連コンテンツ

[支払方法を管理する](manage-payment-methods.md) (article)\
[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)\
[課金内容または請求書の内容を理解する](understand-your-invoice2.md) (article)\
