---
title: スパムおよびフィッシング メッセージのユーザー送信用のメールボックスを指定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーによって報告されるスパム メールやフィッシング メールを収集するように、メールボックスを構成する方法について学習できます。
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826743"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Exchange Online でスパムやフィッシング メッセージのユーザーを送信するためのメールボックスを指定する

Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるとして報告を受けたり、悪意のあるものでないと報告するメッセージを受信するメールボックスを指定できます。 ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージをインターセプト (カスタム メールボックスのみに送信する) か、またはメッセージのコピーを受信 (カスタム メールボックスおよび Microsoft に送信する) ことができます。 この機能は次のメッセージ報告オプションで使用できます。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)

- [Outlook on the web (前の名)](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) の組み込みのレポートOutlook Web App)

- iOS および Android 用の Outlook の組み込みレポート

  > [!NOTE]
  > Outlook on the web でレポート [機能が無効になっている場合](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)、ユーザーの送信を有効にすると、その設定が無効になり、ユーザーは Web 上の Outlook でメッセージを再びレポートできるようになります。

指定したメールボックスにメッセージを転送する、サード パーティのメッセージ レポート ツールを構成することもできます。

ユーザーから報告されたメッセージを直接 Microsoft に送信するのではなく、カスタムのメールボックスに送信すると、管理者は管理者の申請を使用して、管理者が選択的に Microsoft にメッセージを [報告することができます](admin-submission.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 ユーザーの申請ページに **直接進むには、** 次のコマンドを使用します <https://protection.office.com/userSubmissionsReportMessage> 。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - ユーザーの送信の構成を変更するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - ユーザーの送信に対する読み取り専用アクセスを行う場合は、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>セキュリティ コンプライアンス センター &を使用してユーザー送信メールボックスを構成する

1. セキュリティ コンプライアンス センター&で、[脅威管理 **ポリシー ユーザー** \> **による** \> **送信] に移動します**。

2. 表示される **[ユーザーの提出** ] ページで、次のいずれかのオプションを選択します。

   a. **Outlook でメッセージ報告機能を有効にする (推奨)**: 迷惑メール報告アドインまたは Outlook on the web の組み込みのレポートを使用する場合は、このオプションを選択してから、次の設定を構成します。

      - **エンド ユーザー確認メッセージをカスタマイズします**: このリンクをクリックします。 表示される **確認メッセージのポ** ップアップで、次の設定を構成します。

      - **送信前**: タイトルと **確認** メッセージ **ボックスに** 、ユーザーがレポート メッセージ アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 変数 %type% を使用して、提出の種類 (迷惑メール、迷惑メール以外、フィッシングなど) を含めることが可能です。

        既に説明したとおり、報告されたメッセージを Microsoft に送信するオプションを選択した場合、次のテキストも通知に追加されます。

        > メールは、分析のためにその情報をそのものとして Microsoft に送信されます。 個人または機密情報が含まれているメールの中には、一部のメールが含まれる場合があります。

      - **提出後**: 展開 ![ アイコンをクリックします ](../../media/scc-expand-icon.png) 。 [タイトル **]** および **[確認] メッセージ ボックスに** 、ユーザーが報告メッセージ アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 変数 %type% を使用して、提出の種類を含めることができます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[ **ユーザーの申請** を戻 **す] ページの [戻る] をクリック** します。

      - **報告されたメッセージの送信**: 次のいずれかを選択します:

        - **Microsoft (推奨)**: ユーザー送信メールボックスは使用されません (報告されたすべてのメッセージは Microsoft に送信されます)。

        - **Microsoft とカスタム メールボックス**: 表示されるボックスに既存の Exchange Online メールボックスのメール アドレスを入力します。 配布グループは許可されません。 ユーザーの送信は、分析のため Microsoft と、管理者またはセキュリティ運用チームのカスタム メールボックスの両方に移動して分析します。

        - **カスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 このオプションは、最初に分析を目的として、メッセージを管理者またはセキュリティ運用チームにのみ送信する場合に使用します。 管理者がユーザーを転送しない限り、メッセージは Microsoft には送信されません。

        > [!NOTE]
        > 米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。 その他の 2 つのオプションは無効になります。 

      完了したら、[確認] をクリック **します**。

      > [!CAUTION]
      > Web 上の [Outlook のメールボックス ポリシーを使用して Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 上の Outlook で迷惑メール レポート機能を無効にしているが、メッセージを Microsoft に報告するために以前のいずれかの設定を構成した場合、ユーザーはメッセージ報告アドインを使用して、Outlook on the web でメッセージを Microsoft に報告できます。

   - **Outlook のメッセージ報告機能を無効にします。レポート**メッセージ アドインまたは Outlook on the web の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択してから、次の設定を構成します。

      [ **このカスタム メールボックスを使用して、ユーザーの報告された送信を受信する] を選きます**。 表示されるボックスに、既に存在するメール アドレスのメール アドレスを Officeします。 これは、電子メールを受信できる、Exchange Online の既存のメールボックスである必要があります。

      完了したら、[確認] をクリック **します**。

## <a name="message-submission-format"></a>メッセージ送信の形式

カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。 申請のサブジェクト (エンベロープ タイトル) は次の形式である必要があります。

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction は、次のいずれかの整数値です。

- 1: 迷惑メール
- 2: NotJunk
- 3: フィッシング

次に例を示します。

- メッセージはフィッシングとして報告されています。
- ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。
- 送信者の IP は、167.220.232.101 です。
- 送信元アドレスはtest@contoso.com。
- メッセージの件名が「フィッシングのテスト」である

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

この形式に従っていないメッセージは、申請ポータルに正しく表示されません。
