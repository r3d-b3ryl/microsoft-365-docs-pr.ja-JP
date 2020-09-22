---
title: Teams、safelinks、安全なリンク、悪意のあるリンクのブロック、office 365 atp、Teams の安全なリンク、ユーザーによる不正なリンクのクリックを阻止する悪意のあるリンク
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: クリックしたときに Teams が安全なリンクにアクセスできるようになります。 1対1のチャット、グループ間、またはチャネル内のチャットを使用しているかどうか、および Office 365 ATP へのサブスクリプションがある場合は、このセーフティ機能を有効にして使用することができます。
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198753"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Teams の安全なリンク

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> この機能は、2020年2月28日の Microsoft Teams テクノロジ導入プログラム (タップ) にあるお客様向けの **パブリックプレビュー** です。 このメモは、Teams の安全なリンクがより幅広く利用できる場合に記事から削除されます。

Microsoft Teams は、Microsoft のクラウドベースのアプリケーションである仕事を管理するために、既に安全な添付ファイル (Office 365) を使用していますが、これでクリック時に安全なリンクにアクセスできるようになります。 Office 365 ATP へのサブスクリプションがある場合、チャット、グループチャット、チャネル、またはタブを使用しているかどうかにかかわらず、この安全手段を有効にして使用することができます。 ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

次に、動作のしくみを示します。

1. Teams アプリケーションを起動すると、Microsoft 365 は、ユーザーが Office 365 ATP を使用している組織に所属しており、ユーザーが Microsoft Teams の保護が有効になっているアクティブな安全リンクポリシーの一部であることを確認します。

2. 上記の条件に該当する場合、Url は、チャット、グループチャット、チャネル、およびそのユーザーのタブでクリックしたときに検証されます。

## <a name="what-will-users-experience"></a>ユーザーにはどのような状況がありますか?

保護されたすべてのユーザーには、次のような危険な Url があります。

- リンクが Teams 会話、グループチャット、またはチャネルからクリックされた場合は、既定のブラウザーでページが表示されます。 固定されたタブからリンクがクリックされた場合は、そのページがそのタブ内の Teams GUI に表示され、セキュリティ上の理由から、ブラウザーで開くオプションは無効になります。

- このユーザーは、URL のサイトへの進行をブロックされます。

リンクを送信したユーザーが Office 365 ATP によって保護されていない場合は、自分のコンピューターで URL をクリックして、問題のサイトを解決することができます。 これにより、管理者は、保護されたユーザーがどのようなものであるかを認識できるようになります。

![Teams ページの安全なリンクは、悪意のあるリンクを報告し、ページへの送信をブロックします。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Teams で、このページの [ *戻る* ] ボタンをクリックすると、そのページが閉じます (または、ユーザーが空白のページが閉じられる可能性があります)。 ただし、リンクをもう一度クリックすると、このページが表示されるように、サイトの評価が reassessment されます。

> [!NOTE]
> 一部の Microsoft 365 管理者は、[ブロック] ページで **続行** するかどうかのメッセージを有効にします。 ただし、安全なリンクによってサイトの評価が測定され、不足している場合は、これ以上のクリックスルーを行う必要はありません。 ユーザーが安全対策を省略することはお勧めしません。 続行する前に、この点を考慮に入れてください。
