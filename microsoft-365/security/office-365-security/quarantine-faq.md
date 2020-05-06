---
title: 検疫に関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Exchange Online またはスタンドアロン EOP の Office 365 メールボックスの検疫に関してよく寄せられる質問と、Exchange Online のメールボックスがない場合の回答。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c5d7f426701ebc9a546a86a4fccbd7015fc0e49
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033856"
---
# <a name="quarantine-faq"></a>検疫に関する FAQ

このトピックでは、exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) のお客様のメールボックスを使用する Microsoft 365 ユーザーの検疫についてよく寄せられる質問と回答を示します。

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Q: マルウェア用に検疫されたメッセージを管理するにはどうすればよいですか?

管理者のみが、マルウェア用に検疫されたメッセージを管理できます。 詳細については、「[Office 365 の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="q-how-do-i-quarantine-spam"></a>Q: スパムの検疫方法を教えてください。

A. 既定では、スパムフィルターによってスパムまたはバルクメールとして分類されるメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 ただし、スパムまたはバルクメールメッセージを検疫するスパム対策ポリシーを作成して構成することができます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>Q: ユーザーに検疫へのアクセスを許可する方法を教えてください。

A. ユーザーは、検疫で自分のメッセージにアクセスするための有効なアカウントを持っている必要があります。 スタンドアロン EOP では、ユーザーが EOP のメールユーザーとして表されている必要があります (手動で作成またはディレクトリ同期経由で作成されます)。 スタンドアロン EOP 環境でのユーザーの管理の詳細については、「 [Manage mail users IN EOP](manage-mail-users-in-eop.md)」を参照してください。

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>Q: エンドユーザーが検疫でアクセスできるメッセージは何ですか。

A. ユーザーは、スパム、バルクメール、および (2020 年4月) の受信者であるフィッシングメッセージにアクセスできます。 エンドユーザーは、メールフロールール (トランスポートルールとも呼ばれる) でホストされた**検疫アクションにメッセージを配信**するため、検疫されたマルウェア、信頼性の高いフィッシング、またはメッセージを検疫済みメッセージにアクセスできません。 検疫済みメッセージにアクセスするユーザーの詳細については、「 [Office 365 のユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>Q: 検疫内のメッセージはどのくらいの期間保持されますか?

A. スパム対策ポリシーを使用して、スパム、フィッシング、およびバルクメールメッセージを検疫に保持する期間を構成します。 既定値は30日で、これも最大数です。 詳細については、「 [Office のスパム対策ポリシーを構成する 365](configure-your-spam-filter-policies.md) 」を参照してください。

メールフロールールアクションによって検疫されたメッセージは、ホストされた**検疫にメッセージを配信する**ため、メッセージは30日間検疫に保持されます。 この期間を構成することはできません。

期間が過ぎると、メッセージは削除され、復元することはできません。

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Q: 一度に複数の検疫済みメッセージを解放またはレポートすることはできますか。

A. セキュリティ & コンプライアンスセンターでは、一度に最大100のメッセージを選択して解放することができます。

管理者は、Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell で Get-quarantinemessage および[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)コマンドレットを使用して、検疫[済み](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)メッセージを一括で検索して解放し、誤検知を一括で報告することができます。

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Q: 検疫されたメッセージを検索する場合、ワイルドカードはサポートされていますか? 特定のドメインの隔離されたメッセージを検索できますか。

A. セキュリティ & コンプライアンスセンターでは、ワイルドカードはサポートされていません。 たとえば、送信者を検索する場合は、完全な電子メールアドレスを指定する必要があります。 ただし、Exchange Online の PowerShell または Exchange Online Protection の PowerShell でワイルドカードを使用することができます。

たとえば、次のコマンドを実行して、ドメイン contoso.com のすべての送信者からスパム検疫済みメッセージを検索します。

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

その後、次のコマンドを実行して、これらのメッセージを元の受信者すべてに解放します。

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

メッセージを解放した後で、再度解放することはできません。
