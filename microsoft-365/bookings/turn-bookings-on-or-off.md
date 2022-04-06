---
title: Microsoft Bookings を有効または無効にする
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 詳細については、このサイトでユーザーにアクセスMicrosoft BookingsをMicrosoft 365。
ms.openlocfilehash: 09fba96265bc3d2b67db9152f0c6020e10183314
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634803"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings を有効または無効にする

Bookings組織全体または特定のユーザーに対して有効または無効にできます。 ユーザーに対してBookingsを有効にした場合、ユーザーは Bookings ページを作成し、予定表を作成し、他のユーザーが自分と一緒に時間を予約できます。

> [!NOTE]
> これらのセクションで説明されている管理コントロールは、21Vianet (中国) Office 365によって運用されているユーザーには使用できません。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>[Bookingsを使用して組織の有効またはオフを切り替Microsoft 365 管理センター

1. グローバル管理者としてMicrosoft 365 管理センターサインインします。

2. 管理センターで、[組織の設定  **設定** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**移動します**</a>。

3. [組織が組織に対 **して組織を使用Bookings** を有効または無効Bookings] チェック ボックスをオンにします。

   > [!NOTE]
   > この機能をBookingsすると、サービスへのすべてのアクセス (ページの作成と管理を含む) がBookingsされます。

4. [**変更を保存**] を選択します。

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell をBookings組織の有効またはオフを切り替えます

PowerShell コマンドレット Bookings [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) を使用して組織の有効またはConnectを有効Exchange Online、次[の](/powershell/exchange/connect-to-exchange-online-powershell)コマンドを実行します。

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

以下の設定を使用して、Bookings を使用できるユーザー、共有する Bookings 情報、および予約カレンダーに追加する前にスタッフが承認を必要とするかどうかを決定します。

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="スクリーンショット: 設定を使用できるユーザーを制御し、Bookings情報Bookings決定し、スタッフの承認を行う":::

### <a name="block-bookings-from-outside-your-organization"></a>組織外からの予約をブロックする

組織のユーザーだけがBookings予約できるよう、ユーザーを設定できます。 組織内でサインインし、認証されたユーザーだけが予定を予約できます。

### <a name="block-social-sharing-options"></a>ソーシャル共有オプションをブロックする

予約ページをソーシャル ネットワークで共有する方法を制御できます。 この設定は、[Org の設定] の **Microsoft 365 管理センターの設定** -> **で使用Bookings** -> 。

### <a name="block-sharing-staff-details-with-customers"></a>顧客とのスタッフの詳細の共有をブロックする

連絡先情報などのスタッフの詳細は、電子メールや他の通信を介して顧客に送信されません。

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>空き時間情報を共有する前にスタッフの承認を要求する

組織内の従業員に対して、Bookings を通じて空き時間情報を共有する前、および予約ページから予約できる前に、オプトインを要求できます。

この設定を有効にすると、予約カレンダーにスタッフとして追加されたユーザーに、要求の承認/却下へのリンクが記載されたメール **が** 届きます。

## <a name="restrict-collection-of-customer-data"></a>顧客データの収集を制限する

コンプライアンス上の理由から、一部の顧客情報を収集したくない場合があります。 これらのオプションのチェック ボックスをオンにした場合、これらのフィールドはクライアントまたは顧客に表示されるフォームには含まれません。

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="スクリーンショット: チェック ボックスをオンにすると、顧客が機密データを共有しな":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>個々のBookingsのオンとオフを切り替えます

個々のユーザーのBookingsを無効にできます。

1. [ユーザー] に移動Microsoft 365 管理センター、[ユーザーのアクティブな **ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**を選択します**</a>。

1. 目的のユーザーを選択し、[ライセンスとアプリ **] を選択します**。

1. [アプリ **] を展開** し、[アプリ] のチェック ボックスをMicrosoft Bookings。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>選択したユーザーだけが予定表を作成Bookingsする

ポリシー制限を使用すると、ライセンスを持つユーザーが予定表を作成Bookingsできます。 まず、組織全体でBookingsを有効にする必要があります。 組織内のすべてのユーザーは Bookings ライセンスを持ちますが、ポリシーに含まれているユーザーだけが Bookings 予定表を作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。

このポリシーに含まれるユーザーは、新しい Bookings 予定表を作成し、既存の Bookings 予定表に任意の容量 (管理者ロールを含む) のスタッフとして追加できます。 このポリシーに含まれていないユーザーは、新しい Bookings カレンダーを作成する権限を持たないので、新しいカレンダーを作成しようとしてもエラー メッセージが表示されます。

PowerShell を使用して次のコマンドを実行Exchange Onlineがあります。 コマンドレットの実行の詳細についてはExchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) のConnectをExchange Onlineしてください。

> [!IMPORTANT]
> 以下の手順では、組織で他Outlook Web App (OWA) メールボックス ポリシーが作成されていないことを前提とします。

1. 予定表の作成を許可する必要があるユーザー用の新しいメールボックス Bookingsします。 (Bookingsの作成は、新しいメールボックス ポリシーによって既定で許可されます)。

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   詳細については、「 [New-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/new-owamailboxpolicy)。

2. このポリシーを関連するユーザーに割り当てるには、予定表を作成するためのアクセス許可を付与する各ユーザーに対してこのコマンドBookingsします。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   詳細については、「[Set-CASMailbox](/powershell/module/exchange/set-casmailbox)」を参照してください。

3. オプション: 組織内の他のすべてのユーザーに対してBookingsを無効にする場合は、このコマンドを実行します。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   詳細については、「[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。

OWA メールボックス ポリシーの詳細については、次のトピックを参照してください。

- [サーバーでOutlook on the webメールボックス ポリシーを作成Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [メールボックス内のメールボックスにOutlook on the webメールボックス ポリシーを適用または削除Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
