---
title: Defender for Office 365 の安全なリンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 の安全なリンクに関するグローバル設定 ([次の URL をブロックする] リストと Office 365 アプリの保護) を表示および構成する方法について説明します。
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682908"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全なリンクのグローバル設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。 If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

「安全なリンク」は [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信メール メッセージの URL スキャンや、電子メール メッセージや他の場所での URL とリンクのクリック検証の時間を提供します。 詳細については [、Microsoft Defender の 「安全なリンク」を参照してください。Office 365](atp-safe-links.md).

ほとんどの安全なリンクの設定は、安全なリンク ポリシーで構成します。 手順については、「Microsoft Defender で安全なリンク ポリシーをセットアップする(Office [365)」を参照](set-up-atp-safe-links-policies.md)してください。

ただし、安全なリンクは、アクティブな安全なリンク ポリシーに含まれるすべてのユーザーに適用されるグローバル設定も使用します。 次のグローバル設定領域:

- [ **次の URL をブロックする] の一覧** 。 詳細については、「安全なリンク」の「次の [URL をブロックする」を参照してください。](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- 365 アプリの安全Office保護。 詳細については、「365 アプリの安全なリンク [設定Office参照してください](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプションの場合) では、グローバルな安全なリンク設定を構成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 安全なリンクのグローバル設定によって提供される機能は、アクティブな安全なリンク ポリシーに含まれているユーザーにのみ適用されます。 組み込みまたは既定の安全なリンク ポリシーはないので、これらのグローバル設定をアクティブ化するには、少なくとも 1 つの安全なリンク ポリシーを作成する必要があります。 手順については、「Microsoft Defender で安全なリンク ポリシーをセットアップする(Office [365)」を参照](set-up-atp-safe-links-policies.md)してください。

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [安全なリンク] ページ **に直接移動するには** 、次の値を使用します <https://protection.office.com/safelinksv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - 安全なリンクのグローバル設定を構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - 安全なリンクのグローバル設定に読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 安全なリンクのグローバル設定の推奨値については、「安全なリンクの設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新しい機能は、Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加されています。 新機能が追加された場合は、既存の安全なリンク ポリシーの調整が必要な場合があります。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターの [次の URL をブロックする] &構成します。

[ **次の URL をブロック** する] リストは、サポートされているアプリの安全なリンク スキャンによって常にブロックする必要があるリンクを示します。 詳細については、「安全なリンク」の「次の URL を [ブロックする」を参照してください](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。

1. セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全なリンクに移動し、[グローバル設定] \>  \> を **クリックします**。

2. 表示される **組織の安全なリンク** ポリシーで、[次の URL をブロックする] **ボックスに移動** します。

3. 「次の URL をブロックする」の一覧のエントリ構文の説明に従って、1 つ以上の [エントリを構成します](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で "次の URL をブロックする" リストを構成する

エントリ構文の詳細については、「次の URL をブロックする」の一覧 [のエントリ構文を参照してください](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

**Get-AtpPolicyForO365** コマンドレットを使用すると _、BlockURLs_ プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  次の使用例は、次のエントリをリストに追加します。

  - ドメイン、サブドメイン、およびドメインのパスをブロックfabrikam.com。
  - サブドメインの調査をブロックしますが、サブドメイン内の親ドメインや他のサブドメインはtailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  次の使用例は、新しいadatum.comを追加し、そのエントリを削除fabrikam.com。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで Office 365 アプリの安全なリンク保護&構成する

Office 365 アプリの安全なリンク保護は、サポートされているデスクトップ、モバイル、および web アプリOfficeドキュメントに適用されます。 詳細については、「365 アプリの安全なリンク [設定Office参照してください](atp-safe-links.md#safe-links-settings-for-office-365-apps)。

1. セキュリティ/コンプライアンス センター&、**脅威管理** ポリシー ATP の安全なリンクに移動し、[グローバル設定] \>  \> を **クリックします**。

2. 表示される **組織の安全な** リンク ポリシーで、[メール以外のコンテンツに適用される設定] セクションで次の **設定を構成** します。

   - **Office 365** アプリケーション: トグルが右側に表示され、サポートされている Office 365 アプリの安全なリンクを有効にしてください。オンに切り替 ![ え ](../../media/scc-toggle-on.png) 。

   - **Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: Toggle off ![ ](../../media/scc-toggle-off.png) .

   - **元** の URL への安全なリンクをユーザーがクリックで許可しない: トグルが右側に表示され、ユーザーがサポートされている Office 365 アプリの元のブロックされた URL をクリックしてクリックを防ぐことを確認します。オンに切り替え ![ ](../../media/scc-toggle-on.png) 。

   完了したら、**[保存]** をクリックします。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell で 365 Officeの安全なリンク保護を構成する

PowerShell を使用して Office 365 アプリの安全なリンク保護を構成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell で次の構文を使用します。

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

この例では、365 アプリの安全なリンク保護に関する次Office設定を構成します。

- Office 365 アプリの安全なリンクが有効になっています _(EnableSafeLinksForO365Clients_ パラメーターは使用していないので、既定値は $true)。
- サポートされている 365 アプリのブロックされた URL にOfficeクリックが追跡されます。
- ユーザーは、サポートされている Office 365 アプリで元のブロックされた URL をクリックしてクリックすることはできません _(AllowClickThrough_ パラメーターは使用しません。既定値は $false)。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全なリンクのグローバル設定 ([次の **URL** をブロックする] リストと Office 365 アプリ保護設定) が正常に構成されたことを確認するには、次の手順を実行します。

- セキュリティ & コンプライアンス センターで、脅威 **管理** ポリシー ATP の安全なリンクに移動し、[グローバル設定] をクリックして、表示されるフライアウトの設定 \>  \> を確認します。 

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文およびパラメーターの詳細については [、Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)を参照してください。
