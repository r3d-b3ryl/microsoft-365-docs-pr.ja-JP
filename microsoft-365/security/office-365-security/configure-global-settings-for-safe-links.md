---
title: Defender の [リンク] セーフのグローバル設定を構成Office 365
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
description: 管理者は、Microsoft Defender for Office 365 の セーフ リンクのグローバル設定 ([次の URL をブロックする] リストと Office 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 099ff894cc350ecedbd7743ab348aede540874ab
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219823"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender の [リンク] セーフのグローバル設定を構成するOffice 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 セーフリンクに関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

セーフ[リンクは、Microsoft Defender for Office 365](defender-for-office-365.md)の機能で、メール フロー内の受信電子メール メッセージの URL スキャン、および電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。 詳細については[、「Microsoft Defender セーフリンク」を参照Office 365。](safe-links.md)

[リンク] ポリシーでセーフリンクの設定セーフ構成します。 手順については、「Microsoft Defender for セーフのリンク ポリシーをセットアップする[」を参照Office 365。](set-up-safe-links-policies.md)

ただし、セーフリンクは、リンク ポリシー自体の外部で構成する次セーフ設定も使用します。

- [ **次の URL をブロックする] リスト** 。 この設定は、アクティブなリンク ポリシーに含まれるすべてのセーフ適用されます。 詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください。](safe-links.md#block-the-following-urls-list-for-safe-links)
- セーフアプリのリンク保護Office 365します。 これらの設定は、ユーザーがアクティブな セーフ リンク ポリシーに含まれているかどうかに関係なく、Office 365 の Defender のライセンスを取得している組織内のすべてのユーザーに適用されます。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Office 365 アドオン サブスクリプションの場合は Microsoft Defender を使用) でグローバル セーフ リンク設定を構成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 組み込みまたは既定の セーフ リンク ポリシーはないので、[次の URL をブロックする] リストをアクティブにするには、少なくとも 1 つの セーフ リンク ポリシーを作成する必要があります。 手順については、「Microsoft Defender for セーフのリンク ポリシーをセットアップする[」を参照Office 365。](set-up-safe-links-policies.md)

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [リンク] ページに直接 **移動セーフを** 使用します <https://security.microsoft.com/safelinksv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - リンクのグローバル設定を構成セーフ、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。 
  - リンクのグローバル設定への読み取り専用アクセスセーフ、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である必要があります**。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- リンクのグローバル設定の推奨値については、「セーフリンクのセーフ[を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新しい機能は、Microsoft Defender](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加Office 365。 新しい機能が追加された場合、既存のリンク ポリシーを調整するセーフがあります。

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>ポータルで "次の URL をブロックする" リストをMicrosoft 365 Defenderする

[**次の URL をブロックする**] ボックスの一覧は、サポートされているアプリの [リンクセーフによって常にブロックする必要があるリンクを識別します。 詳細については、「リンク」の「次の URL をブロックする[」をセーフしてください](safe-links.md#block-the-following-urls-list-for-safe-links)。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーとリンクセーフメールを送信する] \>  \>  \> **に移動** します。

2. [リンクの **セーフ] ページで**、[グローバル設定]**をクリックします**。 組織の **セーフが表示されたら、[** 次の URL をブロックする]**ボックスに移動** します。

3. 「次の URL をブロックする」リストのエントリ構文の説明に従って、1 つ以上の [エントリを構成します](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で "次の URL をブロックする" リストを構成する

エントリの構文の詳細については、「次の URL をブロックする」リストの [エントリ構文を参照してください](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、PowerShell または PowerShell でExchange Online構文Exchange Online Protectionします。

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>ポータルセーフアプリのOffice 365リンク保護をMicrosoft 365 Defenderする

セーフデスクトップ アプリ、モバイル Office 365 Web アプリでサポートされているドキュメントOfficeリンク保護が適用されます。 詳細については、「[Office 365 アプリ向けの安全なリンク設定](safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーとリンクセーフメールを送信する] \>  \>  \> **に移動** します。

2. [リンクの **セーフ] ページで**、[グローバル設定]**をクリックします**。 組織の **セーフリンク** ポリシーが表示されたら、[サポートされているアプリ] セクションのコンテンツに適用される 設定 で次の **設定Office 365構成** します。

   - **[セーフ** アプリOffice 365リンクを使用する: トグルが右に表示され、サポートされている セーフ アプリの Office 365 リンクが有効Office 365確認します。 ![ ](../../media/scc-toggle-on.png)

   - **ユーザー** が Office 365 アプリで保護されたリンクをクリックした場合は追跡しない: トグルを左に移動して、サポートされている Office 365 アプリのブロックされた URL に関連するユーザークリックを追跡します。トグルをオフにします。 ![ ](../../media/scc-toggle-off.png)

   - **ユーザー** が Office 365 アプリの元の URL をクリックさせない: トグルが右に表示され、サポートされている Office 365 アプリの元のブロックされた URL にユーザーがクリックスルーされるのを防ぐことを確認します。[オンに切り替える] をクリックします。 ![ ](../../media/scc-toggle-on.png)

   完了したら、**[保存]** をクリックします。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell セーフアプリのリンク保護Office 365構成する

powerShell を使用して Office 365 アプリの セーフ リンク保護を構成する場合は、Exchange Online PowerShell または PowerShell で次Exchange Online Protectionします。

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

この例では、アプリ内のリンク保護セーフ設定をOffice 365します。

- セーフアプリのOffice 365がオンになっています _(EnableSafeLinksForO365Clients_ パラメーターは使用していないので、既定値は有効$true)。
- サポートされているアプリのブロックされた URL に関連Office 365クリックが追跡されます。
- ユーザーは、サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません _(AllowClickThrough_ パラメーターは使用していないので、既定値は $false)。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

構文とパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](/powershell/module/exchange/set-atppolicyforo365)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

セーフ リンクのグローバル設定が正常に構成されたことを確認するには ([次のURL リストと Office 365 アプリ保護設定をブロックする] をクリックして、次の手順を実行します。

- Microsoft 365 Defender ポータルで、[ポリシー] セクションの[& Collaboration \> **Policies & Rules** Threat \> **Policies** セーフ \> **Links]** \> に移動し、[グローバル設定] をクリックし、表示されるフライアウトの設定を確認します。

- PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文とパラメーターの詳細については [、「Get-AtpPolicyForO365」を参照してください](/powershell/module/exchange/get-atppolicyforo365)。
