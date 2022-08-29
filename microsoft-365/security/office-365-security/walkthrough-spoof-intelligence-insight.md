---
title: スプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス 分析情報を使用してスプーフィングされた送信者を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス分析情報を使用して、検出されたスプーフィングされた送信者を許可またはブロックする方法を学習できます。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e9cb7fc02a3e84f7fa0909e509f47c21b63050ab
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384860"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>EOP でスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス 分析情報を使用してスプーフィングされた送信者を管理する

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Microsoft 365 Defender ポータルでのスプーフィング送信者管理は、テナント許可/ブロック リストの **[スプーフィングされた送信者**] タブでのみ使用できるようになりました。 Microsoft 365 Defender ポータルの現在の手順については、「[EOP でのスプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)」を参照してください。
>
> Exchange Online PowerShell またはスタンドアロン EOP PowerShell のスプーフィングされた送信者管理は、関連する **\*-TenantAllowBlockListSpoofItems**、**Get-SpoofIntelligenceInsight**、**Get-SpoofMailReport** コマンドレットにのみ移行中です。 これらのコマンドレットを使用する手順については、次の記事を参照してください。
>
> - [PowerShell を使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリまたはブロック エントリを表示する](allow-block-email-spoof.md#use-powershell-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [PowerShell を使用してスプーフィングされた送信者の許可エントリを作成する](allow-block-email-spoof.md#use-powershell-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [PowerShell を使用してスプーフィングされた送信者のブロック エントリを作成する](allow-block-email-spoof.md#use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [PowerShell を使用して、テナント許可/ブロックリストのスプーフィングされた送信者の許可エントリまたはブロック エントリを変更する](allow-block-email-spoof.md#use-powershell-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [PowerShell を使用して、テナント許可/ブロック リストからスプーフィングされた送信者の許可エントリまたはブロック エントリを削除する](allow-block-email-spoof.md#use-powershell-to-remove-allow-or-block-entries-for-spoofed-senders-from-the-tenant-allowblock-list)
>
> **Get-PhishFilterPolicy** コマンドレットと **Set-PhishFilterPolicy** コマンドレットを使用した古いスプーフィングされた送信者管理エクスペリエンスは非推奨のプロセスにありますが、コマンドレットがすべての場所で削除されるまで、この記事では完全さを示しています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、次のメンバーである必要があります。
    - **組織の管理**
    - **セキュリティ管理者**<u>と</u>**表示専用構成** または **表示専用組織管理**。
  - スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- スプーフィング インテリジェンスのオプションについては、「 [フィッシング対策ポリシーのスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

- フィッシング対策ポリシーでは、スプーフィング インテリジェンス設定を有効、無効、および構成できます。 サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。

  - [EOP でフィッシング対策ポリシーを構成します](configure-anti-phishing-policies-eop.md)。
  - [Microsoft Defender for Office 365でフィッシング対策ポリシーを構成](configure-mdo-anti-phishing-policies.md)します。

- スプーフィング インテリジェンスの推奨設定については、「 [EOP フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)」を参照してください。

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用してスプーフィングされた送信者を管理する

許可された送信者とブロックされた送信者をスプーフィング インテリジェンスで表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーのスプーフィングが許可されているすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文とパラメーターの詳細については、「 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy)」を参照してください。

スプーフィング インテリジェンスで許可およびブロックされた送信者を構成するには、次の手順に従います。

1. **Get-PhishFilterPolicy** コマンドレットの出力を CSV ファイルに書き込み、次のコマンドを実行して、検出されたスプーフィングされた送信者の現在の一覧をキャプチャします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して、次の値を追加または変更します。
   - **送信者** (ソース サーバーの PTR レコードのドメイン、IP/24 アドレス、または検証済みの DKIM ドメイン)
   - **スプーフィングユーザー**: 次のいずれかの値。
     - 内部ユーザーの電子メール アドレス。
     - 外部ユーザーの電子メール ドメイン。
     - スプーフィングされた電子メール アドレスに関係なく、指定した **送信者** からのスプーフィングされたメッセージをブロックまたは許可することを示す空白の値。
   - **AllowedToSpoof** (はいまたはいいえ)
   - **SpoofType** (内部または外部)

   次のコマンドを実行して、ファイルを保存し、ファイルを読み取り、内容を名前付きの `$UpdateSpoofedSenders` 変数として格納します。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 次のコマンドを `$UpdateSpoofedSenders` 実行して、変数を使用してスプーフィング インテリジェンス ポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文とパラメーターの詳細については、「 [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スプーフィングが許可され、スプーフィングが許可されていない送信者でスプーフィング インテリジェンスを構成したことを確認するには、PowerShell で次のコマンドを実行して、スプーフィングが許可され、スプーフィングが許可されていない送信者を表示します。

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell で、次のコマンドを実行して、スプーフィングされたすべての送信者の一覧を CSV ファイルにエクスポートします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
