---
title: 請求通知と請求書の添付ファイルを管理する
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 請求通知メールと請求書添付ファイルを受け取るユーザーを管理する方法について学習します。
ms.date: 03/17/2021
ms.openlocfilehash: 11fecb1f5f33810c2bef2425fda845981c2c3193
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321573"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>請求通知と請求書の添付ファイルを管理する

[ **課金通知]** ページでは、組織の請求通知メールを受け取るユーザーを管理できます。 このページには、組織の請求書をメールの添付ファイルとして受け [取るオプションも用意されています](#receive-your-organizations-invoices-as-email-attachments)。

## <a name="before-you-begin"></a>始める前に

この記事で説明する手順を実行するには、グローバル管理者である必要があります。 課金管理者は、以下のセクションで説明されている通り、これらの変更の一部を行えます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="change-the-language-you-receive-email-in"></a>メールを受信する言語を変更する

請求通知メールは、組織の優先言語で送信されます。 優先する言語を変更するには、次の手順を使用します。

1. [メッセージ] Microsoft 365 管理センター、[**BillingBilling** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">通知] ページに移動</a>します。
2. [課金通知 **の設定] セクションで** 、[通知設定の **編集] を選択します**。
3. [課金通知 **の設定] ウィンドウ** の [優先 **言語] で** 、使用する言語を選択し、[保存] を選択 **します**。

## <a name="change-who-receives-billing-notifications"></a>請求通知を受け取るユーザーを変更する

組織の請求通知は、すべてのグローバル管理者および課金管理者のプライマリおよび代替メール アドレスに送信されます。グローバル管理者ロールまたは課金管理者ロールを持つユーザーを変更するには、次の手順を使用します。

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>[課金通知] ページを使用して管理者ロールを割り当てる

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [請求 **通知を受け取る** 管理者] セクションで、説明テキストの [ **課金管理者** ] または **[グローバル** 管理者] リンクを選択します。
3. 右側のウィンドウの [割り当てられた管理者 **] タブ** で、[追加] を **選択します**。
4. [管理者 **の追加]** ウィンドウで、ユーザーの表示名またはユーザー名を入力し、候補の一覧からユーザーを選択します。
5. 完了するまで、複数のユーザーを追加します。
6. **[保存]** を選択します。 ユーザーが割り当てられた管理者の一覧に追加されます。

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>[課金通知] ページを使用して管理者の役割を削除する

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [請求 **通知を受け取る** 管理者] セクションで、説明テキストの [ **課金管理者** ] または **[グローバル** 管理者] リンクを選択します。
3. 右側のウィンドウの [割り **当てられた管理者** ] タブで、役割から削除するユーザーを選択し、[削除] を選択 **します**。
4. 確認ボックスで、[削除] を **選択します**。 割り当てられた管理者の一覧からユーザーが削除されます。

## <a name="change-the-email-addresses-for-admins"></a>管理者のメール アドレスを変更する

組織内の他の管理者のプライマリメール アドレスと代替メール アドレスを変更するには、次の手順を使用します。

> [!NOTE]
> 課金管理者は、自分のプライマリメール アドレスと代替メール アドレスを変更できますが、他の管理者は変更できません。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [請求 **通知を受け取る管理者] セクションで** 、名前を選択します。
3. 右側のウィンドウで、必要に応じてプライマリメール アドレスと代替メール アドレスを追加または更新し、[保存] を選択 **します**。

## <a name="change-your-organizations-contact-email"></a>組織の連絡先メールを変更する

グローバル管理者と課金管理者に加えて、請求通知は組織の連絡先メール アドレスに送信されます。 電子メール アドレスを変更するには、次の手順を使用します。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [請求 **通知を受け取る組織の連絡先] で**、組織の連絡先を選択します。
3. 右側のウィンドウで、使用するメール アドレスを入力し、[保存] を選択 **します**。

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>組織の請求書をメール添付ファイルとして受け取る

> [!NOTE]
> 課金管理者は、このセクションの手順も実行できます。

新しい請求書の準備ができたら、組織の請求書のコピーを PDF ファイルとして請求書通知メールに添付できます。 次の手順を使用して、添付ファイルとして請求書を受信します。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [課金 **通知の設定] で、[** 通知設定 **の編集] を選択します**。
3. [請求 **通知の設定] ウィンドウ** の **[請求書** メールに PDF を添付する] で、チェック ボックスをオンにして、[保存] を選択 **します**。

請求書の添付ファイルの受信をいつでも停止するには、上記の手順に従い、手順 3 の [請求書メールに **PDF** を添付する] チェック ボックスをオフにします。

## <a name="what-if-i-have-a-billing-profile"></a>請求プロファイルがある場合は、

課金プロファイルがある場合、この記事で説明する手順の一部は、一部のサブスクリプションで若干異なる場合があります。 このセクションでは、これらの違いについて説明します。 [請求プロファイルを持っているかどうかは、どのように確認できますか?](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>Who請求通知を受け取る場合

請求通知メールは、次のいずれかの役割が割り当てられているユーザーのプライマリおよび代替メール アドレスに送信されます。

- 課金プロファイルの所有者
- 課金プロファイル投稿者
- 請求書マネージャー

課金プロファイル の役割と管理方法の詳細については、「Azure での Microsoft Customer Agreement の管理役割について [」を参照してください](/azure/cost-management-billing/manage/understand-mca-roles)。

組織の請求通知を受け取るユーザーを変更するには、次の手順を使用して、ユーザーに割り当てられた役割を変更します。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求と支払い]</a> ページの順に移動します。
2. [課金プロファイル **] タブ** で、請求プロファイルを選択します。
3. [課金プロファイル **の役割] セクション** で、課金プロファイルの所有者、請求プロファイル投稿者、または請求書マネージャーの役割を割り当てるか **、削除します**。

### <a name="receive-invoices-as-email-attachments"></a>電子メールの添付ファイルとして請求書を受け取る

請求書通知の添付ファイルとして請求書を受け取る場合は、次の手順を使用して、特定の請求プロファイルに対してこの設定を有効にします。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求と支払い]</a> ページの順に移動します。
2. [課金プロファイル **] タブを選択** し、一覧から請求プロファイルを選択します。
3. [請求プロファイルの詳細] ページの **[電子メール** の添付ファイルで請求書を取得する] で、トグルを [オン] に切り替 **えます**。

## <a name="related-content"></a>関連コンテンツ

[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)\
[メキシコ](mexico-billing-info.md) で Microsoft 365 for businessの課金情報 (記事) \
[ビジネス向け請求書または請求書Microsoft 365を](understand-your-invoice2.md)理解する (記事)\
[ユーザーを追加し、同時にライセンスを割り当てる](../../admin/add-users/add-users.md) (記事)
