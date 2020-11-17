---
title: 予約予定表を削除する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 予約予定表を削除するには、Microsoft 365 管理センターまたは Windows PowerShell を使用します。
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126651"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>予約された予定表を削除する

この記事では、不要な予約予定表を削除する方法について説明します。 Microsoft 365 管理センターで予約予定表を削除するか、PowerShell を使用することができます。 予約予定表は、Exchange Online のメールボックスで、予約予定表を削除するために対応するユーザーアカウントを削除します。

> [!IMPORTANT]
> 2017またはそれ以前に作成したすべての予約予定表は、このトピックの PowerShell の手順を使用して削除する必要があります。 2018またはそれ以降に作成されたすべての予約予定表は、Microsoft 365 管理センターで削除できます。

予約予定表は、予約された予定表とデータに関するすべての関連情報を格納する場所です。

- 予約予定表を作成したときに追加された勤務先情報、ロゴ、および稼働時間
- 予約予定表の作成時に追加された関連スタッフとサービス
- 予約された予定表に追加された予約および期間のすべての予定を予約します。

> [!WARNING]
> 予約予定表を削除すると、この追加情報も完全に削除され、回復できなくなります。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで予約予定表を削除する

1. Microsoft 365 管理センターに移動します。

1. 管理センターで、[ **ユーザー** ] を選択します。

   ![Microsoft 365 管理センターのユーザー UI の画像](../media/bookings-admin-center-users.png)

1. [ **アクティブ ユーザー**] ページで、削除するユーザー名を選択して、[ **ユーザーの削除**] を選択します。

   ![Microsoft 365 管理センターでのユーザーの削除 UI の画像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Exchange Online の PowerShell を使用して予約予定表を削除する

Exchange Online PowerShell への接続に関する前提条件とガイダンスについては、「 [Exchange Online powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 」を参照してください。

これらの手順を実行するには、[管理者として実行] オプションを選択して実行したアクティブな Microsoft PowerShell コマンドウィンドウを使用する必要があります。

1. 次のコマンドを入力します。

   ```PowerShell
    $user = get-credential
   ```

1. メッセージが表示されたら、完全に削除する予約予定表をホストする Microsoft 365 テナントに、テナント管理者の資格情報を使用してログオンします。

1. PowerShell コマンドプロンプトで、次のコマンドを入力します。

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. 次のコマンドを入力します。

   ```PowerShell
    Import-PSSession $s
   ```

1. このコマンドの処理が終わったら、次のコマンドを入力して、テナントの予約メールボックスの一覧を取得します。

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. 次のコマンドを入力します。

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 完全に削除する予約メールボックスのエイリアスの正確な名前を入力するように注意してください。

1. 予定表が削除されたことを確認するには、次のコマンドを入力します。

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   削除された予定表は出力に表示されません。
