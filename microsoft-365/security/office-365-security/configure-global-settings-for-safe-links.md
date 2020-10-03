---
title: Office 365 ATP で安全なリンク設定のグローバル設定を構成する
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
description: 管理者は、Office 365 Advanced Threat Protection (ATP) の「安全なリンク」のグローバル設定を表示および構成する方法について説明します (「Office 365 アプリの次の Url のリストと保護」を参照してください)。
ms.openlocfilehash: 50bef8a1edad50540c7212eb4259e17e2368a56c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350879"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a>Office 365 ATP で安全なリンクのグローバル設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の Safelinks に関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

「安全なリンク」とは、 [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) の機能の1つで、メールフローで受信電子メールメッセージの url スキャンを行い、電子メールメッセージやその他の場所で url とリンクの確認をクリックする時間を示します。 詳細については、「 [Office 365 ATP」の「安全なリンク](atp-safe-links.md)」を参照してください。

[安全なリンク] ポリシーで、ほとんどの安全なリンクの設定を構成します。 手順については、「 [Office 365 ATP で安全なリンクポリシーをセットアップ](set-up-atp-safe-links-policies.md)する」を参照してください。

しかし、安全なリンクは、アクティブな安全リンクポリシーに含まれるすべてのユーザーに適用されるグローバル設定も使用します。 これらのグローバル設定領域:

- [ **次の url をブロック** する] の一覧。 詳細については、 [「安全なリンク」の「次の url をブロックする」の一覧](atp-safe-links.md#block-the-following-urls-list-for-safe-links)を参照してください。
- Office 365 アプリの安全なリンク保護。 詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する資格のある Microsoft 365 組織の場合は Exchange Online PowerShell、exchange online メールボックスを使用しない組織の場合はスタンドアロン EOP PowerShell、Office 365 ATP アドオンサブスクリプション) で、グローバルな安全リンクの設定を構成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 「安全なリンク」のグローバル設定で提供される機能は、アクティブな安全リンクポリシーに含まれているユーザーにのみ適用されます。 組み込みまたは既定の安全なリンクポリシーはありません。そのため、これらのグローバル設定をアクティブにするには、少なくとも1つの安全なリンクポリシーを作成する必要があります。 手順については、「 [Office 365 ATP で安全なリンクポリシーをセットアップ](set-up-atp-safe-links-policies.md)する」を参照してください。

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な **リンク** ] ページに直接移動するには、を使用 <https://protection.office.com/safelinksv2> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 安全なリンクのためのグローバル設定を表示および構成するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**。

- 「安全なリンク」の「グローバル設定」に推奨される値については、「 [安全なリンクの設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)」を参照してください。

- 新規または更新されたポリシーが適用されるまで最大30分かかります。

- [新機能は ATP に継続的に追加](office-365-atp.md#new-features-in-office-365-atp)されています。 新機能が追加されたときに、既存の安全なリンクポリシーを調整する必要がある場合があります。

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの [次の Url をブロックする] の一覧を構成する

[ **次の url をブロック** する] リストは、サポートされているアプリでの安全なリンクスキャンによって常にブロックされるリンクを示しています。 詳細については、 [「安全なリンク」の「次の url をブロックする」の一覧](atp-safe-links.md#block-the-following-urls-list-for-safe-links)を参照してください。

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動し、[ **グローバル設定**] をクリックします。

2. [ **組織の安全なリンク] ポリシー** が表示されたら、[ **次の url をブロック** する] ボックスに移動します。

3. [「次の url をブロックする」リストの「Entry 構文](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)」に記載されている1つ以上のエントリを構成します。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で [次の Url をブロックする] の一覧を構成する

エントリの構文の詳細については、 [「次の url をブロックする」のリストの「エントリの構文」](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)を参照してください。

**AtpPolicyForO365**コマンドレットを使用して、 _blockurls_プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、Exchange Online PowerShell または Exchange Online Protection の PowerShell で次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  この例では、次のエントリをリストに追加します。

  - Fabrikam.com のドメイン、サブドメイン、およびパスをブロックします。
  - サブドメインの調査をブロックするが、tailspintoys.com で親ドメインまたは他のサブドメインをブロックする

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  次の使用例は、adatum.com の新しいエントリを追加し、fabrikam.com のエントリを削除します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで Office 365 アプリの安全なリンク保護を構成する

安全なリンク保護 Office 365 アプリは、サポート対象の Office デスクトップ、モバイル、および web アプリのドキュメントに適用されます。 詳細については、「 [Office 365 アプリの安全なリンク設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)」を参照してください。

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動し、[ **グローバル設定**] をクリックします。

2. [ **組織の安全なリンク] ポリシー** が表示されたら、[ **電子メール以外のコンテンツに適用する設定** ] で、次の設定を構成します。

   - **Office 365 アプリケーション**: サポートされている office 365 アプリの安全なリンクを有効にするには、[切り替え] が [オン] になっていることを確認します。 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

   - **ユーザーが [安全なリンク] をクリックしたときに追跡しない**: サポートされている Office 365 アプリでブロックされる url に関連するユーザークリックを追跡するには、トグルをオフにします。 ![ ](../../media/scc-toggle-off.png)

   - **ユーザーが元の URL に安全なリンクをクリックできない**ようにします。 [トグル] が [サポートされている Office 365 アプリの元のブロックする url] をクリックすると、[オン] に切り替えられないようにします。 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

   完了したら、**[保存]** をクリックします。

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>PowerShell で Office 365 アプリの安全なリンク保護を構成する

PowerShell を使用して Office 365 アプリの安全なリンク保護を構成する場合は、Exchange Online PowerShell または Exchange Online Protection の PowerShell で次の構文を使用します。

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

この例では、Office 365 アプリの安全なリンク保護について次の設定を構成します。

- Office 365 アプリの安全なリンクが有効になっています ( _EnableSafeLinksForO365Clients_ パラメーターは使用しておらず、既定値は $true)。
- サポートされている Office 365 でブロックされている Url に関連するユーザークリックが追跡されます。
- サポートされている Office 365 アプリの元のブロックされた URL をクリックすることはできません ( _allowclickthrough クリックスルー_ パラメーターは使用しておらず、既定値は $false)。

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全なリンクのグローバル設定が正常に構成されたことを確認するには ([ **次の url をブロック** する] と [Office 365 app protection] の設定)、次のいずれかの手順を実行します。

- セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動し、[ **グローバル設定**] をクリックして、画面上に表示される設定を確認します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)」を参照してください。
