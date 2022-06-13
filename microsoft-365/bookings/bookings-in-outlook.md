---
title: Outlookでの予約
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ROBOTS: NO INDEX, NO FOLLOW
description: Outlookで Bookings を使用して、他のユーザーがOutlookで自分と会議をスケジュールできるようにします。
ms.openlocfilehash: 96a150894e27de9f558b81e4f3deaef0d4f3dfa5
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044090"
---
# <a name="bookings-in-outlook"></a>Outlookでの予約

Outlookの予約は、Outlook予定表の空き時間情報と統合された Web ベースの個人用スケジュール ページです。 Outlookでの予約では、ユーザーが自分と一緒に会議や予定をスケジュールできます。 他のユーザーと共有するカスタム会議の種類を作成して、空き時間と好みに基づいて簡単に時間をスケジュールできます。 両方とも電子メールの確認を受け取り、出席者は自分の予約ページからスケジュールされた会議を更新またはキャンセルOutlook。

> [!NOTE]
> Outlookでの予約はプレビューでのみ利用できます。

Outlookの予約には、次の 2 つの異なるビューがあります。

- **開催者ビュー** 他のユーザーが予約できる会議の種類を作成できる個人用の予約ページ。 カスタム会議の種類を使用すると、会議を行うタイミングや、その会議の種類を他のユーザーと共有する方法をカスタマイズできます。 各会議の種類をスケジュール 設定ページに公開するか、非公開にするかを制御し、選択したユーザー グループのみがアクセスできます。 また、Outlook ページで予約したすべての会議にTeams会議を追加することもできます。 Outlook on the webを使用して、Outlook ページで Bookings にアクセスできます。 ページを設定して発行したら、他のユーザーと共有できます。 たとえば、Outlook署名に追加できます。

- **[スケジュール] ビュー** Outlook ページで自分の予約を他のユーザーと共有すると、スケジュール設定ビューが表示されます。 スケジュール 設定ビューに表示される会議は、パブリック会議で Bookings へのリンクOutlook共有したか、個々の会議のプライベート リンクを共有したかによって異なります。
  - パブリック会議は、自分の Bookings をOutlookページ リンクに含めるすべてのユーザーが表示およびスケジュール設定できます。 そのリンクを共有するユーザーを制御できます。 すべての公開会議の種類は、自分の Bookings をページ リンクに含めるすべてのユーザー Outlook表示されます。
  - プライベート会議は、その会議の種類のリンクを持つユーザーのみが表示できます。 パブリック会議とプライベート会議の違いは、プライベート会議には異なるリンクを持つ可能性があり、リンクは 90 日後に期限切れになる場合があります。 プライベート リンクは、1 回限りの予約後に期限切れに設定することもできます。 プライベート会議のスケジュール設定ビューにアクセスすると、その会議の種類のみが表示されます。

## <a name="before-you-begin"></a>はじめに

Outlookの予約は、次のサブスクリプションで利用できます。

- Office 365: A3、A5、E1、E3、E5、F1、F3
- Microsoft 365: A3、A5、E1、E3、E5、F1、F3、Business Basic、Business Standard、Business プレミアム

Outlookの予約は、これらのサブスクリプションを持つユーザーに対して既定で有効になっています。

Outlookの予約には、**Bookings** にアクセスできるように、ユーザーに割り当てられたMicrosoft Bookingsサービス プランが必要です。 このサービス プランは、テナント管理者が有効または無効にすることができます。 そのため、**Microsoft Bookings** が割り当てられていない場合、Bookings アクセスは、前に示した SKU のいずれかに属している場合でも、ユーザーに対して拒否されます。

