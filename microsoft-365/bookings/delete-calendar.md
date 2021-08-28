---
title: 予約カレンダーを削除する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: '[予約] Microsoft 365 管理センターまたはWindows PowerShellを使用して、予約カレンダーを削除します。'
ms.openlocfilehash: fc5975e25fa3b1f2d2aab991cc7aac8038181f3f
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572757"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings で予約カレンダーを削除する

この記事では、不要な予約カレンダーを削除する方法について説明します。 予約カレンダーを削除するには、Microsoft 365 管理センター PowerShell を使用します。 Bookings 予定表は、予約Exchange Online削除するために、対応するユーザー アカウントを削除するメールボックスです。

> [!IMPORTANT]
> 2017 以前に作成した予約カレンダーはすべて、このトピックの PowerShell の手順を使用して削除する必要があります。 2018 以降で作成された予約カレンダーはすべて、このページでMicrosoft 365 管理センター。

予約カレンダーには、その予約カレンダーとデータに関するすべての関連情報が保存されます。以下を含む。

- 予約カレンダーの作成時に追加されたビジネス情報、ロゴ、および勤務時間
- 予約カレンダーの作成時に追加された関連するスタッフとサービス
- 作成後に予約カレンダーに追加されたすべての予約と休み予定。

> [!WARNING]
> 予約カレンダーが削除された後、この追加情報も完全に削除され、回復できません。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>アカウントで予約カレンダーを削除Microsoft 365 管理センター

1. Microsoft 365 管理センターに移動します。

1. 管理センターで、[ **ユーザー** ] を選択します。

   ![[ユーザーの UI のイメージ] Microsoft 365 管理センター。](../media/bookings-admin-center-users.png)

1. [ **アクティブ ユーザー**] ページで、削除するユーザー名を選択して、[ **ユーザーの削除**] を選択します。

   ![[ユーザー UI の削除] Microsoft 365 管理センター。](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>PowerShell を使用して予約カレンダー Exchange Onlineする

PowerShell Connect接続Exchange Onlineの前提条件とガイダンスについては[、「PowerShell](/powershell/exchange/exchange-online-powershell-v2)を使用する方法Exchange Online参照してください。

これらの手順を実行するには、[管理者として実行] オプションを選択して実行したアクティブな Microsoft PowerShell コマンド ウィンドウを使用している必要があります。

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

3. メッセージが表示されたら、完全に削除する予約カレンダーをホストする Microsoft 365 テナントにテナント管理者の資格情報でログオンします。

4. このコマンドの処理が終わったら、次のコマンドを入力して、テナントの予約メールボックスの一覧を取得します。

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. 次のコマンドを入力します。

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 完全に削除する予約メールボックス エイリアスの正確な名前を入力してください。

6. 予定表が削除されたと確認するには、次のコマンドを入力します。

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   削除された予定表は出力に表示されません。
