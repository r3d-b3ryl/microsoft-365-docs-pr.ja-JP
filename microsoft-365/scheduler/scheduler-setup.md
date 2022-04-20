---
title: Microsoft 365用の Scheduler を設定します。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Microsoft 365用の Scheduler を設定します。
ms.openlocfilehash: ef377393134e4d8028ab0e6e40ddcc3647f60695
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953850"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Scheduler for Microsoft 365 を設定する

テナント管理者は、スケジューラ アシスタント メールボックスを設定し、会議開催者の Scheduler ライセンスを取得して、Microsoft 365 サービスの Scheduler を有効にする必要があります。 

## <a name="licensing"></a>ライセンス

詳細情報: [Microsoft 365 ライセンス用スケジューラ](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)

> [!NOTE]
> 会議の出席者には、スケジューラまたはMicrosoft 365ライセンスは必要ありません。
>
> Scheduler アシスタント メールボックスには、Microsoft 365または Scheduler ライセンスは必要ありません。

## <a name="prerequisites"></a>前提条件

|前提条件|説明|
|---|---|
|テナントのスケジューラ アシスタント メールボックス |Cortanaとの間で電子メールを送受信するテナントのスケジューラ アシスタント メールボックスとして機能する、Exchange機器の種類のリソース メールボックス。 Cortanaに送信されたすべてのメールは、アイテム保持ポリシーに基づいてテナントのCortanaメールボックスに保持されます。 スケジューラ アシスタント メールボックスは通常、"Cortana" または "Cortana Scheduler" という名前になります。これは、アシスタントからのすべての電子メールがCortana署名されるためです。 <ul><li>リソース メールボックスExchange機器の種類を作成する</li><li>メールボックスの表示名とプライマリ SMTP アドレス`Cortana <cortana@yourdomain.com>`に名前を付けるか、 .`Cortana Scheduler <cortana.scheduler@yourdomain.com>`</li></ul> <br/> **メモ：** Scheduler アシスタント メールボックスには、Microsoft 365または Scheduler ライセンスは必要ありません。|
|Exchange Online メールボックス |会議の開催者は、通常、Microsoft 365 ライセンスの一部としてExchange Onlineメールボックスと予定表を持っている必要があります。 さらに、会議の開催者には Scheduler ライセンスが必要です。 Scheduler ライセンスを使用すると、スケジューラ アシスタントは会議の開催者のメールボックスと予定表を使用して会議をスケジュールできます。 <br/><br/> ライセンスと価格に関する情報については、Microsoft 365のスケジューラに関するページを参照してください。 <br/><br/> **メモ：** 会議の出席者には、スケジューラまたはMicrosoft 365ライセンスは必要ありません。 会議の出席者は、テナントの内部または外部にすることができます。 会議出席者は、電子メール アドレスへのアクセスのみを必要とします。|

## <a name="setting-up-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスを設定する

スケジューラ アシスタント メールボックスは、追加のMicrosoft 365または Scheduler ライセンスを必要としないExchange機器の種類のメールボックスです。 スケジューラ アシスタントからのメールはすべてCortana署名されるため、メールボックスの表示名とプライマリ SMTP アドレスにはCortanaが含まれている必要があります (つまり)。 `Cortana <cortana@yourdomain.com>` `Cortana Scheduler <cortana.scheduler@yourdomain.com>` スケジューラ アシスタント メールボックスが作成されたら、そのメールボックスをスケジューラ アシスタント メールボックスとして指定する必要があります。 Scheduler アシスタント メールボックスを指定すると、ユーザーに代わって会議をスケジュールできるCortanaが表示されます。

- Microsoft 365 管理センターを使用して、ユーザー メールボックスを作成します。 30 日間のアイテム保持ポリシーをお勧めします。 
- メールボックスのプライマリ SMTP アドレスにCortana名前を使用します。 `Cortana@yourdomain.com`などの名前をお`CortanaScheduler@contoso.com``Cortana.Scheduler@yourdomain.com`勧めします。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>スケジューラ アシスタントとしてメールボックスを指定する

