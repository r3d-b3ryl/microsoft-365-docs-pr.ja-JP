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
ms.openlocfilehash: f09d1f51ed8a868712c22fbd7a641b35f5d29073
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309348"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Scheduler for Microsoft 365 を設定する


スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。

|**必要なもの** |**説明** |
|-------------------|-------------|
|Cortanaメールボックス |テナント管理者は、"Cortana" メールボックス (つまり、cortana@yourdomain.com) として機能するメールボックスを設定する必要があります。         |
|Exchange Online メールボックス |ユーザーはメールと予定表Exchange Online必要があります         |
|スケジューラ ライセンス |ライセンスと価格の情報については[、「Scheduler for Microsoft 365」 を参照してください](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>ユーザーのメールボックスを作成Cortana
テナントExchangeメールボックスは、テナントの Cortana メールボックスとして機能し、テナントとの間で電子メールを送受信Cortana。 ユーザーに送信Cortanaメールは、保持ポリシーに基づいてCortanaのメールボックスに保持されます。

- ユーザー メールボックスをMicrosoft 365 管理センターするには、ユーザー メールボックスを使用します。 30 日間の保持ポリシーをお勧めします。 
- メールボックスのプライマリ SMTP Cortanaの名前を使用します。 "Cortana@yourdomain.com"、'CortanaScheduler@contoso.com'、"Cortana" などの名前。Scheduler@yourdomain.com」 をお勧めします。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>メールボックスをスケジューラ アシスタントとして指定する

スケジューラの一意のメールボックスCortanaした後、メールボックスを正式に作成Microsoft 365必要があります。 スケジューラ メールボックスを指定Cortana、ユーザーに代わって会議をスケジュールできます。

スケジューラ メールボックスのCortana指定するには、承認された管理者が 1 行の PowerShell コマンドを実行する必要があります。 

1. Connect、組織Microsoft 365 PowerShell のリモート実行領域を使用できます。
2. スケジューラのメールボックスを指定するには、次の PowerShell スクリプトを実行します。

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Cortana スケジューラ メールボックスでこの "set" コマンドを実行した後、このメールボックスが "SchedulerAssistant" である点に注意する新しい "PersistedCapability" がメールボックスに設定されます。

> [!NOTE]
> 以前に行ったことがない場合は、次の手順に従って組織を PowerShell に接続します。 Connect PowerShell Microsoft 365 - Microsoft 365 Enterprise | [Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

組織で現在スケジューラ アシスタントとして設定されているメールボックスをCortana、get 関数を実行します。
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> SchedulerAssistant 機能を設定するには、スケジューラ メールボックスが完全なプロビジョニングを完了するために最大 2 時間かかる場合があります。

## <a name="exchange-online-mailbox"></a>Exchange Online メールボックス
スケジューラは、ユーザーに対するMicrosoft 365。 会議の開催者は、スケジューラがExchange Onlineメールボックスと予定表を持っている必要があります。

## <a name="exchange-requirements"></a>Exchange の要件

スケジューラのライセンスに加えて、次のいずれかのライセンスが必要です。

- Microsoft 365 E3、A3、E5、A5
- Business Basic, Business, Business Standard, Business プレミアム
- Office 365 E1、A1、E3、A3、E5、A5
- Business Essentials, Business プレミアム
- Exchange Onlineプラン 1 またはプラン 2 ライセンス。 

> [!Note]
> **現在、Microsoft 365** は英語でのみ、世界中のマルチテナントで利用できます。</br>
>
>中国で 21Vianet がOffice 365を運用しているユーザー、またはデータ トラスティ German Telekom を使用するドイツのクラウドを使用する Microsoft 365 のユーザーは使用できません。 ドイツのユーザーでも、そのデータがドイツのデータセンター以外の場所にある場合は、サポートされます。
>
>この機能は、GCC、Consumer、GCC High、DoD などの政府機関向けクラウドのユーザーに対してもサポートされていません。
