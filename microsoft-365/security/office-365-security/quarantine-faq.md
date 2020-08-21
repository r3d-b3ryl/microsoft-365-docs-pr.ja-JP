---
title: 隔ドされたメッセージに関する FAQ
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
description: 管理者は、検疫済みメッセージに関するよく寄せられる質問と回答を Exchange Online Protection (EOP) で表示できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826791"
---
# <a name="quarantined-messages-faq"></a>隔ドされたメッセージに関する FAQ

このトピックでは、Exchange Online メールボックスを使用している Microsoft 365 組織または Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織向けの検疫済み電子メール メッセージに関するよく寄せられる質問と回答について取り上示します。

スパム対策保護に関する質問と回答については、「スパム対策保護 [のよく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。

マルウェア対策保護に関する質問と回答については、「マルウェア対策保護 [」に関する FAQ を参照してください](anti-malware-protection-faq-eop.md)。

スプーフィング対策保護に関する質問と回答については、「スプーフィング [対策保護に関する FAQ」を参照してください](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>マルウェアのために検疫されたメッセージはどのように管理しますか?

マルウェアのために検疫されたメッセージを管理できるのは管理者のみです。 詳細については、管理者として [検疫済みメッセージとファイルの管理に関するトピックを参照してください](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>スパムを検疫する方法

既定では、スパム フィルター処理によってスパムまたはバルク メールとして分類されたメッセージはユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動します。 ただし、スパム対策ポリシーを作成して構成し、スパムまたはバルク メール メッセージを検疫できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>ユーザーに検疫へのアクセス許可を付与する方法を示しますか?

ユーザーは、検疫内の自分のメッセージにアクセスするために有効なアカウントを持つ必要があります。 スタンドアロン EOP では、ユーザーが EOP のメール ユーザーとして表される必要があります (手動で作成またはディレクトリ同期による作成)。 スタンドアロン EOP 環境でのユーザー管理の詳細については、「EOP でメール [ユーザーを管理する」を参照してください](manage-mail-users-in-eop.md)。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>検疫でエンド ユーザーがアクセスできるメッセージは何ですか。

ユーザーは、スパム、バルク メール、(2020 年 4 月現在) のフィッシング メッセージにアクセスできます。2020 年 4 月以降、これらのメッセージは受信者です。 エンド ユーザーは、検疫されたマルウェア、高い信頼度フィッシング、または検疫されたメッセージにメッセージをメール フロー ルール (トランスポート ルールとも呼ばれる) の **ホスト** された検疫アクションに配信するために処理されたメッセージにアクセスできません。 検疫済みメッセージにアクセスするユーザーの詳細については、ユーザーが検疫 [済みメッセージを検索して解放する必要があります](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>メッセージは検疫内に保持される期間はどれよいでしょうか。

スパム対策ポリシーを使用して、スパム、フィッシング、およびバルク メール メッセージを検疫に保存する期間を構成します。 既定値は 30 日で、これは上限で当されます。 詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください。](configure-your-spam-filter-policies.md)

メール フロー ルールのアクションによって検疫されたメッセージが **ホストされた検疫に配信された場合**、メッセージは検疫に 30 日間保持されます。 この期間は構成できます。

期間が過ぎると、メッセージは削除され、回復不可能になります。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>一度に複数の検疫メッセージを解放または報告できますか。

コンプライアンス センターでは&、同時に最大 100 個のメッセージを選択して解放することができます。

管理者は、Exchange Online PowerShell [の Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) コマンドレットと [Release-QuarantineMessage コマンドレット](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) またはスタンドアロン EOP PowerShell を使用して、検疫済みメッセージを一括で検索して解放したり、誤検知を一括で報告したりすることができます。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。 特定のドメインの隔離されたメッセージを検索できますか。

ワイルドカードは、セキュリティ、コンプライアンス センターでは &サポートされません。 たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。 ただし、ワイルドカードは、Exchange Online PowerShell でも、スタンドアロン EOP PowerShell でも使用できます。

たとえば、ドメイン名の受信者すべてからスパム検疫済みメッセージを検索するには、次のコマンドをcontoso.com。

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

その後、次のコマンドを実行して、それらのメッセージを元のすべての受信者にリリースします。

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

メッセージを解放した後は、もう一度メッセージを解放することはできません。
