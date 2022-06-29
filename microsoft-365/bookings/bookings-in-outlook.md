---
title: 自分で予約する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ROBOTS: NO INDEX, NO FOLLOW
description: 他のユーザーが Outlook で自分と会議をスケジュールできるようにするには、自分と一緒に予約を使用します。
ms.openlocfilehash: 076dc353107aa2499ec170ead5299d94404e351a
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66487340"
---
# <a name="bookings-with-me"></a>自分で予約する

Outlook での予約は、Outlook 予定表の空 **き** 時間情報と統合された Web ベースの個人用スケジュール ページです。 自分と一緒に予約すると、ユーザーは会議や予定を自分と一緒にスケジュールできます。 他のユーザーと共有するカスタム会議の種類を作成して、空き時間と好みに基づいて簡単に時間をスケジュールできます。 両方とも電子メールの確認を受け取り、出席者は自分の予約ページからスケジュールされた会議を更新またはキャンセルできます。

> [!NOTE]
> 私との予約は、プレビュー段階で世界中で利用できます。 プレビューに含まれる機能は完了していない可能性があり、パブリック リリースで利用可能になる前に変更が行われる可能性があります。

自分との予約には、次の 2 つの異なるビューがあります。

- **開催者ビュー** 他のユーザーが予約できる会議の種類を作成できる個人用の予約ページ。 カスタム会議の種類を使用すると、会議を行うタイミングや、その会議の種類を他のユーザーと共有する方法をカスタマイズできます。 各会議の種類をスケジュール 設定ページに公開するか、非公開にするかを制御し、選択したユーザー グループのみがアクセスできます。 [自分で予約] ページで予約したすべての会議に Teams 会議を追加することもできます。 Outlook on the webから自分の予約ページにアクセスできます。 ページを設定して発行したら、他のユーザーと共有できます。 たとえば、Outlook 署名に追加できます。

- **出席者ビュー** 他のユーザーと自分の予約ページを共有すると、出席者ビューが表示されます。 開催者が自分の Bookings と自分のページリンクを共有している場合は、すべての公開会議の種類を確認できます。 開催者が会議リンクを共有している場合は、その会議のみを表示できます。
  - 公開会議は、Bookings with me ページ リンクを持つすべてのユーザーが表示およびスケジュール設定できます。 そのリンクを共有するユーザーを制御できます。 すべての公開会議の種類は、Bookings with me ページ リンクを持つすべてのユーザーに表示されます。
  - プライベート会議は、その会議の種類のリンクを持つユーザーのみが表示できます。 パブリック会議とプライベート会議の違いは、プライベート会議には異なるリンクを持つ可能性があり、リンクは 90 日後に期限切れになる場合があります。 プライベート リンクは、1 回限りの予約後に期限切れに設定することもできます。 プライベート会議のスケジュール設定ビューにアクセスすると、その会議の種類のみが表示されます。

## <a name="when-to-use-bookings-with-me"></a>Bookings を自分と一緒に使用する場合

私と一緒に予約することは、教育機関の企業、小規模企業、およびユーザーが組織の内外のユーザーと 1 対 1 の会議をスケジュールするのに最適なソリューションです。 以下に、Bookings を一緒に使用する方法の例をいくつか示します。

- 外部候補者との面接をスケジュールする
- 顧客とクライアントの会議を設定する
- テクニカル サポートをスケジュールする
- 営業時間を設定する
- メンタリング時間を設定する
- ダイレクト レポートを使用した 1:1 の会議
- ランチとコーヒーの休憩

## <a name="before-you-begin"></a>はじめに

自分との予約は、組織全体または特定のユーザーに対してオンまたはオフにできます。 ユーザーの Bookings を有効にすると、ユーザーは Bookings ページを作成し、他のユーザーとページを共有し、他のユーザーが自分と時間を予約できるようにします。 この記事は、自分の組織で自分と一緒に Bookings を管理する所有者と管理者を対象としています。

自分との予約は、次のサブスクリプションで利用できます。

- Office 365: A3、A5、E1、E3、E5、F1、F3
- Microsoft 365: A3、A5、E1、E3、E5、F1、F3、Business Basic、Business Standard、Business Premium

これらのサブスクリプションを持つユーザーの場合、自分との予約は既定で有効になっています。