詳細については、「[Outlook Microsoft 365 ロードマップの Bookings」を参照してください](https://go.microsoft.com/fwlink/?linkid=328648)。

## <a name="turn-bookings-in-outlook-on-or-off"></a>Outlookで Bookings をオンまたはオフにする  

Outlookの予約は、組織全体または特定のユーザーに対して有効または無効にすることができます。 Outlookの Bookings が有効になっている場合、ユーザーはOutlookページで Bookings を作成し、組織内または外部の他のユーザーとリンクを共有できます。

### <a name="turn-bookings-in-outlook-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織のOutlookで Bookings を有効または無効にする

PowerShell を使用して次のコマンドExchange Online実行する必要があります。 Exchange Online コマンドレットの実行の詳細については、「[PowerShell をExchange OnlineするConnect」を](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。 PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) を使用して組織のOutlookで Bookings をオンまたはオフにするには、PowerShell [をExchange Onlineし](/powershell/exchange/connect-to-exchange-online-powershell)、次のコマンドを実行Connect。

**Get-OrganizationConfig** コマンドと **Set-OrganizationConfig** コマンドを使用して、組織の状態を確認し、Outlookで Bookings をオンまたはオフにします。

> [!NOTE]
> 通常、Set-OrganizationConfig コマンドがユーザーに対して有効になるまでに約 30 ~ 60 分かかります。

1. 次のコマンドを実行して EWS コントロールのアクセスを確認します。

   ```PowerShell
   Get-OrganizationConfig | Format-List EwsEnabled
   ```

    コマンドが "EwsEnabled: **$true**" を返す場合は、手順 2 に進みます。

    コマンドが "EwsEnabled:" (空は既定) を返す場合は、有効にして手順 2 に進みます。

   ```PowerShell
   Set-OrganizationConfig -EwsEnabled: $true
   ```

2. 次のコマンドを実行して EwsApplicationAccessPolicy を確認します。

   ```PowerShell
   Get-OrganizationConfig | Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. **EwsApplicationAccessPolicy** の値が **EnforceAllowList** の場合、**EwsAllowList** に指定されているアプリケーションだけに EWS と REST へのアクセスが許可されます。

    - 組織のOutlookで Bookings を無効にするには、次のコマンドを実行して **、EwsAllowList** から **MicrosoftOWSPersonalBookings** (存在する場合) を削除します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - 組織のOutlookで Bookings を有効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EwsAllowList** に追加します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。

    - 組織のOutlookで Bookings を無効にするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - ブロックされた場合にOutlookで Bookings を有効にするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を削除します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. **EwsApplicationAccessPolicy** の値が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - 組織のOutlookで Bookings を無効にするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し **、MicrosoftOWSPersonalBookings** をブロック リストに追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsApplicationAccessPolicy EnforceBlockList -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
   
  > [!NOTE]
  > EwsApplicationAccessPolicy パラメーターは、Entourage、Outlook、Outlook for Mac以外のどのアプリケーションが EWS にアクセスできるかを定義します。

### <a name="turn-bookings-in-outlook-off-or-on-for-individual-users"></a>個々のユーザーの予約をOutlookでオフまたはオンにする

**Get-CASMailbox** コマンドと **Set-CASMailbox** コマンドを使用して、組織内の個々のユーザーに対してユーザーの状態を確認し、Outlookで Bookings をオンまたはオフにします。

1. 次のコマンドを実行して、個人の EWS 制御アクセスを確認します。

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsEnabled
   ```

    **A**. コマンドが "**EwsEnabled: $true**" を返す場合は、手順 2 に進みます。

2. 次のコマンドを実行して、個人の **EwsApplicationAccessPolicy** を確認します。

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. **EwsApplicationAccessPolicy** の値が **EnforceAllowList** の場合、EwsAllowList に指定されているアプリケーションだけに EWS と REST へのアクセスが許可されます。

    - このユーザーのOutlookで Bookings を無効にするには、次のコマンドを実行して **EwsAllowList** から **MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーのOutlookで Bookings を有効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EwsAllowList** に追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。  

    - このユーザーのOutlookで Bookings を無効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EnforceBlockList** に追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーのOutlookで Bookings を有効にするには、次のコマンドを実行して、**EnforceBlockList から MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. EwsApplicationAccessPolicy の値が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - このユーザーのOutlookで Bookings を無効にするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し **、MicrosoftOWSPersonalBookings** を EWSBlockList に追加します。

    ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsApplicationAccessPolicy EnforceBlockList -EWSBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
