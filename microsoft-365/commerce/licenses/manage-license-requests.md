---
title: ライセンス要求の管理
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: micurn, nicholak
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
description: ビジネス サブスクリプションのユーザーからのライセンス要求を確認および承認またはMicrosoft 365する方法について学習します。
ms.date: 06/07/2021
ms.openlocfilehash: 7932383afe109e707a5c35914e50c665d0bf1885
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321475"
---
# <a name="manage-license-requests"></a>ライセンス要求の管理

> [!NOTE]
> この記事の情報は、セルフサービス購入製品にのみ適用されます。 詳細については、「セルフサービス購入 [に関するよく寄せられる質問」を参照してください](../subscriptions/self-service-purchase-faq.yml)。

組織内でセルフサービス購入を無効にした場合は、ライセンス要求を使用してユーザーのライセンス要求プロセスを管理できます。 ユーザーがブロックした製品のセルフサービス購入を試みる場合は、管理者からライセンスの要求を送信できます。要求を行う場合は、製品のライセンスも必要とする他のユーザーの名前を追加できます。

> [!NOTE]
> ユーザーによるセルフサービスの購入をブロックした場合、Microsoft はマーケティングメールを送信しません。 また、製品の試用版を使用している場合、製品の購入を求めるメッセージは表示されます。 詳細については、「セルフサービス購入 [の管理 (Admin)」を参照してください](../subscriptions/manage-self-service-purchases-admins.md)。

ライセンス要求を表示および管理するために、管理者は [ライセンス] ページの [要求] タブ **を使用** します。 一覧には、要求された製品の名前、ライセンスを要求するユーザーの名前、要求された日付、要求の状態が表示されます。 管理者はリストをフィルター処理して、保留中または完了した要求を表示できます。 要求は 30 日間保持されます。

## <a name="before-you-begin"></a>始める前に

この記事のタスクを実行するには、グローバル管理者である必要があります。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="use-your-own-request-process"></a>独自の要求プロセスを使用する

組織に独自の要求プロセスがある場合は、代わりにそれを使用できます。 ユーザーがライセンスを要求するときに表示されるメッセージを作成します。

> [!IMPORTANT]
> 独自の要求プロセスを使用する場合は、[要求] タブに要求 **は表示** されません。メッセージを追加する前の既存の要求は、メッセージを承認または拒否するまで引き続き表示されます。

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a> > ] ページに移動し、[要求] **タブを選択** します。
2. [既存 **の要求プロセスを使用する] を選択します**。
3. 右側のウィンドウの [メッセージ] **ボックスに、** ユーザーがライセンスを要求するときに表示するメッセージを入力します。 組織ポリシーや他のドキュメントへのリンクも含める場合は、[ドキュメントへのリンク] **(オプション)** テキスト ボックスに URL を入力します。
4. **[保存]** を選択します。

[要求] ボックスの **一覧に戻** り、独自のライセンス要求プロセスを使用しているというメッセージ **が表示されます**。 ユーザーに送信されるメッセージに変更を加える場合は、[既存の要求プロセスを使用 **する] を選択します**。

## <a name="stop-using-your-own-request-process"></a>独自の要求プロセスの使用を停止する

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a> > ] ページに移動し、[要求] **タブを選択** します。
2. [既存 **の要求プロセスを使用する] を選択します**。
3. 右側のウィンドウで、[組織の要求プロセスを使用する **] チェック ボックス** をオフにします。
4. **[保存]** を選択します。

## <a name="approve-or-deny-a-license-request"></a>ライセンス要求を承認または拒否する

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a> > ] ページに移動し、[要求] **タブを選択** します。
2. 確認する要求を含む行を選択します。 右側のウィンドウには、製品のライセンスを必要とするユーザーの詳細が表示されます。
3. 要求全体を拒否するには、[承認しない] **を選択** し、ダイアログ ボックスで [承認しない **] を選択します**。
4. 要求に対して一部のユーザーを拒否し、他のユーザーを承認するには、削除するユーザーの名前で X を選択します。 [これらのユーザーに割り当てない] **の下に名前が移動されます**。
5. 複数の製品がある場合は、[製品の選択] で、ライセンスの割り当てに使用する製品を選択します。
6. ユーザーが特定のアプリやサービスへのアクセスを拒否するには、[アプリとサービスを有効またはオフにする] を展開し、除外するアプリのチェック ボックスをオフにします。
7. ウィンドウの下部に、テキスト ボックスにオプションのメッセージを入力します。
8. 完了したら、[承認] を **選択します**。 右側のウィンドウには、要求の詳細が表示されます。
9. 右側のウィンドウを閉じます。
    ユーザーは、要求が承認または拒否されたという電子メールを受信します。

## <a name="related-content"></a>関連コンテンツ

[ユーザーにライセンスを割り当てる](../../admin/manage/assign-licenses-to-users.md) (記事)\
[ユーザーを別のサブスクリプションに移動](../subscriptions/move-users-different-subscription.md) する (記事)\
[サブスクリプション ライセンスを購入または削除する](buy-licenses.md) (記事)
