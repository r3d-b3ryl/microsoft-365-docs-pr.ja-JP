---
title: Defender for Office 365でセーフ リンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Microsoft Defender for Office 365の セーフ リンクのグローバル設定 ([次の URL をブロックする] の一覧とOffice 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 857519e93df9490ebeb178a23a44ddddbdfc83ef
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61932597"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365で セーフ リンクのグローバル設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlookで Safelinks に関する情報を探しているホーム ユーザーの場合は、「[Advanced Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

セーフ リンクは[、メール](defender-for-office-365.md) フロー内の受信電子メール メッセージの URL スキャンと、電子メール メッセージやその他の場所での URL とリンクのクリック確認の時間を提供する、Microsoft Defender for Office 365の機能です。 詳細については、「[Microsoft Defender for Office 365のリンクのセーフ](safe-links.md)」を参照してください。

ほとんどのセーフリンク設定は、セーフ リンク ポリシーで構成します。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

ただし、セーフ リンクでは、セーフ リンク ポリシー自体の外部で構成する次のグローバル設定も使用されます。

- [ **次の URL をブロックする]** の一覧。 この設定は、アクティブな セーフ リンク ポリシーに含まれるすべてのユーザーに適用されます。 詳細については、[セーフ リンクの「次の URL をブロックする」の一覧を](safe-links.md#block-the-following-urls-list-for-safe-links)参照してください。
- Office 365 アプリのリンク保護をセーフします。 これらの設定は、ユーザーがアクティブなセーフリンク ポリシーに含まれているかどうかに関係なく、Defender for Office 365のライセンスを持つ組織内のすべてのユーザーに適用されます。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

グローバル セーフ リンクの設定は、Microsoft 365 Defender ポータルまたは PowerShell で構成できます (Exchange Online PowerShell は、Exchange Onlineのメールボックスを持つ適格なMicrosoft 365組織の場合は PowerShell、スタンドアロン EOP PowerShell は組織なしメールボックスをExchange Onlineしますが、アドオン サブスクリプションMicrosoft Defender for Office 365)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 既定のセーフ リンク ポリシーはありませんが、**組み込みの保護** プリセット セキュリティ ポリシーでは、すべての受信者 (カスタム セーフ リンク ポリシーで定義されていないユーザー) に対してセーフリンク保護が提供されます。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。 セーフ リンク ポリシーを作成して、特定のユーザー、グループ、またはドメインに適用することもできます。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[セーフ リンク**] ページに直接移動するには、<https://security.microsoft.com/safelinksv2>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - セーフ リンクのグローバル設定を構成するには、**組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - セーフ リンクのグローバル設定に対する読み取り専用アクセス権を持つ場合は、**グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- セーフ リンクのグローバル設定に推奨される値については、「[セーフ リンクの設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)」を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新機能はMicrosoft Defender for Office 365に継続的に追加されています](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新機能が追加されると、既存のセーフ リンク ポリシーを調整することが必要になる場合があります。

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで [次の URL をブロックする] 一覧を構成する

[**次の URL をブロックする]** ボックスの一覧では、サポートされているアプリでセーフリンク スキャンを行って、常にブロックする必要があるリンクを特定します。 詳細については、[セーフ リンクの「次の URL をブロックする」の一覧を](safe-links.md#block-the-following-urls-list-for-safe-links)参照してください。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[セーフ リンク**] ページに直接移動するには、<https://security.microsoft.com/safelinksv2>.

2. **[セーフ リンク**] ページで、[**グローバル設定**] をクリックします。 表示される **組織の [セーフ リンク] ポリシー** が表示されたら、[**次の URL をブロック** する] ボックスに移動します。

3. ["次の URL をブロックする" 一覧のエントリ構文](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)で説明されているように、1 つ以上のエントリを構成します。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で "次の URL をブロックする" 一覧を構成する

エントリ構文の詳細については、「 [次の URL をブロックする」の一覧のエントリ構文を参照してください](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、PowerShell または powerShell のExchange Online Protection Exchange Online次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  この例では、次のエントリを一覧に追加します。

  - fabrikam.com のドメイン、サブドメイン、パスをブロックします。
  - サブドメインの調査をブロックしますが、tailspintoys.com の親ドメインやその他のサブドメインはブロックしません

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 他の既存のエントリに影響を与えずに値を追加または削除するには、次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  この例では、adatum.com の新しいエントリを追加し、fabrikam.com のエントリを削除します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでOffice 365 アプリのセーフ リンク保護を構成する

Office 365 アプリのセーフ リンク保護は、サポートされているOfficeデスクトップ アプリ、モバイル アプリ、および Web アプリのドキュメントに適用されます。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[セーフ リンク**] ページに直接移動するには、<https://security.microsoft.com/safelinksv2>.

2. **[セーフ リンク**] ページで、[**グローバル設定**] をクリックします。 表示される **組織の [セーフ リンク] ポリシー** が表示されたら、[**サポートされているOffice 365 アプリ] セクションのコンテンツに適用される設定で次の設定を** 構成します。

   - **Office 365 アプリで セーフ リンクを使用** する: トグルが右側にあり、サポートされているOffice 365 アプリのセーフ リンクを有効にする場合![は右に切り替えます](../../media/scc-toggle-on.png)。

   - **ユーザーがOffice 365 アプリで保護されたリンクをクリックしたタイミングを追跡しない**: トグルを左に移動して、サポートされているOffice 365 アプリのブロックされた URL に関連するユーザーのクリックを追跡します。 ![](../../media/scc-toggle-off.png)

   - **ユーザーがOffice 365 アプリで元の URL をクリック** できないようにする:ユーザーがサポートされているOffice 365 アプリで元のブロックされた URL をクリックできないようにするには、トグルが右側であることを確認します。![トグルオンにします](../../media/scc-toggle-on.png)。

   完了したら、**[保存]** をクリックします。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell で Office 365 アプリのセーフ リンク保護を構成する

PowerShell を使用してOffice 365 アプリのセーフリンク保護を構成する場合は、powerShell または powerShell Exchange Online Protection Exchange Online次の構文を使用します。

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

この例では、Office 365 アプリの セーフ リンク保護に対して次の設定を構成します。

- Office 365 アプリのセーフ リンクが有効になっています (_EnableSafeLinksForO365Clients_ パラメーターは使用されておらず、既定値は$true)。
- サポートされているOffice 365 アプリのブロックされた URL に関連するユーザークリックが追跡されます。
- ユーザーは、サポートされているOffice 365 アプリで元のブロックされた URL をクリックすることはできません (_AllowClickThrough_ パラメーターは使用されておらず、既定値は$false)。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

構文とパラメーターの詳細については、「 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

セーフ リンクのグローバル設定 (**[次の URL のブロック**] 一覧とOffice 365アプリ保護設定) が正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの **[セーフ リンク**] ページで<https://security.microsoft.com/safelinksv2>、[**グローバル設定**] をクリックし、表示されるポップアップで設定を確認します。

- powerShell または powerShell Exchange Online Protection Exchange Onlineで、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文とパラメーターの詳細については、「 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)」を参照してください。
