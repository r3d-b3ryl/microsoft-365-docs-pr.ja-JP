---
title: OutlookのBookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ROBOTS: NO INDEX, NO FOLLOW
description: OutlookでBookingsを使用して、他のユーザーがOutlookで自分と一緒に会議をスケジュールできるようにします。
ms.openlocfilehash: 9f8e1c4428133dce6f6ec9e539464271abfd8ffd
ms.sourcegitcommit: 35d0c891f3d927f3346044be61ab9f348e8da2b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2022
ms.locfileid: "65364281"
---
# <a name="bookings-in-outlook"></a>OutlookのBookings

OutlookのBookingsは、Outlook予定表の空き時間情報と統合された Web ベースの個人用スケジュール ページです。 OutlookのBookingsを使用すると、ユーザーは会議や予定を自分でスケジュールできます。 他のユーザーと共有するカスタム会議の種類を作成して、空き時間と好みに基づいて簡単に時間をスケジュールできます。 両方ともメールの確認を受け取り、出席者はOutlookページでBookingsからスケジュールされた会議を更新またはキャンセルできます。

> [!NOTE]
> OutlookのBookingsはプレビューでのみ使用できます。

OutlookのBookingsには、次の 2 つの異なるビューがあります。

- **開催者ビュー** 他のユーザーが予約できる会議の種類を作成できる個人用の予約ページ。 カスタム会議の種類を使用すると、会議を行うタイミングや、その会議の種類を他のユーザーと共有する方法をカスタマイズできます。 各会議の種類をスケジュール 設定ページに公開するか、非公開にするかを制御し、選択したユーザー グループのみがアクセスできます。 また、Outlook ページでBookingsを通じて予約されたすべての会議にTeams会議を追加することもできます。 Outlook on the webからOutlookページでBookingsにアクセスできます。 ページを設定して発行したら、他のユーザーと共有できます。 たとえば、Outlook署名に追加できます。

- **[スケジュール] ビュー** Outlook ページでBookingsを他のユーザーと共有すると、スケジュール 設定ビューが表示されます。 スケジュール 設定ビューに表示される会議は、Outlook ページでBookingsへのリンクをパブリック会議と共有したか、個々の会議のプライベート リンクを共有したかによって異なります。
    - パブリック会議は、Outlook ページ リンクにBookingsがあるすべてのユーザーが表示およびスケジュール設定できます。 そのリンクを共有するユーザーを制御できます。 すべてのパブリック会議の種類は、Outlookページ リンクにBookingsがあるすべてのユーザーに表示されます。
    - プライベート会議は、その会議の種類のリンクを持つユーザーのみが表示できます。 パブリック会議とプライベート会議の違いは、プライベート会議には異なるリンクを持つ可能性があり、リンクは 90 日後に期限切れになる場合があります。 プライベート リンクは、1 回限りの予約後に期限切れに設定することもできます。 プライベート会議のスケジュール設定ビューにアクセスすると、その会議の種類のみが表示されます。

## <a name="before-you-begin"></a>はじめに

OutlookのBookingsは、次のサブスクリプションで使用できます。

- Office 365: A3、A5、E1、E3、E5、F1、F3
- Microsoft 365: A3、A5、E1、E3、E5、F1、F3、Business Basic、Business Standard、Business プレミアム

OutlookのBookingsは、これらのサブスクリプションを持つユーザーに対して既定でオンになっています。

詳細については、「[Outlook Microsoft 365 ロードマップ」の項目のBookings](https://go.microsoft.com/fwlink/?linkid=328648)を参照してください。

## <a name="turn-bookings-in-outlook-on-or-off"></a>OutlookでBookingsをオンまたはオフにする  

OutlookのBookingsは、組織全体または特定のユーザーに対してオンまたはオフにすることができます。 OutlookのBookingsがオンになっている場合、ユーザーはOutlookページでBookingsを作成し、組織内または外部の他のユーザーとリンクを共有できます。

### <a name="turn-bookings-in-outlook-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して組織のOutlookでBookingsをオンまたはオフにする

PowerShell を使用して次のコマンドExchange Online実行する必要があります。 Exchange Online コマンドレットの実行の詳細については、「[PowerShell をExchange OnlineするConnect」を](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。 PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) を使用して組織のOutlookのBookingsをオンまたはオフにするには、PowerShell [をExchange Onlineし](/powershell/exchange/connect-to-exchange-online-powershell)、次のコマンドを実行Connect。

**Get-OrganizationConfig** コマンドと **Set-OrganizationConfig** コマンドを使用して、状態を確認し、組織のOutlookでBookingsをオンまたはオフにします。

> [!NOTE]
> 通常、Set-OrganizationConfig コマンドがユーザーに対して有効になるまでに約 30 ~ 60 分かかります。

1. 次のコマンドを実行して EWS コントロールのアクセスを確認します。

   ```PowerShell
   Get-Organizationconfig | Format-List EwsEnabled
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

    - 組織のOutlookでBookingsをオフにするには、次のコマンドを実行して **EwsAllowList** から **MicrosoftOWSPersonalBookings** (存在する場合) を削除します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - 組織のOutlookでBookingsを有効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EwsAllowList** に追加します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。

    - 組織のOutlookでBookingsをオフにするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - ブロックされている場合は、OutlookでBookingsを有効にするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を削除します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**.  **値EwsApplicationAccessPolicyis**  が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - 組織のOutlookでBookingsをオフにするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し、**MicrosoftOWSPersonalBookings** をブロック リストに追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsApplicationAccessPolicy EnforceBlockList -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

### <a name="turn-bookings-in-outlook-off-or-on-for-individual-users"></a>個々のユーザーのOutlookのBookingsをオンまたはオフにする

**Get-CASMailbox** コマンドと **Set-CASMailbox** コマンドを使用して、ユーザーの状態を確認し、組織内の個々のユーザーのOutlookでBookingsをオンまたはオフにします。

1. 次のコマンドを実行して、個人の EwsApplicationAccessPolicy を確認します。

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsEnabled
   ```

    **A**. コマンドが "**EwsEnabled: $true**" を返す場合は、手順 2 に進みます。

2. 次のコマンドを実行して、個人の **EwsApplicationAccessPolicy** を確認します。

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com| Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. **EwsApplicationAccessPolicy** の値が **EnforceAllowList** の場合、EwsAllowList に指定されているアプリケーションだけに EWS と REST へのアクセスが許可されます。

    - このユーザーのOutlookでBookingsをオフにするには、次のコマンドを実行して **EwsAllowList** から **MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーのOutlookでBookingsを有効にし、次のコマンドを実行して **、EwsAllowList** に **MicrosoftOWSPersonalBookings** を追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。  

    - このユーザーのOutlookでBookingsをオフにするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EnforceBlockList** に追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsApplicationAccessPolicy  EnforceBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーのOutlookでBookingsを有効にするには、次のコマンドを実行して、**EnforceBlockList から MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. EwsApplicationAccessPolicy の値が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - このユーザーのOutlookでBookingsをオフにするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し、 **addMicrosoftOWSPersonalBookingsto**  EWSBlockList を追加します。

    ```PowerShell
   Set-CASMailbox -Identity Adam -EwsApplicationAccessPolicy  EnforceBlockList -EWSBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
