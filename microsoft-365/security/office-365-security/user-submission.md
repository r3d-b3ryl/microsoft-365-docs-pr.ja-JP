---
title: ユーザーがスパムおよびフィッシングメッセージを送信するためのメールボックスを指定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーによって報告されたスパムやフィッシング電子メールを収集するようにメールボックスを構成する方法について説明します。
ms.openlocfilehash: 6de4c076af5b0c669625cd8edaa367f072c27598
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173346"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a>Office 365 でスパムおよびフィッシングのメッセージをユーザーが送信するためのメールボックスを指定する

Exchange Online メールボックスを使用する Office 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。 ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。 この機能は、次のメッセージレポートオプションで機能します。

- [レポートメッセージアドイン](enable-the-report-message-add-in.md)

- [Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート

また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。

ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、[管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [**ユーザーの送信**] ページに直接移動する<https://protection.office.com/userSubmissionsReportMessage>には、を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 ユーザーが送信するメールボックスを構成するには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**ユーザーの送信**] に移動します。

2. 表示される [**ユーザーの送信**] ページで、次のいずれかのオプションを選択します。

   - **Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。

     - **エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。 [**確認メッセージのカスタマイズ**] ポップアップが表示されたら、次の設定を構成します。

       - **提出前**:**タイトル**と確認の**メッセージ**ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。

         前述のように、通知には次のテキストも追加されます。

         > 電子メールは、のように、分析のために Microsoft に提出されます。 メールによっては個人情報や機密情報が含まれる場合があります。

       - **送信後**: [ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックします。 [**タイトル**] および [**確認メッセージ**] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、提出の種類を含めることができます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。

   - **報告されたメッセージの送信先**: 次のいずれかの選択を行います。

     - **Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。

     - **Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。

     - **カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。

     完了したら、[**確認**] をクリックします。

     ![報告されたメッセージを Microsoft およびカスタムメールボックスに送信する](../../media/user-submission-enable-outlook-report-message.png)

   - **Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。

     [**このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。 表示されるボックスに、既存のメールボックスの電子メールアドレス、または作成するメールボックスの電子メールアドレスを入力します。

     完了したら、[**確認**] をクリックします。

     ![サードパーティ製のツールを使用して、レポートされたメッセージをカスタムメールボックスに送信する](../../media/user-submission-disable-outlook-report-message.png)
