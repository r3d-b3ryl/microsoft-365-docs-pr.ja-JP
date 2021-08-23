---
title: スケジューラの設定 Microsoft 365。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: スケジューラの設定 Microsoft 365。
ms.openlocfilehash: a6d642364abcf4672d59494614daaf2d9e248208
ms.sourcegitcommit: f2381c3bb3351235aaca977c57a46c654b9b0657
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2021
ms.locfileid: "58386938"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Scheduler for Microsoft 365 を設定する

テナント管理者は、スケジューラ アシスタント メールボックスをセットアップし、会議開催者のスケジューラ ライセンスを取得して、スケジューラ for Microsoft 365必要があります。 

## <a name="licensing"></a>ライセンス

詳細:[ライセンスのスケジューラMicrosoft 365する](https://wwww.microsoft.com/microsoft-365/meeting-scheduler-pricing)

>[メモ]会議の出席者は、スケジューラ ライセンスまたは会議出席許可Microsoft 365必要ではありません。 <br>スケジューラ アシスタント メールボックスには、スケジューラ ライセンスまたはスケジューラ Microsoft 365は必要とされません。

## <a name="prerequisites"></a>前提条件

| 前提条件 | 説明 |
|-------------------|-------------|
|テナントのスケジューラ アシスタント メールボックス |テナントExchangeを送受信するスケジューラ アシスタント メールボックスとして機能する、デバイスタイプのリソース メールボックスCortana。 ユーザーに送信Cortanaメールは、保持ポリシーに基づいてCortanaのメールボックスに保持されます。 スケジューラ アシスタント メールボックスは、通常、アシスタントからのすべての電子メールに署名Cortana または "Cortana スケジューラ" という名前が付Cortana。</br> - リソース メールボックスの備品Exchange作成する</br> - メールボックスの表示名とプライマリ SMTP アドレスに "Cortana" または <cortana@yourdomain.com> "Cortana スケジューラ" という名前を付 <cortana.scheduler@yourdomain.com> します。</br>**注:** スケジューラ アシスタント メールボックスには、スケジューラ ライセンスまたはスケジューラ Microsoft 365は必要とされません。|
|Exchange Online メールボックス |会議の開催者は、通常、Exchange Onlineライセンスの一部として、メールボックスと予定表をMicrosoft 365必要があります。 さらに、会議の開催者はスケジューラ ライセンスを持っている必要があります。 スケジューラ ライセンスを使用すると、スケジューラ アシスタントは会議開催者のメールボックスと予定表を使用して会議をスケジュールできます。</br></br> ライセンスと価格情報についてはMicrosoft 365スケジューラを参照してください。  </br></br>**注:** 会議の出席者は、スケジューラ ライセンスまたは会議出席許可Microsoft 365必要ではありません。 会議の出席者は、テナントの内部または外部にできます。 会議の出席者は、電子メール アドレスへのアクセスのみを必要とします。|


## <a name="setting-up-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスのセットアップ

スケジューラ アシスタント メールボックスは、Exchangeまたはスケジューラ ライセンスを必要としない、Microsoft 365種類のメールボックスです。 スケジューラ アシスタントからのすべての電子メールは Cortana (つまり、"Cortana" または <cortana@yourdomain.com> "Cortana Scheduler") に署名されますので、メールボックスの表示名とプライマリ SMTP アドレスには Cortana が含まれている必要があります <cortana.scheduler@yourdomain.com> 。 スケジューラ アシスタント メールボックスを作成したら、そのメールボックスをスケジューラ アシスタント メールボックスとして指定する必要があります。 スケジューラ アシスタント メールボックスを指定すると、Cortanaに代わって会議をスケジュールすることができます。



- ユーザー メールボックスをMicrosoft 365 管理センターするには、ユーザー メールボックスを使用します。 30 日間の保持ポリシーをお勧めします。 
- メールボックスのプライマリ SMTP Cortanaの名前を使用します。 "Cortana@yourdomain.com"、'CortanaScheduler@contoso.com'、"Cortana" などの名前。Scheduler@yourdomain.com」 をお勧めします。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>メールボックスをスケジューラ アシスタントとして指定する

スケジューラの一意のメールボックスCortanaした後、メールボックスを正式に作成Microsoft 365必要があります。 スケジューラ メールボックスを指定Cortana、ユーザーに代わって会議をスケジュールできます。

#### <a name="connect-to-powershell"></a>Connect PowerShell へのアクセス

ユーザー メールボックスをMicrosoft 365 管理センターするには、ユーザー メールボックスを使用します。 30 日間の保持ポリシーをお勧めします。
メールボックスのプライマリ SMTP Cortanaの名前を使用します。 "Cortana@yourdomain.com"、'CortanaScheduler@contoso.com'、"Cortana" などの名前。Scheduler@yourdomain.com」 をお勧めします。

```PowerShell

$domain="yourdomain.com  "
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin

```

#### <a name="create-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスの作成

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 

```
    
#### <a name="designate-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスの指定

```PowerShell

Set-mailbox cortana@$domain -SchedulerAssistant:$true


```
Cortana スケジューラ アシスタント メールボックスでこの "set" コマンドを実行すると、このメールボックスが "SchedulerAssistant" である点に注意する新しい "PersistedCapability" がメールボックスに設定されます。

>[!Note]
> 組織を PowerShell に接続する方法については、「PowerShell を使用して組織[Connect Microsoft 365」を参照してください。](/microsoft-365/enterprise/connect-to-microsoft-365-powershell)

### <a name="verifying-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスの確認

スケジューラ アシスタント メールボックスが作成されたを確認するには

```PowerShell

Get-CalendarProcessing cortana$domain <cortana>@microsoft.com   | fl DeleteNonCalendarItems`

```

結果は "false" である必要があります。

<br>

```PowerShell

Get-Mailbox -Identity <cortana>@microsoft.com$domain -Organization microsoft.com$domain | fl *type*

```

結果は次の値になります。
- ResourceType: 機器
- リモート RecipientType: なし
- RecipientType: UserMailbox
- RecipientTypeDetails: EquipmentMailbox

</br>

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>スケジューラ アシスタント メールボックスがどのメールボックスか確認するには

```PowerShell

Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

>[重要]スケジューラ アシスタント メールボックスが完全なプロビジョニングを完了して SchedulerAssistant 機能を設定するには、数時間かかる場合があります。


## <a name="exchange-online-mailbox"></a>Exchange Online メールボックス
スケジューラ ライセンスは、会議の開催者が会議のスケジュール タスクをスケジューラ アシスタントに委任できる、Microsoft 365のアドオンです。 会議開催者には、スケジューラ アシスタント メールボックスとしてメールボックスを指定する以外に、スケジューラ ライセンスと Exchange Online メールボックスと予定表が必要です。通常はスケジューラの Microsoft 365 ライセンスを使用して動作します。 会議の出席者には、スケジューラ ライセンスまたはユーザー ライセンスはMicrosoft 365ではありません。

スケジューラ アドオンを購入するには、次のいずれかのライセンスが必要です。

- Microsoft 365 E3、A3、E5、A5
- Business Basic, Business, Business Standard, Business プレミアム
- Office 365 E1、A1、E3、A3、E5、A5
- Business Essentials, Business プレミアム
- Exchange Onlineプラン 1 またはプラン 2 ライセンス。 

> [!Note]

> ユーザーのMicrosoft 365は、英語でのみ世界中のマルチテナント環境で利用できます。 **次のMicrosoft 365** ユーザーが利用できない場合は、次のスケジューラを使用できます。

- Microsoft 365 21Vianet が運営する中国
- Microsoft 365トラスティ German Telekom を使用するドイツのクラウドを使用する場合
- 政府機関向けクラウド (GCC、コンシューマー、GCC、DoD など)

スケジューラーは、データの場所がドイツのデータセンターではないドイツのユーザーをサポートします。
