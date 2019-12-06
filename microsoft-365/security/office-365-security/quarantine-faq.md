---
title: 検疫に関する FAQ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。
ms.openlocfilehash: 2754efb6edee577eca351da0486ac54912ec4b5b
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39872083"
---
# <a name="quarantine-faq"></a>検疫に関する FAQ

このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。

 **Q: 検疫でマルウェアによって検疫されたメッセージを管理するにはどうすればよいですか?**

検疫に送信された&amp;メッセージにマルウェアが含まれている場合に、そのメッセージを表示および操作するには、セキュリティコンプライアンスセンターを使用する必要があります。 詳細については、「[Office 365 でのメール メッセージの検疫](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)」を参照してください。

 **Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**

A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

 **Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**

A. 管理者は、検疫された電子メール メッセージすべてに関する詳細を Exchange 管理センター (EAC) で検索し、表示することができます。メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。

エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。

- スパム検疫ユーザー インターフェース。 詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

 **Q. エンド ユーザーにスパム検疫へのアクセスを許可するにはどのようにすればよいですか。**

A. エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。 社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。 ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](manage-mail-users-in-eop.md)する」を参照してください。 EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

 **Q. スパム以外のものを検疫に送信できますか?**

A. はい。 フィッシングとして識別されたメッセージと共に、メールフロールール (トランスポートルールとも呼ばれます) に一致するメッセージを、管理者検疫に送信することもできます (構成済みのアクションの場合)。 エンドユーザー検疫は、スパムのみを対象としています。

 **Q. メッセージが検疫内に保存される期間はどのくらいですか。**

A. 既定では、スパム検疫メッセージは30日間検疫に保存されますが、メールフロールールと一致した検疫メッセージは、既定のコンテンツフィルターポリシーで設定された保持期間に基づいて最大30日間検疫に保持されます。 この期間が経過したら、メッセージは削除され、取得不能になります。 メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。 ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。 詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

 **Q. 一度に複数の検疫メッセージを解放または報告できますか。**

A. はい。検疫ポータルで一度に最大100のメッセージを解放することができます。 さらに、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。 メッセージを検索する場合は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットを使用します。

 **Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**

A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。

リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

この結果は、[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
