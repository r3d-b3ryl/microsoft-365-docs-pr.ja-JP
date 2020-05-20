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
ms.openlocfilehash: 2a1872aff88cd1cc21c6a6e3258671c303b55e17
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294195"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Exchange Online でスパムおよびフィッシングメッセージをユーザーが送信するためのメールボックスを指定する

Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。 ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。 この機能は、次のメッセージレポートオプションで機能します。

- [レポートメッセージアドイン](enable-the-report-message-add-in.md)

- [Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート

  > [!NOTE]
  > [Web 上の outlook で](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーによる送信を有効にすると、その設定が無効になり、ユーザーは web 上の outlook でメッセージを再度レポートすることができます。

また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。

ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、[管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [**ユーザーの送信**] ページに直接移動するには、を使用 <https://protection.office.com/userSubmissionsReportMessage> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 ユーザーが送信するメールボックスを構成するには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのユーザーの送信] に移動 \> **Policy** \> **User submissions**します。

2. 表示される [**ユーザーの送信**] ページで、次のいずれかのオプションを選択します。

   a.  **Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。

      - **エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。 [**確認メッセージのカスタマイズ**] ポップアップが表示されたら、次の設定を構成します。

      - **提出前**:**タイトル**と確認の**メッセージ**ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。

        前述したように、報告されたメッセージを Microsoft に送信するオプションを選択すると、通知に次のテキストも追加されます。

        > 電子メールは、のように、分析のために Microsoft に提出されます。 メールによっては個人情報や機密情報が含まれる場合があります。

      - **送信後**: [ ![ 展開] アイコンをクリックし ](../../media/scc-expand-icon.png) ます。 [**タイトル**] および [**確認メッセージ**] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、提出の種類を含めることができます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。

      - **報告されたメッセージの送信先**: 次のいずれかの選択を行います。

        - **Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。

        - **Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。 ユーザーによる送信は、分析のために Microsoft と Microsoft の両方に、管理者またはセキュリティ運用チームのためのカスタムメールボックスに移動します。

        - **カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。 このオプションを使用するのは、最初に分析のために管理者またはセキュリティ操作チームのみにメッセージを移動する場合です。 管理者が転送しない限り、メッセージは Microsoft に送られません。

        完了したら、[**確認**] をクリックします。

     > [!CAUTION]
     > Web 上の outlook on the web メールボックスポリシーを使用して outlook の[迷惑メール報告を無効](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)にしたが、microsoft にメッセージを報告するために以前の設定のいずれかを構成した場合、ユーザーはレポートメッセージアドインを使用して、web 上の outlook でメッセージを microsoft に報告できます。

   - **Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。

      [**このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。 表示されるボックスに、Office 365 に既に存在する既存のメールボックスの電子メールアドレスを入力します。 これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。

      完了したら、[**確認**] をクリックします。

## <a name="message-submission-format"></a>メッセージ送信形式

カスタムメールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。 提出物の件名 (封筒のタイトル) は、次の形式である必要があります。

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

"Saf Etyapiaction:

- 迷惑メール = 1
- NotJunk = 2
- フィッシング = 3

次の例に示します。

- メッセージはフィッシングとして報告されています。
- ネットワークメッセージ ID は49871234-6dc6-43e8-abcd-08d797f20abe です。
- 送信者の IP は167.220.232.101 です。
- From アドレスは test@contoso.com です。
- メッセージの電子メールの件名は "test フィッシング提出" です。

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

この形式に従っていないメッセージは、送信ポータルで適切に表示されません。
