---
title: Defender for Office 365 のセーフ リンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 のセーフ リンクのグローバル設定 ([次の URL をブロックする] リストと Office 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065380"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>365 用 Microsoft Defender のセーフ リンクのグローバルOffice構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlook で Safelinks に関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

セーフ リンクは [、Microsoft Defender for Office 365](defender-for-office-365.md) の機能で、メール フロー内の受信電子メール メッセージの URL スキャンと、電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。 詳細については [、「Safe Links in Microsoft Defender for microsoft Defender for Office 365」を参照してください](safe-links.md)。

セーフ リンク ポリシーでは、ほとんどのセーフ リンク設定を構成します。 手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-safe-links-policies.md)。

ただし、セーフ リンクは、アクティブなセーフ リンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定も使用します。 次のグローバル設定領域:

- [ **次の URL をブロックする] リスト** 。 詳細については、「安全なリンク [」の「次の URL をブロックする」リストを参照してください。](safe-links.md#block-the-following-urls-list-for-safe-links)
- 365 のアプリOfficeリンク保護。 詳細については、「セーフ リンクの [設定」を参照Office 365 アプリを参照してください](safe-links.md#safe-links-settings-for-office-365-apps)。

グローバルセーフ リンクの設定は、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象となる Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織ではスタンドアロンの EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプション)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- セーフ リンクのグローバル設定によって提供される機能は、アクティブなセーフ リンク ポリシーに含まれるユーザーにのみ適用されます。 組み込みまたは既定のセーフ リンク ポリシーはないので、これらのグローバル設定をアクティブにするには、少なくとも 1 つのセーフ リンク ポリシーを作成する必要があります。 手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-safe-links-policies.md)。

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [安全なリンク] ページに **直接移動するには** 、 を使用します <https://protection.office.com/safelinksv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - セーフ リンクのグローバル設定を構成するには、組織の管理またはセキュリティ管理者の役割グループの **メンバーである** 必要があります。
  - セーフ リンクのグローバル設定への読み取り専用アクセスには、グローバル リーダーまたはセキュリティリーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- セーフ リンクのグローバル設定の推奨値については、「セーフ リンクの設定 [」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新しい機能は、Microsoft Defender に継続的に 365 Officeされています](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新しい機能が追加された場合、既存のセーフ リンク ポリシーを調整する必要がある場合があります。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターで [次の URL をブロックする] &構成する

[ **次の URL をブロックする** ] リストは、サポートされているアプリのセーフ リンク スキャンによって常にブロックする必要があるリンクを識別します。 詳細については、「安全なリンク」の「次の URL をブロックする [」リストを参照してください](safe-links.md#block-the-following-urls-list-for-safe-links)。

1. セキュリティ コンプライアンス センターで&管理ポリシー ATPセーフ リンクに移動し、[グローバル \>  \> 設定]**をクリックします**。

2. 組織の **セーフ リンク ポリシーが表示されたら** 、[次の URL をブロックする] **ボックスに移動** します。

3. 「次の URL をブロックする」リストのエントリ構文の説明に従って、1 つ以上の [エントリを構成します](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で "次の URL をブロックする" リストを構成する

エントリの構文の詳細については、「次の URL をブロックする」リストの [エントリ構文を参照してください](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  次の使用例は、次のエントリをリストに追加します。

  - ドメイン、サブドメイン、およびパスをブロック fabrikam.com。
  - サブドメインの調査をブロックしますが、親ドメインや他のサブドメインはブロック tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  次の使用例は、adatum.com の新しいエントリを追加し、そのエントリを fabrikam.com。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターで 365 Officeアプリの安全なリンク保護&構成する

365 のアプリOfficeの安全なリンク保護は、サポートされているデスクトップ、モバイル、および web アプリOfficeドキュメントに適用されます。 詳細については、「セーフ リンクの [設定」を参照Office 365 アプリを参照してください](safe-links.md#safe-links-settings-for-office-365-apps)。

1. セキュリティ コンプライアンス センターで&管理ポリシー ATPセーフ リンクに移動し、[グローバル \>  \> 設定]**をクリックします**。

2. 組織の **セーフ リンク ポリシー** が表示されたら、[メール以外のコンテンツに適用される設定] セクションで次の **設定を構成** します。

   - **Office 365** アプリケーション: サポートされている 365 アプリの安全なリンクを有効にするには、トグルが右側 ![ Office確認してください。 ](../../media/scc-toggle-on.png)

   - **ユーザー** が [安全なリンク] をクリックしても追跡しない: トグルを左に移動して、サポートされている Office 365 アプリのブロックされた URL に関連するユーザーのクリックを追跡します。トグルを ![ オフにします ](../../media/scc-toggle-off.png) 。

   - **ユーザー** が元の URL への安全なリンクをクリックさせない: トグルが右にあることを確認して、ユーザーがサポートされている Office 365 アプリの元のブロックされた URL をクリックできない状態にします。トグルをオンにします。 ![ ](../../media/scc-toggle-on.png)

   完了したら、**[保存]** をクリックします。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell で 365 のアプリOfficeリンク保護を構成する

PowerShell を使用して Office 365 アプリのセーフ リンク保護を構成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

この例では、365 アプリのセーフ リンク保護のOffice構成します。

- 365 Office アプリの安全なリンクが有効になっています _(EnableSafeLinksForO365Clients_ パラメーターは使用していないので、既定値は$true)。
- 365 アプリのサポートされている URL に関連するユーザー Officeクリックが追跡されます。
- ユーザーは、サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません _(AllowClickThrough_ パラメーターは使用していないので、既定値は $false)。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

セーフ リンクのグローバル設定 ([次の **URL** をブロックする] リストと Office 365 アプリ保護設定) が正常に構成されたことを確認するには、次の手順を実行します。

- [セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー ATP セーフ リンク] に移動し、[グローバル設定] をクリックして、表示されるフライアウトの設定 \>  \> を確認します。 

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。