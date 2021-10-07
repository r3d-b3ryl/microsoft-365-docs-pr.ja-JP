---
title: 自動拡張アーカイブを有効にする - 管理者ヘルプ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '管理者向け: Exchange Online 自動拡張アーカイブを有効にする方法について説明します。 組織全体に対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 18123fb53cd13cf742c7b2a19574a540dded1f9b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158192"
---
# <a name="enable-auto-expanding-archiving---admin-help"></a>自動拡張アーカイブを有効にする - 管理者ヘルプ

自動拡張アーカイブ機能Exchange Onlineを使用して、アーカイブ メールボックスの追加の記憶域を有効にできます。 自動拡張アーカイブを有効にすると、ユーザーのアーカイブ メールボックスが 1.5 TB の記憶域制限に達するまで、追加の記憶域が自動的にユーザーのアーカイブ メールボックスに追加されます。 組織の全ユーザーに対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。 自動拡張アーカイブの詳細については、「自動拡張アーカイブの概要」 [を参照してください](autoexpanding-archiving.md)。

## <a name="before-you-enable-auto-expanding-archiving"></a>自動拡張アーカイブを有効にする前に

- 組織全体または特定のユーザーに対して自動拡張アーカイブを有効にするには、組織のグローバル管理者または Exchange Online 組織の組織管理役割グループのメンバーである必要があります。 または、特定のユーザーに対する自動拡張アーカイブを有効にするには、メール受信者の役割を割り当てられた役割グループのメンバーである必要があります。

- 自動拡張アーカイブを有効にする前に、ユーザーのアーカイブ メールボックスを有効にする必要があります。 アーカイブ メールボックスを有効にするには、ユーザーに Exchange Online プラン 2 のライセンスが割り当てられている必要があります。 ユーザーに Exchange Online プラン 1 のライセンスが割り当てられている場合、アーカイブ メールボックスを有効にするには、別の Exchange Online アーカイブ ライセンスを割り当てる必要があります。 「 [アーカイブ メールボックスを有効にする」を参照してください](enable-archive-mailboxes.md)。

- PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。 組織内のすべてのユーザーのアーカイブ メールボックスを有効するために使用できる PowerShell コマンドの例については、「[詳細情報](#more-information)」セクションを参照してください。

- アーカイブの自動拡張では、共有メールボックスもサポートされます。 共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。

- アーカイブを自動拡張すると、非アクティブなメールボックスを回復または復元 [できません](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes)。 つまり、メールボックスの自動拡張アーカイブを有効にし、後でメールボックスを非アクティブにした場合は、非アクティブな[メールボックスを回復](recover-an-inactive-mailbox.md)したり (アクティブなメールボックスに変換して) 復元したり (コンテンツを既存[](restore-an-inactive-mailbox.md)のメールボックスにマージして) 復元したりすることはできません。 非アクティブなメールボックスで自動拡張アーカイブが有効になっている場合、データを回復する唯一の方法は、Microsoft 365 コンプライアンス センター のコンテンツ検索ツールを使用して、メールボックスからデータをエクスポートし、別のメールボックスにインポートすることです。 詳細については、「非アクティブなメールボックスの概要」の「非アクティブなメールボックスと自動拡張アーカイブ」 [セクションを参照してください](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)。

- 管理センターまたは管理センター Exchangeを使用してMicrosoft 365 コンプライアンス センターアーカイブを有効にすることはできません。 Exchange Online PowerShell を使用する必要があります。 リモート PowerShell を使って Exchange Online 組織に接続する方法については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>自動拡張アーカイブを組織全体で有効にする

組織全体の自動拡張アーカイブを有効にすることができます。 いったん有効にすると、既存ユーザーのメールボックスと、作成される新規ユーザーのメールボックスに対し、自動拡張アーカイブが有効になります。 ユーザー メールボックスを作成するときは、自動拡張アーカイブ機能が新しいユーザー メールボックスで機能するように、ユーザーのメイン アーカイブ メールボックスを有効にする必要があります。
  
1. [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

2. 自動拡張アーカイブを組織全体で有効にするには、Exchange Online PowerShell で次のコマンドを実行します。

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>自動拡張アーカイブを特定のユーザーに対して有効にする

組織内のすべてのユーザーの自動拡張アーカイブを有効にするのではなく、特定のユーザーについてだけ有効にできます。 大容量のアーカイブ記憶領域の容量を必要とするのが一部のユーザーのみの場合に、この方法を使用します。
  
特定のユーザーと保持ポリシーに割り当てられているユーザーのメールボックスに対して自動拡張アーカイブを有効にした場合、次の 2 つの構成が変更されます。
  
- ユーザーのプライマリ アーカイブ メールボックスの記憶領域のクォータが 10 GB 増加します (100 GB から 110 GB へ)。 また、アーカイブの警告クォータも 10 GB 増加します (90 GB から 100 GB へ)。

- ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーの記憶領域のクォータは、10 GB 増加します (100 GB から 110 GB へ)。 回復可能なアイテムの警告クォータも、10 GB 増加します (90 GB から 100 GB へ)。 これらの変更は、保持中のメールボックスまたはアイテム保持ポリシーに割り当てられている場合にのみ適用されます。

この追加容量は、自動拡張アーカイブのプロビジョニングが行われる前に発生する可能性がある記憶領域の問題を防ぐために追加されるものです。 前のセクションで説明したように、自動拡張アーカイブを組織全体に対して有効にする場合は、追加記憶領域は追加 *されません*。
  
1. [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

2. 自動拡張アーカイブを特定のユーザーに対して有効にするには、次の PowerShell コマンドを実行します。 前述のように、ユーザーの自動拡張アーカイブを有効にする前に、そのユーザーのアーカイブ メールボックス (メイン アーカイブ) を有効にしておく必要があります。

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> Exchange ハイブリッド展開では **、Enable-Mailbox -AutoExpandingArchive** コマンドを使用して、プライマリ メールボックスがオンプレミスで、アーカイブ メールボックスがクラウドベースの特定のユーザーに対して自動拡張アーカイブを有効にすることはできません。 クラウド ベースのアーカイブ メールボックスの自動拡張アーカイブを Exchange ハイブリッド展開で有効にするには、Exchange Online PowerShell で **Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して、組織全体に対して自動拡張アーカイブを有効にする必要があります。 ユーザーのプライマリ メールボックスとアーカイブ メールボックスが両方ともクラウド ベースの場合は、**Enable-Mailbox -AutoExpandingArchive** コマンドを使用してそのユーザーに対して自動拡張アーカイブを有効にできます。
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>自動拡張アーカイブが有効になっていることを確認する

自動拡張アーカイブが組織に対して有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

値 `True` は、自動拡張アーカイブが組織に対して有効になっていることを示します。 
  
特定のユーザーに対して自動拡張アーカイブが有効になっているか確認するには、PowerShell で次のコマンドExchange Onlineします。
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

値 `True` は、自動拡張アーカイブがそのユーザーに対して有効になっていることを示します。
  
非アクティブなメールボックスに対して自動拡張アーカイブが有効になっているかどうかを確認するには、PowerShell で次のコマンドExchange Onlineします。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

値は  `True` 、非アクティブなメールボックスに対して自動拡張アーカイブが有効になっているかどうかを示します。 値は `False` 、自動拡張アーカイブが有効になっていないかどうかを示します。

自動拡張アーカイブを有効にした後は、次の点に注意してください。
  
- **Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して自動拡張アーカイブを組織に対して有効化する場合は、個々のメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** を実行する必要はありません。 組織の自動拡張アーカイブを有効にする **Set-OrganizationConfig** コマンドレットを実行しても、ユーザー メールボックスの  *AutoExpandingArchiveEnabled*  プロパティはに変更されません `True` 。

- 同様に、自動拡張アーカイブを有効にしても、メールボックスの *ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティの値も変更されません。 実際、ユーザー メールボックスの自動拡張アーカイブを有効にして、*AutoExpandingArchiveEnabled* プロパティを `True` に設定している場合、*ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティは無視されます。 ユーザーのメールボックスの自動拡張アーカイブを有効にした後のこれらのメールボックス プロパティの例を示します。 

    ![アーカイブの自動拡張を有効にした後、ArchiveQuota プロパティと ArchiveWarningQuota プロパティは無視されます。](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>詳細情報

- PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。 たとえば、Exchange Online PowerShell で次のコマンドを実行して、アーカイブ メールボックスがまだ有効になっていないすべてのユーザーのアーカイブ メールボックスを有効にできます。

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 組織または特定のユーザーに対して自動拡張アーカイブを有効にした後、アーカイブ メールボックス ([回復可能なアイテム] フォルダーを含む) が 90 GB に達すると、アーカイブ メールボックスは自動拡張アーカイブに変換されます。 追加記憶領域がプロビジョニングされるには、最大 30 日かかります。

- 自動拡張アーカイブを有効にした後は、無効にすることはできません。 さらに、管理者は自動拡張アーカイブの記憶域クォータを調整できない。

- 自動拡張アーカイブは、オンプレミスのプライマリメールボックスを持つユーザーについて、Exchange ハイブリッド展開のクラウド ベースのアーカイブ メールボックスでサポートされています。 ただし、クラウド ベースのアーカイブ メールボックスに対して自動拡張アーカイブを有効にした後は、そのアーカイブ メールボックスをオフボードしてオンプレミスの Exchange 組織に戻すことはできません。 自動拡張アーカイブは、任意のバージョンのメールボックスのオンプレミス メールボックスExchange Server。

- ユーザーがアーカイブ メールボックス内の追加の記憶域内のアイテムにアクセスするために使用できる Outlook クライアントの一覧については、「自動拡張アーカイブの概要」の「自動拡張アーカイブ内のアイテムにアクセスする Outlook 要件[](autoexpanding-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)」セクションを参照してください。

- 前述のように、**Enable-Mailbox -AutoExpandingArchive** コマンドを実行すると、ユーザーのプライマリ アーカイブ メールボックス (および、メールボックスが保留中の場合は、[回復可能なアイテム] フォルダー) の記憶領域のクォータ に 10 GB が追加されます。 これにより、自動拡張記憶領域がプロビジョニングされるまで (最大で30 日間かかります)、追加の記憶領域が提供されます。 **Set-OrganizationConfig -AutoExpandingArchive** を実行して組織のすべてのメールボックスに対して自動拡張アーカイブを有効化した場合は、追加記憶領域は追加されません。 自動拡張アーカイブを組織全体に対して有効化した場合でも、特定のユーザーの記憶領域に 10 GB を追加する必要がある場合は、そのメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** コマンドを実行できます。 自動拡張アーカイブが既に有効化されているというエラー メッセージが表示されますが、メールボックスには追加記憶領域が追加されます。

> [!IMPORTANT]
> 自動拡張アーカイブは、個々のユーザーが使用するメールボックス、または 1 日に 1 GB を超えない増加率の共有メールボックスでのみサポートされます。 アーカイブ目的のために、ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。 ユーザーのアーカイブ メールボックスは、そのユーザー専用です。 Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを保存したり、不適切な使用を行った場合に、追加のアーカイブを拒否する権利を保持します。
