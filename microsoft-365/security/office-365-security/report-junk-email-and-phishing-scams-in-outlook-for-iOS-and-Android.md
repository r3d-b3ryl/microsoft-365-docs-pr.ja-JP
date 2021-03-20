---
title: Outlook for iOS および Android で迷惑メールとフィッシングメールを報告する
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
description: 管理者は、Outlook for iOS と Android の組み込みの迷惑メール、迷惑メール、フィッシングメールレポートのオプションについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eda0d8d43244834236a70374df6b7d6ccf0b69ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908820"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Exchange Online で Outlook for iOS と Android で迷惑メールとフィッシングメールを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスメールボックスにメールボックスを持つ[](../../enterprise/hybrid-modern-auth-overview.md)Microsoft 365 組織では、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始する前に知る必要があるもの

- 最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージとレポート フィッシング アドインを使用することをお勧めします。詳細 [については、「レポート メッセージ アドインを有効](./enable-the-report-message-add-in.md) にする」および「レポート フィッシング アドインを [有効にする」](./enable-the-report-phish-add-in.md) を参照してください。

- Exchange Online メールボックスを使用している組織の管理者の場合は、セキュリティ コンプライアンス センターの申請ポータルを使用&勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については [、「User Submissions ポリシー」を参照してください](user-submission.md)。

- Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > ユーザー申請ポリシーで Outlook の迷惑メールレポートが無効になっている場合、迷惑メールまたはフィッシング メッセージは迷惑メール フォルダーに移動され、管理者または Microsoft には報告されません。