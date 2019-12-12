---
title: Exchange Online の差出人セーフ リストと受信拒否リスト
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。
ms.openlocfilehash: 5530fa8c8ee5a83c4e8515a8f31f91e45b2ec97b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971675"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online の差出人セーフ リストと受信拒否リスト

Exchange Online または Exchange Online Protection (EOP) の管理者は、サービスを通過する電子メール メッセージがスパムとしてマークされないようにできます。そのための方法の 1 つに、組織内のユーザーの中で、信頼できる差出人とブロックする差出人のリストを作成する、というものがあります。

[Office 365 で良好なメールがスパムとしてマークされないようにする方法](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam)*について、これらのリストを管理者として管理する方法に関するヒントと手順の更新版を参照してください*。

管理者ではない場合に、差出人セーフリストを使用して Outlook で自分の迷惑メールを管理する場合は、[「迷惑メールフィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」の手順を参照してください。

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online での信頼できる差出人とブロックする差出人の制限について

Exchange Online での信頼できる差出人とブロックする差出人の制限は、Active Directory の制限や Outlook の制限と異なります。以下にその例を示します。

- 差出人セーフ リストの制限: 1,024

- ブロックする差出人の制限: 500

注:

[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)で説明されているエラーが発生することがあります。 この問題を解決するには、[連絡先からの電子メールを信頼する] チェックボックスをオフにします。 または、"MaxSafeSenders" 属性に設定されている Exchange Online で、既定の連絡先フォルダーに含まれる電子メールアドレスの量を減らして、最大許容制限である1024に設定します。 この属性とメールボックスの設定コマンドレットの詳細については、次のトピックを参照してください。

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>関連項目

[Exchange Server での送信者フィルター](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
