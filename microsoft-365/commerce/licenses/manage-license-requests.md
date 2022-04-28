---
title: ライセンス要求を管理する
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- MACBillingLicensesRequests
- AdminSurgePortfolio
search.appverid: MET150
description: ビジネス サブスクリプションのMicrosoft 365に対するユーザーからのライセンス要求を確認および承認または拒否する方法について説明します。
ms.date: 04/22/2022
ms.openlocfilehash: 802b84445c83c2831e5fd88598cc00fb8b0ab867
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098694"
---
# <a name="manage-license-requests"></a>ライセンス要求を管理する

> [!NOTE]
> この記事の情報は、セルフサービスで購入された製品にのみ適用されます。 詳細については、「 [セルフサービス購入に関する FAQ](../subscriptions/self-service-purchase-faq.yml)」を参照してください。

組織内でセルフサービス購入を無効にした場合は、ライセンス要求を使用して、ユーザーのライセンス要求プロセスを管理できます。 ユーザーがブロックした製品のセルフサービス購入を行おうとすると、管理者であるユーザーにライセンスの要求を送信できます。要求を行うときは、製品のライセンスも必要な他のユーザーの名前を追加できます。

> [!NOTE]
> ユーザーがセルフサービス購入を行うのをブロックした場合、Microsoft はマーケティングメールを送信しません。 また、試用版の製品を使用している場合、製品の購入を求めるメッセージは表示されません。 詳細については、「 [セルフサービス購入の管理 (管理者)](../subscriptions/manage-self-service-purchases-admins.md)」を参照してください。

管理者は、ライセンス要求を表示および管理するために、[ライセンス] ページ **の [要求** ] タブ **を** 使用します。 一覧には、要求された製品の名前、ライセンスを要求するユーザーの名前、要求された日付、要求の状態が表示されます。 管理者は、一覧をフィルター処理して、保留中または完了している要求を表示できます。 要求は 30 日間保持されます。

## <a name="before-you-begin"></a>開始する前に

この記事のタスクを実行するには、グローバル管理者である必要があります。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="use-your-own-request-process"></a>独自の要求プロセスを使用する

組織に独自の要求プロセスがある場合は、代わりにそれを使用できます。 ユーザーがライセンスを要求したときに表示されるメッセージを作成します。

> [!IMPORTANT]
> 独自の要求プロセスを使用する場合、[要求] タブには **要求** は表示されません。メッセージを追加する前の既存の要求は、承認または拒否するまで引き続き表示されます。

1. 管理センターで <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  ページに移動し、[**要求**] タブを選択します。
2. **代わりに [既存の要求プロセスを使用** する] を選択します。
3. 右側のウィンドウの [ **メッセージ** ] ボックスに、ユーザーがライセンスを要求したときに表示するメッセージを入力します。 組織ポリシーまたはその他のドキュメントへのリンクも含める場合は、ドキュメントへの **リンク (省略可能)** テキスト ボックスに URL を入力します。
4. **[保存]** を選択します。

**要求** の一覧に戻ると、**独自のライセンス要求プロセスを使用している** というメッセージが表示されます。 ユーザーに送信されるメッセージを変更するには、 **代わりに [既存の要求プロセスを使用** する] を選択します。

## <a name="stop-using-your-own-request-process"></a>独自の要求プロセスの使用を停止する

1. 管理センターで <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  ページに移動し、[**要求**] タブを選択します。
2. **代わりに [既存の要求プロセスを使用** する] を選択します。
3. 右側のウィンドウで、[組織の **要求プロセスを使用** する] チェック ボックスをオフにします。
4. **[保存]** を選択します。

## <a name="approve-or-deny-a-license-request"></a>ライセンス要求を承認または拒否する

1. 管理センターで <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  ページに移動し、[**要求**] タブを選択します。
2. 確認する要求を含む行を選択します。 右側のウィンドウには、製品に対するライセンスを必要とするユーザーの詳細が表示されます。
3. 要求全体を拒否するには、[ **承認しない**] を選択し、ダイアログ ボックスで [ **承認しない**] を選択します。
4. 要求の一部のユーザーを拒否し、他のユーザーを承認するには、削除するユーザーの名前で X を選択します。 それらの名前は[ **これらのユーザーに割り当てないでください] の下に** 移動されます。
5. 複数の製品がある場合は、[製品の **選択]** で、ライセンスの割り当てに使用する製品を選択します。
6. ユーザーが特定のアプリやサービスへのアクセスを拒否するには、[ **アプリとサービスを有効または無効にする**] を展開し、除外するアプリとサービスのチェック ボックスをオフにします。
7. ウィンドウの下部にあるテキスト ボックスにオプションのメッセージを入力します。
8. 完了したら、[承認] を選択 **します**。 右側のウィンドウには、要求の詳細が表示されます。
9. 右側のウィンドウを閉じます。
    ユーザーは、要求が承認または拒否されたことを示す電子メールを受け取ります。

## <a name="related-content"></a>関連コンテンツ

[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)\
[ユーザーを別のサブスクリプションに移動する](../subscriptions/move-users-different-subscription.md) (記事)\
[サブスクリプション ライセンスを購入または削除する](buy-licenses.md) (記事)
