---
title: Microsoft Bookings を有効または無効にする
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft Bookings にアクセスする方法については、Microsoft 365。
ms.openlocfilehash: cc0352166bf7cd20cfa10542d57da9fbd5b160f7
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823819"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings を有効または無効にする

予約は、組織全体または特定のユーザーに対して有効または無効にできます。 ユーザーの予約を有効にした場合、ユーザーは [予約] ページを作成し、予定表を作成し、他のユーザーが自分と一緒に時間を予約できます。

> [!NOTE]
> これらのセクションで説明する管理コントロールは、21Vianet (中国) Office 365によって運用されているユーザーには使用できません。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>ユーザー設定を使用して組織の予約を有効またはMicrosoft 365 管理センター

1. グローバル管理者としてMicrosoft 365 管理センターサインインします。

2. 管理センターで、[組織] **** ページに移動   \> **設定、[設定]** **を選択します**。

3. [組織で予約 **を使用して組織の予約** を有効または無効にする] チェック ボックスをオンにします。

   > [!NOTE]
   > Bookings をオフにすると、Bookings ページの作成と管理を含むサービスへのすべてのアクセスが無効になります。

4. [**変更を保存**] を選択します。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織の予約を有効またはオフにする

PowerShell コマンドレット[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)を使用して組織の予約を有効またはConnect [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) Exchange Online実行し、次のコマンドを実行します。

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>個々のユーザーの予約をオンまたはオフにする

個々のユーザーの予約を無効にできます。

1. [ユーザー] に移動Microsoft 365 管理センター、[ユーザー] [アクティブユーザー **]** \> **を選択します**。

1. 目的のユーザーを選択し、[ライセンスとアプリ **] を選択します**。

1. [アプリ **] を展開** し、[Microsoft Bookings] のチェック ボックスをオフにします。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>空き時間情報を共有する前にスタッフの承認を要求する

管理者は、予約ページを通じて予約可能になる前に、利用可能な情報を共有する前に、組織内の従業員にオプトインを要求できます。 この設定は、[予約] の [Microsoft 365 管理センター] の \> **設定設定** \> **使用できます**。

この設定を有効にすると、予約カレンダーにスタッフとして追加された従業員は、受信した電子メール通知に [承認/拒否] リンクを見つける。

## <a name="block-social-sharing-options"></a>ソーシャル共有オプションをブロックする

管理者は、予約ページをソーシャル ネットワーク上で共有する方法を制御できます。 この設定は、[予約] の [Microsoft 365 管理センター] の \> **設定設定** \> **使用できます**。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>選択したユーザーにのみ予約カレンダーの作成を許可する

ポリシー制限を使用すると、ライセンスユーザーが予約カレンダーを作成できないのを制限できます。 まず、組織全体で予約を有効にする必要があります。 組織内のすべてのユーザーは Bookings ライセンスを持ちますが、ポリシーに含まれているユーザーだけが Bookings カレンダーを作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。

このポリシーに含まれるユーザーは、新しい Bookings カレンダーを作成し、既存の Bookings カレンダーに任意の容量 (管理者ロールを含む) のスタッフとして追加できます。 このポリシーに含まれていないユーザーは、新しい予約カレンダーを作成できないので、新しい予約カレンダーを作成しようとしてもエラー メッセージが表示されます。

PowerShell を使用して次のコマンドを実行Exchange Onlineがあります。 コマンドレットの実行の詳細についてはExchange Online PowerShell のConnect[をExchange Onlineしてください](/powershell/exchange/connect-to-exchange-online-powershell)。

> [!IMPORTANT]
> 以下の手順では、組織内に他Outlook Web App (OWA) メールボックス ポリシーが作成されていないことを前提とします。

1. 予約カレンダーの作成を許可する必要があるユーザー用の新しいメールボックス ポリシーを作成します。 (予約カレンダーの作成は、新しいメールボックス ポリシーによって既定で許可されます)。

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   詳細については [、「New-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/new-owamailboxpolicy)。

2. このポリシーを関連するユーザーに割り当てるには、予約カレンダーを作成するアクセス許可を付与するユーザーごとにこのコマンドを実行します。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   詳細については、「[Set-CASMailbox](/powershell/module/exchange/set-casmailbox)」を参照してください。

3. オプション: 組織内の他のすべてのユーザーの予約を無効にする場合は、このコマンドを実行します。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   詳細については、「[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。

OWA メールボックス ポリシーの詳細については、次のトピックを参照してください。

- [メールボックス ポリシー Outlook on the web作成するExchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [メールボックス内のメールボックスにOutlook on the webメールボックス ポリシーを適用または削除Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)