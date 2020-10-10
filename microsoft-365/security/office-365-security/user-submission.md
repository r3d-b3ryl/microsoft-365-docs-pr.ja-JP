---
title: ユーザー送信ポリシー
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
- m365-initiative-defender-office365
description: 管理者は、ユーザーによって報告されたスパムやフィッシング電子メールを収集するようにメールボックスを構成する方法について説明します。
ms.openlocfilehash: 8347463a4c3f41b6b6333d35c5b4207d1b94aabe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412564"
---
# <a name="user-submissions-policies"></a>ユーザー送信ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。 ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。 この機能は、次のメッセージレポートオプションで機能します。

- [レポートメッセージアドイン](enable-the-report-message-add-in.md)

- [Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート

- [IOS および Android 用の Outlook の組み込みレポート](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > [Web 上の outlook で](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーによる送信を有効にすると、その設定が無効になり、ユーザーは web 上の outlook でメッセージを再度レポートすることができます。

また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。

ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、 [管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。

## <a name="custom-mailbox-prerequisites"></a>カスタムメールボックスの前提条件

次の記事を使用して、ユーザーがレポートされたメッセージをカスタムメールボックスに移動するために必要な前提条件を構成します。

- スパムの信頼度を設定する exchange メールフロールールを作成して、スパムフィルタリングをスキップします。 SCL を **-1**に設定する[メッセージの scl を設定するメールフロールールを作成するには、EAC を使用](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)してください。

- マルウェア用の添付ファイルのスキャンを無効にします。 [ [設定] (または [編集])](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) を使用して、[事前に安全な添付ファイルを作成する] ポリシーを作成します。このポリシーは、 **マルウェアが有効になっている場合、添付ファイルはスキャンされません** 。

- メッセージに対する URL スキャンを無効にします。 [すべてのまたは特定の電子メールの受信者に適用される、追加 (または編集) の ATP の安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients)ポリシーを使用して、安全なリンクポリシーを作成します。 **[メッセージ内の不明な悪意のある url に対するアクション] を [** **オフ**] に設定します。

- マルウェア対策ポリシーを作成して、マルウェアのゼロ時間の自動削除を無効にします。 **マルウェアのゼロ時間自動削除**を**オフ**に設定するに[は、「セキュリティ & コンプライアンスセンターを使用してマルウェア対策ポリシーを作成する」を](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies)参照してください。

- スパム ZAP およびフィッシング ZAP のゼロ時間自動削除 (ZAP) を無効にするスパムフィルターポリシーを作成します。 「 [セキュリティ & コンプライアンスセンターを使用](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) してスパム対策ポリシーを作成 **し、スパム** zap およびフィッシング ZAP のチェックボックスをオフにする」を参照してください。

- 迷惑メールルールを無効にします。 迷惑メールルールを無効にするには、 [Exchange Online メールボックスで迷惑メールの設定を構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) します。 無効にした場合、EOP は、迷惑メールフォルダーにメッセージを移動することはできません verdict アクションによる迷惑メール **フォルダーへのメッセージの移動** またはメールボックス上のセーフリストコレクションへのメッセージの移動。

メールボックスが適用可能なすべての前提条件を満たしていることを確認したら、 [セキュリティ & コンプライアンスセンターを使用して、ユーザー送信メールボックスを構成](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) します (この記事で説明します)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ **ユーザーの送信** ] ページに直接移動するには、を使用 <https://protection.office.com/userSubmissionsReportMessage> します。

- ユーザー送信の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのユーザーの送信] に移動 \> **Policy** \> **User submissions**します。

2. 表示される [ **ユーザーの送信** ] ページで、次のいずれかのオプションを選択します。

   a. **Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。

      - **エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。 [ **確認メッセージのカスタマイズ** ] ポップアップが表示されたら、次の設定を構成します。

      - **提出前**: **タイトル** と確認の **メッセージ** ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。

        前述したように、報告されたメッセージを Microsoft に送信するオプションを選択すると、通知に次のテキストも追加されます。

        > 電子メールは、のように、分析のために Microsoft に提出されます。 メールによっては個人情報や機密情報が含まれる場合があります。

      - **送信後**: [ ![ 展開] アイコンをクリックし ](../../media/scc-expand-icon.png) ます。 [ **タイトル** ] および [ **確認メッセージ** ] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。 変数% 型% を使用して、提出の種類を含めることができます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。

      - **報告されたメッセージの送信先**: 次のいずれかの選択を行います。

        - **Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。

        - **Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。 ユーザーによる送信は、分析のために Microsoft と Microsoft の両方に、管理者またはセキュリティ運用チームのためのカスタムメールボックスに移動します。

        - **カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。 配布グループは許可されていません。 このオプションを使用するのは、最初に分析のために管理者またはセキュリティ操作チームのみにメッセージを移動する場合です。 管理者が自分を転送しない限り、メッセージは Microsoft には送られません。

        > [!NOTE]
        > 米国政府機関 (GCC、GCC、.H、DoD) は、 **カスタムメールボックス**のみを構成できます。 他の2つのオプションは無効になっています。 

      完了したら、[ **確認**] をクリックします。

      > [!CAUTION]
      > Web 上の outlook on the web メールボックスポリシーを使用して outlook の [迷惑メール報告を無効](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) にしたが、microsoft にメッセージを報告するために以前の設定のいずれかを構成した場合、ユーザーはレポートメッセージアドインを使用して、web 上の outlook でメッセージを microsoft に報告できます。

   - **Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。

      [ **このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。 表示されるボックスに、Office 365 に既に存在する既存のメールボックスの電子メールアドレスを入力します。 これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。

      完了したら、[ **確認**] をクリックします。

## <a name="message-submission-format"></a>メッセージ送信形式

カスタムメールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。 提出物の件名 (封筒のタイトル) は、次の形式である必要があります。

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

"Saf Etyapiaction" は、次のいずれかの整数型 (integer) の値です。

- 1: 迷惑メール
- 2: NotJunk
- 3: フィッシング

次の例に示します。

- メッセージはフィッシングとして報告されています。
- ネットワークメッセージ ID は49871234-6dc6-43e8-abcd-08d797f20abe です。
- 送信者の IP は167.220.232.101 です。
- From アドレスは test@contoso.com です。
- メッセージの件名行は "test フィッシング提出" です。

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

この形式に従っていないメッセージは、送信ポータルで適切に表示されません。
