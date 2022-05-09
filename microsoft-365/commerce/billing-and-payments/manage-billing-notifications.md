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
description: 課金通知メールと請求書の添付ファイルを受け取るユーザーを管理する方法について説明します。
ms.date: 03/17/2021
ms.openlocfilehash: 11fecb1f5f33810c2bef2425fda845981c2c3193
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321573"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>請求通知と請求書の添付ファイルを管理する

**[課金通知]** ページでは、組織の課金通知メールを受け取るユーザーを管理できます。 このページには、 [組織の請求書を電子メールの添付ファイルとして受け取る](#receive-your-organizations-invoices-as-email-attachments)オプションも用意されています。

## <a name="before-you-begin"></a>開始する前に

この記事で説明されている手順を実行するには、グローバル管理者である必要があります。 課金管理者は、以下のセクションで説明するように、これらの変更の一部を行うことができます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="change-the-language-you-receive-email-in"></a>電子メールで受信する言語を変更する

課金通知メールは、組織の優先言語で送信されます。 優先言語を変更するには、次の手順に従います。

1. Microsoft 365 管理センターで、<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">BillingBilling</a>  >  通知ページに移動します。
2. [ **課金通知の設定]** セクションで、[ **通知設定の編集]** を選択します。
3. **[課金通知の設定**] ウィンドウの [**優先言語**] で、使用する言語を選択し、[**保存**] を選択します。

## <a name="change-who-receives-billing-notifications"></a>課金通知を受け取るユーザーを変更する

組織の課金通知は、すべてのグローバル管理者と課金管理者のプライマリメール アドレスと代替メール アドレスに送信されます。グローバル管理者ロールまたは課金管理者ロールを持つユーザーを変更するには、次の手順に従います。

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>[課金通知] ページを使用して管理者ロールを割り当てる

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [**課金通知を受け取る管理者]** セクションで、説明テキストの **[課金管理者**] または **[グローバル管理者**] リンクを選択します。
3. 右側のウィンドウの [ **割り当てられた管理者** ] タブで、[ **追加**] を選択します。
4. [ **管理者の追加]** ウィンドウで、ユーザーの表示名またはユーザー名を入力し、候補の一覧からユーザーを選択します。
5. 完了するまで、複数のユーザーを追加します。
6. **[保存]** を選択します。 ユーザーが割り当てられた管理者の一覧に追加されます。

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>[課金通知] ページを使用して管理者ロールを削除する

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [**課金通知を受け取る管理者]** セクションで、説明テキストの **[課金管理者**] または **[グローバル管理者**] リンクを選択します。
3. 右側のウィンドウの [ **割り当てられた管理者** ] タブで、ロールから削除するユーザーを選択し、[削除] を選択 **します**。
4. 確認ボックスで、[削除] を選択 **します**。 ユーザーは、割り当てられた管理者の一覧から削除されます。

## <a name="change-the-email-addresses-for-admins"></a>管理者のメール アドレスを変更する

組織内の他の管理者のプライマリメール アドレスと代替メール アドレスを変更するには、次の手順に従います。

> [!NOTE]
> 課金管理者は、独自のプライマリと代替の電子メール アドレスを変更できますが、他の管理者には変更できません。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. [ **管理者が課金通知を受け取る** ] セクションで、名前を選択します。
3. 右側のウィンドウで、必要に応じてプライマリと代替の電子メール アドレスを追加または更新し、[保存] を選択 **します**。

## <a name="change-your-organizations-contact-email"></a>組織の連絡先メールを変更する

グローバル管理者と課金管理者に加えて、組織の連絡先の電子メール アドレスに課金通知が送信されます。 電子メール アドレスを変更するには、次の手順に従います。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. **[課金通知を受け取る組織の連絡先**] で、組織の連絡先を選択します。
3. 右側のウィンドウで、使用するメール アドレスを入力し、[保存] を選択 **します**。

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>組織の請求書を電子メールの添付ファイルとして受け取る

> [!NOTE]
> 課金管理者は、このセクションの手順を実行することもできます。

新しい請求書の準備ができたら、組織の請求書のコピーを PDF ファイルとして添付して、請求書通知メールに添付することができます。 添付ファイルとして請求書を受け取るには、次の手順に従います。

1. 管理センターで、**[課金情報]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">[課金に関する通知]</a> ページに移動します。
2. **[課金通知の設定]** で、[**通知設定の編集]** を選択します。
3. **[課金通知の設定**] ウィンドウの [**請求書のメールに PDF を添付** する] で、チェック ボックスをオンにし、[保存] を選択 **します**。

請求書の添付ファイルの受信をいつでも停止するには、上記の手順に従って、手順 3 の **[請求書のメールに PDF を添付する** ] チェック ボックスをオフにします。

## <a name="what-if-i-have-a-billing-profile"></a>課金プロファイルがある場合はどうなりますか?

課金プロファイルがある場合、この記事で説明されている手順の一部は、一部のサブスクリプションで若干異なる場合があります。 このセクションでは、これらの違いについて説明します。 [課金プロファイルがあるかどうか操作方法わかりますか?](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>Who請求通知を受信しますか?

課金通知メールは、次のいずれかのロールが割り当てられているユーザーのプライマリと代替の電子メール アドレスに送信されます。

- 課金プロファイルの所有者
- 課金プロファイル共同作成者
- 請求書マネージャー

課金プロファイル ロールとその管理方法の詳細については、「[Azure での管理ロールMicrosoft 顧客契約理解](/azure/cost-management-billing/manage/understand-mca-roles)する」を参照してください。

組織の課金通知を受け取るユーザーを変更するには、次の手順に従って、ユーザーに割り当てられているロールを変更します。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求と支払い]</a> ページの順に移動します。
2. [ **課金プロファイル** ] タブで、課金プロファイルを選択します。
3. [**課金プロファイルロール**] セクションで、**課金プロファイル所有者、課金プロファイル****共同作成者**、または **請求書マネージャー** のロールを割り当てるか削除します。

### <a name="receive-invoices-as-email-attachments"></a>請求書を電子メールの添付ファイルとして受け取る

請求書通知の添付ファイルとして請求書を受信するには、次の手順に従って、特定の課金プロファイルに対してこの設定を有効にします。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求と支払い]</a> ページの順に移動します。
2. [ **課金プロファイル** ] タブを選択し、一覧から課金プロファイルを選択します。
3. [課金プロファイルの詳細] ページ **の [電子メール添付ファイルで請求書を取得** する] で、トグルを **[オン]** に切り替えます。

## <a name="related-content"></a>関連コンテンツ

[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)\
[メキシコ](mexico-billing-info.md) で Microsoft 365 for businessの課金情報 (記事) \
[Microsoft 365 for Business の請求書または請求明細書を理解する](understand-your-invoice2.md) (記事)\
[ユーザーを追加し、同時にライセンスを割り当てる](../../admin/add-users/add-users.md) (記事)
