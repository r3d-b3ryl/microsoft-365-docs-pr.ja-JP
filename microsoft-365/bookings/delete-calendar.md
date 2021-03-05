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
description: Microsoft 365 管理センターまたは管理者Windows PowerShellを使用して、予約カレンダーを削除します。
ms.openlocfilehash: 1f8df15eafac7867f7ae852e344e1c5730362598
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454207"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings で予約カレンダーを削除する

この記事では、不要な予約カレンダーを削除する方法について説明します。 予約カレンダーは、Microsoft 365 管理センターで削除するか、PowerShell を使用できます。 予約カレンダーは Exchange Online のメールボックスなので、対応するユーザー アカウントを削除して予約予定表を削除します。

> [!IMPORTANT]
> 2017 以前に作成した予約カレンダーはすべて、このトピックの PowerShell の手順を使用して削除する必要があります。 2018 以降で作成された予約カレンダーはすべて、Microsoft 365 管理センターで削除できます。

予約カレンダーには、その予約カレンダーとデータに関するすべての関連情報が保存されます。以下を含む。

- 予約カレンダーの作成時に追加されたビジネス情報、ロゴ、および勤務時間
- 予約カレンダーの作成時に追加された関連するスタッフとサービス
- 作成後に予約カレンダーに追加されたすべての予約と休み予定。

> [!WARNING]
> 予約カレンダーが削除された後、この追加情報も完全に削除され、回復できません。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで予約カレンダーを削除する

1. Microsoft 365 管理センターに移動します。

1. 管理センターで、[ **ユーザー** ] を選択します。

   ![Microsoft 365 管理センターのユーザー UI のイメージ](../media/bookings-admin-center-users.png)

1. [ **アクティブ ユーザー**] ページで、削除するユーザー名を選択して、[ **ユーザーの削除**] を選択します。

   ![Microsoft 365 管理センターでのユーザー UI の削除のイメージ](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Exchange Online PowerShell を使用して予約カレンダーを削除する

Exchange Online [PowerShell に接続するための](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 前提条件とガイダンスについては、「Connect to Exchange Online PowerShell」を参照してください。

これらの手順を実行するには、[管理者として実行] オプションを選択して実行したアクティブな Microsoft PowerShell コマンド ウィンドウを使用している必要があります。

1. PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > すでに、[EXO V2 モジュールをインストール](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)している場合は、前のコマンドは表示のとおり機能します。
   
2. 実行する必要があるコマンドでは、次の構文を使用します。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ は、ユーザー プリンシパル名の形式 (`john@contoso.com`など) のアカウントです。

3. メッセージが表示されたら、完全に削除する予約予定表をホストする Microsoft 365 テナントにテナント管理者資格情報を使用してログオンします。

4. このコマンドの処理が終わったら、次のコマンドを入力して、テナントの予約メールボックスの一覧を取得します。

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. 次のコマンドを入力します。

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 完全に削除する予約メールボックス エイリアスの正確な名前を入力してください。

6. 予定表が削除されたと確認するには、次のコマンドを入力します。

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

   削除された予定表は出力に表示されません。
