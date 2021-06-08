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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809193"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>スケジューラのセットアップ Microsoft 365

スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。

|**必要なもの** |**説明** |
|-------------------|-------------|
|Cortana メールボックス |テナント管理者は、"Cortana" メールボックスとして機能するメールボックスを設定する必要があります (つまり、cortana@yourdomain.com)。         |
|Exchange Online メールボックス |ユーザーはメールと予定表Exchange Online必要があります         |
|スケジューラ ライセンス |ライセンスと価格の情報については[、「Scheduler for Microsoft 365」 を参照してください](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>Cortana のメールボックスを作成する
テナントExchangeメールボックスは、Cortana との間で電子メールを送受信するテナントの Cortana メールボックスとして機能します。 Cortana に送信されたメールはすべて、保持ポリシーに基づいてテナントの Cortana メールボックスに保持されます。

- 管理者センター Microsoft 365を使用して、ユーザー メールボックスを作成します。 30 日間の保持ポリシーをお勧めします。 
- メールボックスのプライマリ SMTP アドレスで Cortana という名前を使用します。 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"、"Cortana.Scheduler@yourdomain.com" などの名前をお勧めします。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>メールボックスをスケジューラ アシスタントとして指定する

Cortana Scheduler の一意のメールボックスが作成された後、メールボックスを正式に作成Microsoft 365必要があります。 Cortana Scheduler メールボックスを指定すると、ユーザーに代わって会議をスケジュールできます。

Cortana Scheduler メールボックスを指定するには、承認された管理者が 1 行の PowerShell コマンドを実行する必要があります。 

1. Connect、組織Microsoft 365 PowerShell のリモート実行領域を使用できます。
2. スケジューラのメールボックスを指定するには、次の PowerShell スクリプトを実行します。

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Cortana Scheduler メールボックスでこの "set" コマンドを実行した後、このメールボックスが "SchedulerAssistant" である点に注意する新しい "PersistedCapability" がメールボックスに設定されます。

> [!NOTE]
> 以前に行ったことがない場合は、次の手順に従って組織を PowerShell に接続します。 Connect PowerShell Microsoft 365 - Microsoft 365 Enterprise | [Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

現在 Cortana Scheduler アシスタントとして設定されている組織内のメールボックスを確認するには、get 関数を実行します。
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> SchedulerAssistant 機能を設定するには、スケジューラ メールボックスが完全なプロビジョニングを完了するために最大 2 時間かかる場合があります。

## <a name="exchange-online-mailbox"></a>Exchange Online メールボックス
スケジューラは、ユーザーに対するMicrosoft 365。 会議の開催者は、スケジューラがExchange Onlineメールボックスと予定表を持っている必要があります。

## <a name="exchange-requirements"></a>Exchange の要件

スケジューラのライセンスに加えて、次のいずれかのライセンスが必要です。

- Microsoft 365 E3、A3、E5、A5
- Business Basic, Business, Business Standard, Business プレミアム
- Office 365E1、A1、E3、A3、E5、A5
- Business Essentials, Business プレミアム
- Exchange Onlineプラン 1 またはプラン 2 ライセンス。 

> [!Note]
> 21Vianet **Microsoft 365** 21Vianet が運営するユーザーは、Office 365スケジューラを使用できません。 また、データ トラスティ German Telekom をMicrosoft 365ドイツのクラウドを使用しているユーザーは利用できません。 ドイツのユーザーでも、そのデータがドイツのデータセンター以外の場所にある場合は、サポートされます。
>
>この機能は、GCC、Consumer、GCC High、DoD などの政府機関向けクラウドのユーザーに対してもサポートされていません。
