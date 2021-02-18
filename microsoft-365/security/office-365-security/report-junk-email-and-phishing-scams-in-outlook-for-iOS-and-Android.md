---
title: iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、iOS および Android 用の Outlook の組み込みの迷惑メール、迷惑メール、フィッシングメール報告オプションについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289175"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Exchange Online で iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

ハイブリッドの最新認証を使用して Exchange Online またはオンプレミスのメールボックスにメールボックスを持[](../../enterprise/hybrid-modern-auth-overview.md)つ Microsoft 365 組織では、iOS および Android 用の Outlook の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に知る必要がある情報

- 最適なユーザー送信エクスペリエンスを得る場合は、レポート メッセージ アドインと Report Phishing アドインの使用をお勧めします。詳細 [については、「メッセージ報告アドインを有効にする](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) 」および「フィッシング報告 [アドインを有効にする](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) 」を参照してください。

- Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。 詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。

- Microsoft にメッセージを報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > ユーザー送信ポリシーで Outlook で迷惑メール報告が無効になっている場合、迷惑メールまたはフィッシングメッセージは迷惑メール フォルダーに移動され、管理者や Microsoft には報告されません。