---
title: 予約カレンダーを削除する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Microsoft 365 管理センターまたはWindows PowerShellを使用して、Bookings カレンダーを削除します。
ms.openlocfilehash: 57ad1ea0e7857a1d7af4f98d196a67f27f743dd0
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037558"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings で予約カレンダーを削除する

この記事では、不要な予約カレンダーを削除する方法について説明します。 Microsoft 365 管理センターで予約カレンダーを削除することも、PowerShell を使用することもできます。 Bookings 予定表はExchange Onlineのメールボックスであるため、対応するユーザー アカウントを削除して予約予定表を削除します。

> [!IMPORTANT]
> 2017 以前に作成したすべての予約予定表は、このトピックの PowerShell の手順を使用して削除する必要があります。 2018 以降に作成されたすべての予約予定表は、Microsoft 365 管理センターで削除できます。

予約予定表は、その予約予定表とデータに関するすべての関連情報が格納される場所です。次のものが含まれます。

- 予約予定表の作成時に追加されたビジネス情報、ロゴ、および勤務時間
- 予約カレンダーの作成時に追加された関連スタッフとサービス
- 作成された予約予定表に追加されたすべての予約と休暇の予定。

> [!WARNING]
> 予約予定表が削除されると、この追加情報も完全に削除され、回復できません。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで予約カレンダーを削除する

1. Microsoft 365 管理センターに移動します。

1. 管理センターで、[ **ユーザー** ] を選択します。

   ![Microsoft 365 管理センターのユーザー UI の画像。](../media/bookings-admin-center-users.png)

1. [ **アクティブなユーザー]** ページで、削除する予約予定表の名前を選択し、[ **ユーザーの削除**] を選択します。

   ![Microsoft 365 管理センターのユーザー UI の削除の画像。](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>PowerShell を使用して予約カレンダー Exchange Online削除する

[PowerShell に接続するための](/powershell/exchange/exchange-online-powershell-v2)前提条件とガイダンスについては、「PowerShell への接続Exchange Online Exchange Online参照してください。

これらの手順を実行するには、"管理者として実行" オプションを選択して実行したアクティブな Microsoft PowerShell コマンド ウィンドウを使用する必要があります。

1. PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > すでに、[EXO V2 モジュールをインストール](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)している場合は、前のコマンドは表示のとおり機能します。
   
2. 実行する必要があるコマンドでは、次の構文を使用します。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ は、ユーザー プリンシパル名の形式 (`john@contoso.com`など) のアカウントです。

3. メッセージが表示されたら、完全に削除する予約予定表をホストする Microsoft 365 テナントにテナント管理者の資格情報を使用してログオンします。

4. このコマンドの処理が終わったら、次のコマンドを入力して、テナントの予約メールボックスの一覧を取得します。

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. 次のコマンドを入力します。

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 完全に削除する予約メールボックスエイリアスの正確な名前を入力してください。

6. 予定表が削除されたことを確認するには、次のコマンドを入力します。

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   削除された予定表は出力に表示されません。
