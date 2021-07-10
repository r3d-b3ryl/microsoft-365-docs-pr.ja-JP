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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362548"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Scheduler for Microsoft 365 を設定する


スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。

| 必要なもの | 説明 |
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
> 以前に行ったことがない場合は、次の手順に従って組織を Power [Microsoft 365 Connect Shell](../enterprise/connect-to-microsoft-365-powershell.md)に接続します。

組織で現在スケジューラ アシスタントとして設定されているメールボックスをCortana、get 関数を実行します。

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> SchedulerAssistant 機能を設定するには、スケジューラ メールボックスが完全なプロビジョニングを完了するために最大 2 時間かかる場合があります。

## <a name="exchange-online-mailbox"></a>Exchange Online メールボックス
スケジューラ ライセンスは、会議の開催者が会議Microsoft 365スケジュール タスクをスケジューラ アシスタントに委任できる、ユーザーに対するアドオンです。 スケジューラが動作するには、通常、Microsoft 365ライセンスを使用して、会議の開催者には次のコンポーネントが必要です。

- スケジューラ アシスタント メールボックスとして指定されたメールボックス
- スケジューラ ライセンス
- Exchange Onlineと予定表

会議の出席者は、スケジューラまたはユーザー ライセンスをMicrosoft 365ではありません。

## <a name="scheduler-end-user-license-requirements"></a>スケジューラーのエンド ユーザー ライセンス要件

スケジューラ ライセンスには、次のいずれかのライセンスが必要です。

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

スケジューラーは、ドイツのデータセンターにデータの場所が存在しないドイツのユーザーをサポートします。