自分と一緒に予約するには、ユーザーが Bookings にアクセスできるようにするために、**Microsoft Bookings アプリ (サービス プラン)** が割り当てられている必要があります。 このサービス プランは、テナント管理者が有効または無効にすることができます。 そのため、**Microsoft Bookings** が割り当てられていない場合、Bookings アクセスは、前に示した SKU のいずれかに属している場合でも、ユーザーに対して拒否されます。

詳細については、「 [Bookings with me Microsoft 365 ロードマップ」の項目](https://go.microsoft.com/fwlink/?linkid=328648)を参照してください。

### <a name="prerequisites-for-using-bookings-with-me"></a>Bookings を自分と一緒に使用するための前提条件

1. 自分と Bookings との予約は、同じライセンス モデルを共有します。 ただし、ユーザーが自分と一緒に Bookings にアクセスするためのテナント設定を使用して、組織で Bookings を有効にする必要はありません。 ユーザーが自分で Bookings にアクセスできるようにするには、Bookings アプリを有効にする必要があります。

   Bookings にアクセスせずに自分で Bookings を有効にするには、[OWA メールボックス ポリシー PowerShell コマンド](/powershell/module/exchange/set-owamailboxpolicy?view=exchange-ps)を使用してMicrosoft Bookingsへのアクセスをブロックするか、次の手順に従います:[Microsoft Bookingsオンまたはオフにします](turn-bookings-on-or-off.md)。

2. 自分と一緒に Bookings を使用するには、予定表 FreeBusy 匿名共有を有効にする必要があります。 これにより、Bookings ページで Outlook 予定表の空き時間情報にアクセスできるようになります。 PowerShell を使用して状態を確認します。

   ```PowerShell
     Get-SharingPolicy -Identity "Default Sharing Policy" | fl Domains 
   ```

    "Anonymous:CalendarSharingFreeBusyReviewer"" は、応答のドメインの 1 つである必要があります。

   匿名共有を有効にするには、次のコマンドを使用します。

   ```PowerShell
     Set-SharingPolicy "Default Sharing Policy" -Domains @{Add="Anonymous:CalendarSharingFreeBusyReviewer"}
   ```

## <a name="turn-bookings-with-me-on-or-off"></a>自分で予約を有効または無効にする

自分との予約は、組織全体または特定のユーザーに対してオンまたはオフにできます。 自分と一緒に予約を有効にすると、ユーザーは自分のページで Bookings を作成し、組織内または外部の他のユーザーとリンクを共有できます。

### <a name="turn-bookings-with-me-on-or-off-for-your-organization-using-powershell"></a>PowerShell を使用して、組織で自分で予約をオンまたはオフにする

PowerShell を使用して次のコマンドExchange Online実行する必要があります。 Exchange Online コマンドレットの実行の詳細については、「[PowerShell への接続Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。 PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) を使用して組織の Bookings をオンまたはオフにするには、[PowerShell Exchange Onlineに接続](/powershell/exchange/connect-to-exchange-online-powershell)し、次のコマンドを実行します。

**Get-OrganizationConfig** コマンドと **Set-OrganizationConfig** コマンドを使用して、組織の状態を確認し、自分で Bookings をオンまたはオフにします。

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

    - 組織の Bookings を無効にするには、次のコマンドを実行して **EwsAllowList** から **MicrosoftOWSPersonalBookings** (存在する場合) を削除します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - 組織で Bookings を有効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EwsAllowList** に追加します。  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。

    - 組織で Bookings を無効にするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - ブロックされている場合に Bookings を有効にするには、次のコマンドを実行して **MicrosoftOWSPersonalBookings** を削除します。

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. **EwsApplicationAccessPolicy** の値が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - 組織の Bookings を無効にするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し、 **MicrosoftOWSPersonalBookings** をブロック リストに追加します。

   ```PowerShell
   Set-OrganizationConfig -EwsApplicationAccessPolicy EnforceBlockList -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
   
  > [!NOTE]
  > EwsApplicationAccessPolicy パラメーターは、Entourage、Outlook、Outlook for Mac以外のどのアプリケーションが EWS にアクセスできるかを定義します。

### <a name="turn-bookings-with-me-off-or-on-for-individual-users"></a>個々のユーザーに対して、自分で予約をオフまたはオンにする

**Get-CASMailbox** コマンドと **Set-CASMailbox** コマンドを使用して、ユーザーの状態を確認し、組織内の個々のユーザーに対して自分で Bookings をオンまたはオフにします。

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

    - このユーザーの Bookings を無効にするには、次のコマンドを実行して **EwsAllowList** から **MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーの Bookings を有効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EwsAllowList** に追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. **EwsApplicationAccessPolicy** の値が **EnforceBlockList** の場合、**EwsBlockList** に指定されているものを除くすべてのアプリケーションに EWS と REST へのアクセスが許可されます。  

    - このユーザーの Bookings を無効にするには、次のコマンドを実行して **、MicrosoftOWSPersonalBookings** を **EnforceBlockList** に追加します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - このユーザーに対して Bookings を有効にするには、次のコマンドを実行して、EnforceBlockList から **MicrosoftOWSPersonalBookings** が存在する場合は削除します。

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. EwsApplicationAccessPolicy の値が空の場合、すべてのアプリケーションは EWS と REST にアクセスできます。

    - このユーザーの Bookings を無効にするには、次のコマンドを実行して **、EnforceBlockList** ポリシーを設定し **、MicrosoftOWSPersonalBookings** を EWSBlockList に追加します。

    ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsApplicationAccessPolicy EnforceBlockList -EWSBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-is-the-difference-between-bookings-and-bookings-with-me"></a>Bookings と Bookings の違いは何ですか?

自分との予約は Outlook 予定表と統合され、1 対 1 の会議にのみ使用できます。 私との予約は、個々のユーザーとの会議時間をスケジュールすることを目的としています。 予約は、ユーザーのグループのスケジュール設定を管理することを目的としています。

また、自分と一緒の Bookings では、自分のページを含む各 Bookings の新しいメールボックスは作成されません。

### <a name="why-is-bookings-with-me-in-preview"></a>Bookings と共にプレビューを行う理由

私との予約は、世界中のすべてのエンタープライズ ユーザー向けにプレビュー段階です。 Bookings と Outlook のスケジュール設定エクスペリエンスに統合されている間、フィードバックを収集し、改善を行っています。  

### <a name="who-can-access-my-public-bookings-page"></a>誰が自分のパブリック Bookings ページにアクセスできますか?

公開会議の種類は、自分のページ アドレスを持つ Bookings を持つすべてのユーザーがアクセスできます。 自分の予約を自分のページ アドレスと共有するユーザーを決定します。

### <a name="what-is-the-difference-between-public-and-private-meeting-types"></a>パブリック会議とプライベート会議の種類の違いは何ですか?

会議の種類は、パブリックでもプライベートでもかまいません。 パブリック会議の種類は、Bookings ページのリンクを共有するすべてのユーザーが利用できます。 プライベート会議の種類は、個々のプライベート会議の種類を共有するユーザーのみが使用できます。  

プライベート会議の種類では、単一の使用リンクを生成することもできます。 シングル ユース リンクは、最初の予約後に期限切れになります。

### <a name="do-people-need-to-have-a-microsoft-account-or-bookings-license-to-schedule-time-with-me"></a>時間をスケジュールするには、Microsoft アカウントまたは Bookings ライセンスが必要ですか?

いいえ。 Microsoft アカウントを持っていない場合でも、誰でも自分の予約ページを使用して時間をスケジュールできます。 自分のページで Bookings を作成するには、Bookings ライセンスが必要です。

## <a name="privacy"></a>プライバシー

### <a name="where-is-bookings-with-me-data-stored"></a>Bookings と自分のデータはどこに保存されますか?

私との予約は、Bookings を搭載した Outlook の機能です。 すべてのデータは、Microsoft 365 プラットフォームと Exchange に格納されます。 予約は、Microsoft によって設定されたデータ ストレージ ポリシーに従います。これは、すべての Office アプリが従うのと同じポリシーです。 すべての顧客データ (予約時に出席者から提供された情報を含む) は、Bookings にキャプチャされ、Exchange 内に格納されます。 詳細については、「 [プライバシー: お客様のすべて](https://www.microsoft.com/en-us/trust-center/privacy)」を参照してください。
