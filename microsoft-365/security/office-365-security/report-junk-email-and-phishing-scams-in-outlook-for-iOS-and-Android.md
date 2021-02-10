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
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166821"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Exchange Online で iOS および Android 用の Outlook で迷惑メールとフィッシングメールを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

ハイブリッドの最新認証を使用して Exchange Online またはオンプレミスのメールボックスにメールボックスを持[](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)つ Microsoft 365 組織では、iOS および Android 用の Outlook の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (無効な電子メールが許可)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に知る必要がある情報

- Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&することをお勧めします。 詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。

- メッセージを Microsoft に報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > ユーザー送信ポリシーで Outlook で迷惑メール報告が無効になっている場合、迷惑メールまたはフィッシングメッセージは迷惑メール フォルダーに移動され、管理者や Microsoft には報告されません。

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でスパムメッセージとフィッシング メッセージを報告する

受信トレイ内のメッセージ、または迷惑メール以外の他のメール フォルダーの場合は、次の手順を使用して、iOS および Android のスパム メッセージとフィッシング メッセージを報告します。

1. 1 つ以上のメッセージを選択します。
2. 右上隅で、3 つの垂直ドットをタップします。 操作メニューが開きます。

   ![操作メニューから迷惑メールまたはフィッシングメールを報告する](../../media/Android-report-as-junk-dialog.png)

3. [ **迷惑メールの報告]** をタップし、[ **迷惑メール** ] または [フィッシング **] を選択します**。

   ![迷惑メールまたはフィッシングメールを報告する](../../media/Android-report-junk-or-phishing.png)

4. 表示されるダイアログで、[レポート] または [No Thanks]**を****選択できます**。 On selecting **No Thanks,** if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder. [ **レポート]** を選択すると、メッセージのコピーも Microsoft に送信されます。

   ![迷惑メールまたはフィッシングメールの報告オプションを報告する](../../media/Android-junk-email-reporting-options.png)

考え方が変わる場合は **、表示される** トースト通知で [元に戻す] を選択します。 メッセージは受信トレイ フォルダーに残ります。

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook の [迷惑メール] フォルダーからスパムではないメッセージを報告する

迷惑メール フォルダーで、次の手順を使用してスパム誤検知を報告します。

1. 1 つ以上のメッセージを選択します。
2. 右上隅で、3 つの垂直ドットをタップします。 操作メニューが開きます。

   ![操作メニューから迷惑メールではないメールを報告する](../../media/Android-not-junk-email.png)

3. [迷惑 **メールではない] をタップします**。

電子メールが受信トレイに移動されたというトースト通知が表示されます。 考え方が変わる場合は、トースト **通知で [元に** 戻す] を選択します。 メールは迷惑メール フォルダーに残ります。
