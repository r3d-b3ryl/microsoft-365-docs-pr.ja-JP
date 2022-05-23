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
description: Microsoft 365でMicrosoft Bookingsにアクセスする方法について説明します。
ms.openlocfilehash: 98c6ae99bceada7649dc823ca88669ae0081fc10
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637298"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings を有効または無効にする

Bookingsは、組織全体または特定のユーザーに対してオンまたはオフにできます。 ユーザーのBookingsを有効にすると、ユーザーはBookings ページを作成したり、予定表を作成したり、他のユーザーが時間を予約したりできます。 この記事は、組織のBookingsを管理する所有者と管理者を対象としています。

> [!NOTE]
> これらのセクションで説明する管理者コントロールは、Office 365 21Vianet (中国) のお客様が操作することはできません。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して組織のBookingsをオンまたはオフにする

1. グローバル管理者としてMicrosoft 365 管理センターにサインインします。

2. 管理センターで、[**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**組織の設定]**</a> に移動します。

3. [**組織がBookingsを使用して組織のBookings** を有効または無効にすることを許可する] チェック ボックスをオンにします。

   > [!NOTE]
   > Bookingsをオフにすると、Bookings ページの作成と管理を含むサービスへのすべてのアクセスが無効になります。

4. [**変更を保存**] を選択します。

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織のBookingsをオンまたはオフにする

PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) を使用して組織のBookingsをオンまたはオフにするには、PowerShell [をExchange Onlineし](/powershell/exchange/connect-to-exchange-online-powershell)、次のコマンドを実行Connect。

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="granular-controls"></a>詳細なコントロール

以下の設定を使用して、Bookingsを使用できるユーザーを制御し、共有するBookings情報を決定し、スタッフが Booking カレンダーに追加する前に承認を必要とするかどうかを決定します。

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="スクリーンショット: Bookingsを使用できるユーザーを制御できる設定、共有するBookings情報とスタッフの承認を決定する":::

### <a name="block-bookings-from-outside-your-organization"></a>組織外からの予約をブロックする

組織内のユーザーのみが予定を予約できるように、Bookingsを設定できます。 サインインして認証された組織内のユーザーのみが、予定を予約できます。

### <a name="block-social-sharing-options"></a>ソーシャル共有オプションをブロックする

ソーシャル ネットワークで予約ページを共有する方法を制御できます。 この設定は、設定 **Org 設定** -> **Bookings** の **Microsoft 365 管理センター** -> で使用できます。

### <a name="block-sharing-staff-details-with-customers"></a>顧客とのスタッフの詳細の共有をブロックする

連絡先情報などのスタッフの詳細は、電子メールやその他の通信を介して顧客に送信されることはありません。

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>空き時間情報を共有する前にスタッフの承認を必要とする

組織内の従業員に対して、可用性情報がBookingsを通じて共有される前と、予約ページを通じて予約可能になる前にオプトインするように要求できます。

この設定を有効にすると、予約カレンダーにスタッフとして追加されたユーザーに、要求の **承認と拒否** へのリンクが記載されたメールが届きます。

## <a name="restrict-collection-of-customer-data"></a>顧客データの収集を制限する

コンプライアンス上の理由から、一部の顧客情報を収集したくない場合があります。 これらのオプションのチェック ボックスをオンにした場合、これらのフィールドはクライアントまたは顧客に表示されるフォームには含まれません。

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="スクリーンショット: 顧客が機密データを共有できないようにするには、チェック ボックスをオンにします。":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>個々のユーザーのBookingsをオンまたはオフにする

個々のユーザーのBookingsを無効にすることができます。

1. Microsoft 365 管理センターに移動し、[**ユーザー**<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**アクティブ ユーザー**</a>\>] を選択します。

1. 目的のユーザーを選択し、[ **ライセンスとアプリ**] を選択します。

1. **[アプリ] を** 展開し、Microsoft Bookingsのチェック ボックスをオフにします。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>選択したユーザーのみがBookings予定表を作成できるようにする

ポリシー制限を使用すると、ライセンスを持つユーザーがBookings予定表を作成できないように制限できます。 まず、組織全体のBookingsを有効にする必要があります。 組織内のすべてのユーザーにBookingsライセンスが付与されますが、ポリシーに含まれるユーザーのみがBookings予定表を作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。

このポリシーに含まれているユーザーは、新しいBookings予定表を作成でき、既存のBookings予定表に任意の容量 (管理者ロールを含む) のスタッフとして追加できます。 このポリシーに含まれていないユーザーは、新しいBookingsカレンダーを作成できず、そうしようとするとエラー メッセージが表示されます。

PowerShell を使用して次のコマンドExchange Online実行する必要があります。 Exchange Online コマンドレットの実行の詳細については、「[PowerShell をExchange OnlineするConnect」を](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。

> [!IMPORTANT]
> 次の手順では、組織内に他のOutlook Web App (OWA) メールボックス ポリシーが作成されていないことを前提としています。

1. Bookings予定表の作成を許可する必要があるユーザーの新しいメールボックス ポリシーを作成します。 (Bookings予定表の作成は、既定で新しいメールボックス ポリシーで許可されます。

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   詳細については、「 [New-OwaMailboxPolicy」を参照](/powershell/module/exchange/new-owamailboxpolicy)してください。

2. このポリシーを関連ユーザーに割り当てるには、Bookings予定表を作成するアクセス許可を付与するユーザーごとにこのコマンドを実行します。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   詳細については、「[Set-CASMailbox](/powershell/module/exchange/set-casmailbox)」を参照してください。

3. 省略可能: 組織内の他のすべてのユーザーのBookingsを無効にする場合は、このコマンドを実行します。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

詳細については、「[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。

OWA メールボックス ポリシーの詳細については、次のトピックを参照してください。

- [Exchange OnlineでOutlook on the webメールボックス ポリシーを作成する](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online内のメールボックスにOutlook on the webメールボックス ポリシーを適用または削除する](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
