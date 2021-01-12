---
title: 検疫済みメッセージに関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Exchange Online Protection (EOP) で検疫済みメッセージに関してよく寄せられる質問と回答を表示できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794414"
---
# <a name="quarantined-messages-faq"></a>検疫済みメッセージに関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


このトピックでは、Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織の検疫済み電子メール メッセージについてよく寄せられる質問と回答を提供します。

スパム対策保護に関する質問と回答については、スパム対策保護に関する [FAQ を参照してください](anti-spam-protection-faq.md)。

マルウェア対策保護に関する質問と回答については、マルウェア対策保護に関する [FAQ を参照してください](anti-malware-protection-faq-eop.md)。

スプーフィング対策保護に関する質問と回答については、スプーフィング対策保護に関する [FAQ を参照してください](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>マルウェアに対して検疫されたメッセージを管理する方法

マルウェアに対して検疫されたメッセージを管理できるのは管理者のみです。 詳細については、「管理者として検疫 [済みメッセージとファイルを管理する」を参照してください](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>スパムを検疫する方法

既定では、スパム フィルターによってスパムまたはバルク メールとして分類されたメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 ただし、スパム対策ポリシーを作成して構成して、代わりにスパムメッセージまたはバルク メール メッセージを検疫できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>ユーザーに検疫へのアクセス権を与える方法

検疫で自分のメッセージにアクセスするには、ユーザーに有効なアカウントが必要です。 スタンドアロン EOP では、ユーザーは EOP でメール ユーザーとして表される必要があります (ディレクトリ同期を使用して手動で作成または作成)。 スタンドアロン EOP 環境でのユーザー管理の詳細については、「EOP でのメール ユーザーの管理」を [参照してください](manage-mail-users-in-eop.md)。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>エンド ユーザーが検疫でアクセスできるメッセージ

ユーザーは、スパム、バルク メール、および受信者である (2020 年 4 月現在) フィッシング メッセージにアクセスできます。 エンド ユーザーは、メール フロー ルール (トランスポート ルールとも呼ばれる) のホストされた検疫アクションにメッセージを配信するために検疫されたマルウェア、信頼度の高いフィッシング、または検疫されたメッセージにアクセスできない。 検疫済みメッセージにアクセスするユーザーの詳細については、「ユーザーとして検疫済みメッセージを検索 [して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>検疫にメッセージを保持する期間はどのくらいですか?

スパム対策ポリシーを使用して、スパム、フィッシング、バルク メール メッセージを検疫に保持する期間を構成します。 既定値は 30 日で、これは最大値です。 詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください。](configure-your-spam-filter-policies.md)

メール フロー ルールアクションによって検疫されたメッセージの場合 **、** ホストされた検疫にメッセージを配信すると、メッセージは 30 日間検疫に保持されます。 この期間は構成できない。

期間が経過すると、メッセージは削除され、回復できません。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>一度に複数の検疫メッセージを解放または報告できますか。

セキュリティ/コンプライアンス センター&、一度に最大 100 件のメッセージを選択して解放できます。

管理者は、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell で [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) コマンドレットと [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) コマンドレットを使用して、検疫済みメッセージを一括して検索して解放し、誤検知を一括して報告できます。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。 特定のドメインの隔離されたメッセージを検索できますか。

セキュリティ/コンプライアンス センターでは、ワイルドカード&サポートされていません。 たとえば、送信者を検索する場合は、完全なメール アドレスを指定する必要があります。 ただし、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell ではワイルドカードを使用できます。

たとえば、次のコマンドを実行して、ドメイン 内のすべての送信者からのスパム検疫済みメッセージを検索contoso.com。

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

次に、次のコマンドを実行して、これらのメッセージを元のすべての受信者に解放します。

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

メッセージを解放した後は、メッセージを解放し直す必要はありません。
