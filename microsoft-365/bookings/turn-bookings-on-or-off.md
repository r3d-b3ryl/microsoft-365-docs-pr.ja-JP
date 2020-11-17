---
title: Microsoft の予約をオンまたはオフにする
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365 で Microsoft の予約にアクセスする方法について説明します。
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126593"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft の予約をオンまたはオフにする

予約は、組織全体または特定のユーザーに対してオンまたはオフにすることができます。 ユーザーに対して予約を有効にすると、ユーザーは予約ページを作成し、予定表を作成して、他のユーザーに時間を表示させることができます。

> [!NOTE]
> これらのセクションで説明する管理者コントロールは、21Vianet (中国) のお客様が運用している Office 365 では使用できません。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して、組織の予約をオンまたはオフにする

1. グローバル管理者として Microsoft 365 管理センターにサインインします。

2. 管理センターで、[ **設定**] [組織の設定] に移動し、   \> **Org Settings** [**予約**] を選択します。

3. [組織で予約を **使用できるよう** にする] チェックボックスをオンにして、組織の予約を有効または無効にします。

   > [!NOTE]
   > 予約を無効にすると、予約ページの作成と管理を含む、サービスへのすべてのアクセスが無効になります。

4. [ **Save Changes**] を選びます。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織の予約をオンまたはオフにする

PowerShell コマンドレット [Set](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)を使用して、組織の予約をオンまたはオフにするには、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) し、次のコマンドを実行します。

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>個々のユーザーの予約を有効または無効にする

個々のユーザーに対して予約を無効にすることができます。

1. Microsoft 365 管理センターに移動し、[ **ユーザー** の \> **アクティブなユーザー**] を選択します。

1. 目的のユーザーを選択して、[ **ライセンスとアプリ**] を選択します。

1. [ **アプリ** ] を展開し、[Microsoft 予約] のチェックボックスをオフにします。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>空き時間情報を共有する前にスタッフの承認を必須にする

管理者は、組織内の従業員に対して、予約ページを通じて書籍を参照できるようにするために、組織内の従業員にオプトインを要求する必要があります。 この設定は、Microsoft 365 管理センターの [**設定** の予約] の下にあり \> **Settings** \> **Bookings** ます。

この設定を有効にすると、予定表にスタッフとして追加された従業員は、受信した電子メール通知の承認/拒否リンクを見つけます。

この機能は、全世界の Microsoft 365 ユーザーに徐々にロールアウトされています。 Microsoft 365 管理センターでこのオプションが表示されない場合は、もう一度確認してください。

## <a name="block-social-sharing-options"></a>ソーシャル共有オプションをブロックする

管理者は、ソーシャルネットワークで予約ページを共有する方法を制御できます。 この設定は、Microsoft 365 管理センターの [**設定** の予約] の下にあり \> **Settings** \> **Bookings** ます。

この機能は、全世界の Microsoft 365 ユーザーに徐々にロールアウトされています。 Microsoft 365 管理センターでこのオプションが表示されない場合は、もう一度確認してください。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>選択したユーザーのみに予約予定表の作成を許可する

ポリシーの制限を使用すると、ライセンスが付与されたユーザーが予約予定表を作成できないように制限できます。 最初に、組織全体で予約を有効にする必要があります。 組織内のすべてのユーザーは、予約ライセンスを持っていますが、ポリシーに含まれるもののみが予約予定表を作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。

このポリシーに含まれているユーザーは、新しい予約予定表を作成したり、既存の予約予定表に任意の容量 (管理者の役割を含む) にスタッフとして追加したりできます。 このポリシーに含まれていないユーザーは、新しい予約予定表を作成することができず、実行しようとするとエラーメッセージが表示されます。

Exchange Online PowerShell を使用して、次のコマンドを実行する必要があります。 Exchange Online のコマンドレットの実行の詳細については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

> [!IMPORTANT]
> 次の手順では、組織内に他の Outlook Web App (OWA) メールボックスポリシーが作成されていないことを前提としています。

1. 予約予定表の作成が許可されるユーザーの新しいメールボックスポリシーを作成します。 (予約予定表の作成は、新しいメールボックスポリシーによって既定で許可されます。)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   詳細については、「 [新しい-Owamが Boxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)」を参照してください。

2. 予約予定表を作成するためのアクセス許可を付与するユーザーごとに、このコマンドを実行して、このポリシーを関連するユーザーに割り当てます。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   詳細については、「[Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)」を参照してください。

3. オプション: 組織内の他のすべてのユーザーに対して予約を無効にする場合は、このコマンドを実行します。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   詳細については、「[Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。

OWA メールボックスポリシーの詳細については、以下のトピックを参照してください。

- [Exchange Online で Outlook on the web メールボックスポリシーを作成する](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online のメールボックスで Outlook on the web メールボックスポリシーを適用または削除する](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
