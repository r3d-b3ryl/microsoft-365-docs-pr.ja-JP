---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Exchange メールフロールールを作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりできないようにすることができます。
ms.openlocfilehash: 530cc12fd83650f319da3f65e961c925a1de7409
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598064"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

分析のために、偽陽性と偽陰性のメッセージを Microsoft に送信する方法は複数あります。 管理者は、メール フロー ルールを使用して、ユーザーが Microsoft にスパム、スパム以外、およびフィッシング詐欺として報告しているものを確認することができます。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。 反対に、Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりするのを防ぐことができます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

予想所要時間 : 5 分

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「 [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)」の「メールフロー」および「web メールボックスポリシー」のエントリを参照してください。

このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. ![[追加] アイコン](../media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。

3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。

4. **[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。

5. [**単語または語句の指定**] ボックスで、次の手順を実行します。

   - 種類`abuse@messaging.microsoft.com`**をクリックし** ![、[](../media/ITPro-EAC-AddIcon.gif)追加] `junk@office365.microsoft.com`アイコン、入力して、](../media/ITPro-EAC-AddIcon.gif) **[追加] アイコンをクリック** ![します。 これらの電子メール アドレスは、偽陰性のメッセージをマイクロソフトに送信するために使用されます。

   - 入力`phish@office365.microsoft.com`して、 **[追加]** ![アイコン](../media/ITPro-EAC-AddIcon.gif)をクリックします。 この電子メール アドレスは、フィッシングとして処理されなかったフィッシング メッセージを Microsoft に送信するために使用されます。

   - 種類`false_positive@messaging.microsoft.com`**をクリックし** ![、[](../media/ITPro-EAC-AddIcon.gif)追加] `not_junk@office365.microsoft.com`アイコン、種類、 **[追加]** ![アイコン](../media/ITPro-EAC-AddIcon.gif)をクリックします。 これらの電子メール アドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。

   - **[OK]** をクリックします。

6. **[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。

7. これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 「[メールフロールールの手順」を](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)参照してください。

8. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。

ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。
