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
description: Microsoft 365 で Microsoft Bookings にアクセスする方法について説明します。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913768"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings を有効または無効にする

予約は、組織全体または特定のユーザーに対して有効または無効にできます。 ユーザーの予約を有効にした場合、ユーザーは [予約] ページを作成し、予定表を作成し、他のユーザーが自分と一緒に時間を予約できます。

> [!NOTE]
> これらのセクションで説明されている管理コントロールは、21Vianet (中国) のお客様Office 365 Operated では使用できません。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して組織の予約をオンまたはオフにする

1. グローバル管理者として Microsoft 365 管理センターにサインインします。

2. 管理センターで、[設定] [組織の  **設定**]   \> **に移動し、[** 予約]**を選択します**。

3. [組織で予約 **を使用して組織の予約** を有効または無効にする] チェック ボックスをオンにします。

   > [!NOTE]
   > Bookings をオフにすると、Bookings ページの作成と管理を含むサービスへのすべてのアクセスが無効になります。

4. [変更 **の保存] を選択します**。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織の予約を有効またはオフにする

PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)を使用して組織の予約を有効またはオフにする場合は [、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続し、次のコマンドを実行します。

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>個々のユーザーの予約をオンまたはオフにする

個々のユーザーの予約を無効にできます。

1. Microsoft 365 管理センターに移動し、[ユーザー] [アクティブユーザー **]** \> **を選択します**。

1. 目的のユーザーを選択し、[ライセンスとアプリ **] を選択します**。

1. [アプリ **] を展開** し、[Microsoft Bookings] のチェック ボックスをオフにします。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>空き時間情報を共有する前にスタッフの承認を要求する

管理者は、予約ページを通じて予約可能になる前に、利用可能な情報を共有する前に、組織内の従業員にオプトインを要求できます。 この設定は、Microsoft 365 管理センターの[設定設定の予約] \> **で** \> **使用できます**。

この設定を有効にすると、予約カレンダーにスタッフとして追加された従業員は、受信した電子メール通知に [承認/拒否] リンクを見つける。

この機能は、Microsoft 365 のお客様に世界全体で段階的に展開されています。 Microsoft 365 管理センターにこのオプションが表示しない場合は、すぐに確認してください。

## <a name="block-social-sharing-options"></a>ソーシャル共有オプションをブロックする

管理者は、予約ページをソーシャル ネットワーク上で共有する方法を制御できます。 この設定は、Microsoft 365 管理センターの[設定設定の予約] \> **で** \> **使用できます**。

この機能は、Microsoft 365 のお客様に世界全体で段階的に展開されています。 Microsoft 365 管理センターにこのオプションが表示しない場合は、すぐに確認してください。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>選択したユーザーにのみ予約カレンダーの作成を許可する

ポリシー制限を使用すると、ライセンスユーザーが予約カレンダーを作成できないのを制限できます。 まず、組織全体で予約を有効にする必要があります。 組織内のすべてのユーザーは Bookings ライセンスを持ちますが、ポリシーに含まれているユーザーだけが Bookings カレンダーを作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。

このポリシーに含まれるユーザーは、新しい Bookings カレンダーを作成し、既存の Bookings カレンダーに任意の容量 (管理者ロールを含む) のスタッフとして追加できます。 このポリシーに含まれていないユーザーは、新しい予約カレンダーを作成できないので、新しい予約カレンダーを作成しようとしてもエラー メッセージが表示されます。

Exchange Online PowerShell を使用して次のコマンドを実行する必要があります。 Exchange Online コマンドレットの実行の詳細については [、「Connect to Exchange Online PowerShell」を参照してください](/powershell/exchange/connect-to-exchange-online-powershell)。

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

- [Exchange Online で Outlook on the Web メールボックス ポリシーを作成する](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online のメールボックスで Outlook on the Web メールボックス ポリシーを適用または削除する](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)