Cortana Scheduler の一意のメールボックスが作成されたら、正式にMicrosoft 365するメールボックスを指定する必要があります。 Cortana Scheduler メールボックスを指定すると、ユーザーに代わって会議をスケジュールできます。

### <a name="connect-to-powershell"></a>PowerShell へのConnect

Microsoft 365 管理センターを使用して、ユーザー メールボックスを作成します。 30 日間のアイテム保持ポリシーをお勧めします。
メールボックスのプライマリ SMTP アドレスにCortana名前を使用します。 `Cortana@yourdomain.com`などの名前をお`CortanaScheduler@contoso.com``Cortana.Scheduler@yourdomain.com`勧めします。

```PowerShell
$domain="yourdomain.com"
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin
```

### <a name="create-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスを作成する

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 
```

### <a name="designate-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスを指定する

```PowerShell
Set-mailbox cortana@$domain -SchedulerAssistant:$true
```

Cortana Scheduler アシスタント メールボックスでこの "set" コマンドを実行した後、メールボックスに新しい "PersistedCapability" が設定され、このメールボックスが "SchedulerAssistant" であることに注意してください。

> [!NOTE]
> 組織を PowerShell に接続する方法については、「PowerShell で[Microsoft 365するConnect](/microsoft-365/enterprise/connect-to-microsoft-365-powershell)」を参照してください。

### <a name="verifying-the-scheduler-assistant-mailbox"></a>Scheduler アシスタント メールボックスの確認

Scheduler アシスタント メールボックスが作成されたことを確認するには

```PowerShell
Get-CalendarProcessing cortana@$domain | fl DeleteNonCalendarItems
```

結果は "false" である必要があります。

```PowerShell
Get-Mailbox -Identity cortana@$domain | fl *type*
```

結果は次のようになります。

- ResourceType: Equipment
- Remote RecipientType: None
- RecipientType: UserMailbox
- RecipientTypeDetails: EquipmentMailbox

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスであるメールボックスを検出するには

```PowerShell
Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> SchedulerAssistant 機能を設定するには、Scheduler アシスタント メールボックスが完全なプロビジョニングを完了するまでに数時間かかる場合があります。

## <a name="exchange-online-mailbox"></a>Exchange Online メールボックス

スケジューラ ライセンスは、会議の開催者が自分のスケジューラ アシスタントに会議のスケジュール タスクを委任できる、Microsoft 365のアドオンです。 会議の開催者は、スケジューラ アシスタント メールボックスとしてメールボックスを指定するだけでなく、スケジューラ のライセンスとExchange Onlineメールボックスと予定表 (通常は Scheduler が機能するためのMicrosoft 365 ライセンス) も必要になります。 会議出席者には、Scheduler ライセンスやMicrosoft 365 ライセンスは必要ありません。

Scheduler アドオンを購入するには、次のいずれかのライセンスが必要です。

- Microsoft 365 E3、A3、E5、A5
- Business Basic、Business、Business Standard、Business プレミアム
- Office 365 E1、A1、E3、A3、E5、A5
- Business Essentials、Business プレミアム
- プラン 1 またはプラン 2 のライセンスをExchange Onlineします。

> [!NOTE]
> Microsoft 365用スケジューラは、英語でのみ世界中のマルチテナント環境で使用できます。 **次のユーザーは、Microsoft 365用スケジューラ** を使用できません。
>
> - Microsoft 365中国の 21Vianet によって運用されている
> - データ トラスティ German Telekom を使用するドイツのクラウドを使用するMicrosoft 365
> - GCC、コンシューマー、GCC High、DoD などの政府機関向けクラウド
>
> Scheduler は、データの場所がドイツのデータセンターではないドイツのユーザーをサポートします。
