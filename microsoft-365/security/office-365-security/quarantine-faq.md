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
- m365initiative-m365-defender
description: 管理者は、Exchange Online Protection (EOP) で、検疫されたメッセージについてよく寄せられる質問と回答を確認できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cf1281338de66f54a6c4546b047259d647cc3ea
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615998"
---
# <a name="quarantined-messages-faq"></a>検疫済みメッセージに関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


このトピックでは、exchange Online にメールボックスがある Microsoft 365 組織の検疫済み電子メールメッセージ、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織についてよく寄せられる質問とその回答について説明します。

スパム対策保護に関する質問と回答については、「 [スパム対策保護](anti-spam-protection-faq.md)に関する FAQ」を参照してください。

マルウェア対策保護に関する質問と回答については、「 [マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。

スプーフィング対策保護に関する質問と回答については、「 [スプーフィング対策保護](anti-spoofing-protection-faq.md)に関する FAQ」を参照してください。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>マルウェア用に検疫されたメッセージを管理するにはどうすればよいですか?

管理者のみが、マルウェア用に検疫されたメッセージを管理できます。 詳細については、「 [管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="how-do-i-quarantine-spam"></a>スパムを検疫する方法

既定では、スパムフィルターによってスパムまたはバルクメールとして分類されるメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 ただし、スパムまたはバルクメールメッセージを検疫するスパム対策ポリシーを作成して構成することができます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>ユーザーに検疫へのアクセスを許可するには、どうすればよいですか?

ユーザーは、検疫で自分のメッセージにアクセスするための有効なアカウントを持っている必要があります。 スタンドアロン EOP では、ユーザーが EOP のメールユーザーとして表されている必要があります (手動で作成またはディレクトリ同期経由で作成されます)。 スタンドアロン EOP 環境でのユーザーの管理の詳細については、「 [Manage mail users IN EOP](manage-mail-users-in-eop.md)」を参照してください。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>エンドユーザーが検疫でアクセスできるメッセージ

ユーザーは、スパム、バルクメール、および (2020 年4月) の受信者であるフィッシングメッセージにアクセスできます。 エンドユーザーは、メールフロールール (トランスポートルールとも呼ばれる) でホストされた **検疫アクションにメッセージを配信** するため、検疫されたマルウェア、信頼性の高いフィッシング、またはメッセージを検疫済みメッセージにアクセスできません。 検疫済みメッセージにアクセスするユーザーの詳細については、「 [ユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>メッセージは検疫に保持される期間はどのくらいですか?

スパム対策ポリシーを使用して、スパム、フィッシング、およびバルクメールメッセージを検疫に保持する期間を構成します。 既定値は30日で、これも最大数です。 詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

メールフロールールアクションによって検疫されたメッセージは、ホストされた **検疫にメッセージを配信する** ため、メッセージは30日間検疫に保持されます。 この期間を構成することはできません。

期間が過ぎると、メッセージは削除され、復元することはできません。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>一度に複数の検疫メッセージを解放または報告できますか。

セキュリティ & コンプライアンスセンターでは、一度に最大100のメッセージを選択して解放することができます。

管理者は、Exchange Online PowerShell またはスタンドアロン EOP PowerShell で [get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) および [get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) コマンドレットを使用して、検疫済みメッセージを一括で検索して解放し、誤検知を一括で報告することができます。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。 特定のドメインの隔離されたメッセージを検索できますか。

セキュリティ & コンプライアンスセンターでは、ワイルドカードはサポートされていません。 たとえば、送信者を検索する場合は、完全な電子メールアドレスを指定する必要があります。 ただし、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell でワイルドカードを使用することができます。

たとえば、次のコマンドを実行して、ドメイン contoso.com のすべての送信者からスパム検疫済みメッセージを検索します。

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

その後、次のコマンドを実行して、これらのメッセージを元の受信者すべてに解放します。

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

メッセージを解放した後で、再度解放することはできません。
