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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286188"
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

- 管理センター Microsoft 365を使用して、新しいメールボックスを作成します。 30 日間の保持ポリシーをお勧めします。 メールボックスのプライマリ SMTP アドレスで Cortana という名前を使用します。 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"、"Cortana.Scheduler@yourdomain.com" などの名前をお勧めします。
- Cortana メールボックスを有効にするには、microsoft (scheduler_m365@microsoft.com) に問い合わせください。 

> [!IMPORTANT]
> スケジューラ サービスを使用する Cortana メールボックスを構成するには、Microsoft に問い合 scheduler_m365@microsoft.com。 Cortana メールボックスを有効にすると、最大 2 週間かかる場合があります。

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
