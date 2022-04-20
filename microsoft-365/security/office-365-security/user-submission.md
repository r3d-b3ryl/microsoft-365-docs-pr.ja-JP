---
title: ユーザーが報告したメッセージ設定
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 管理者は、ユーザーによって報告されたスパムやフィッシングメールを収集するようにメールボックスを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2e57c5dbfb8738eb9e554a3207679bfd48c6f60
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64970905"
---
# <a name="user-reported-message-settings"></a>ユーザーが報告したメッセージ設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineメールボックスを持つMicrosoft 365組織では、ユーザーが悪意のある、または悪意のないものとして報告するメッセージを受信するメールボックスを指定できます。 ユーザーがさまざまなレポート オプションを使用してメッセージを報告する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスのみに送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信したりできます。 この機能は、次のメッセージ レポート オプションで機能します。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)
- [レポート フィッシング アドイン](enable-the-report-phish-add-in.md)
- [サード パーティのレポート ツール](#third-party-reporting-tools)

ユーザーが報告したメッセージを Microsoft に直接ではなくカスタム メールボックスに配信すると、管理者は [管理者の申請](admin-submission.md)を使用して選択的に手動でメッセージを Microsoft に報告できます。 これらの設定は、以前はユーザー申請ポリシーと呼ばれていた。

  > [!NOTE]
  > [Outlook on the webで](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーから報告されたメッセージを有効にすると、その設定が上書きされ、ユーザーはOutlook on the webでメッセージを再度報告できるようになります。

## <a name="custom-mailbox-prerequisites"></a>カスタム メールボックスの前提条件

次の記事を使用して、ユーザーが報告したメッセージをカスタム メールボックスに移動するために必要な前提条件を構成します。

- Exchange メール フロー ルールを作成して、スパム信頼レベルを設定することで、カスタム メールボックスのスパム フィルター処理をスキップします。 [EAC を使用して、SCL をスパム フィルターのバイパスに設定するメッセージの SCL を設定するメール フロー ルールを作成](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)する方法に関 **するページを** 参照してください。

- マルウェアのゼロ時間自動消去 (ZAP) がオフになっているカスタム メールボックスを含む [マルウェア対策ポリシーを作成](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)します (**[保護設定]** セクション \> [**マルウェアの 0 時間の自動消去を有効にする]** が選択されていません)。

- スパムの ZAP とフィッシング詐欺の ZAP がオフになっているカスタム メールボックスを含む [スパム対策ポリシーを作成](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)します (**ゼロ時間自動消去** セクション\>**有効ゼロ時間自動消去 (ZAP)** が選択されていません)。

Microsoft Defender for Office 365がある場合は、高度なフィルター処理がメッセージを報告するユーザーに影響を与えないように、次の設定も構成する必要があります。

- [セーフ リンク](set-up-safe-links-policies.md) スキャンがオフになっているカスタム メールボックスを含む セーフ リンク ポリシーを作成します ([メッセージ] セクション **で、悪意のある可能性のある不明な URL のアクションを選択** します\>**)。**

- [セーフ添付ファイル](set-up-safe-attachments-policies.md)のスキャンがオフになっているカスタム メールボックスを含むセーフ添付ファイル ポリシーを作成します (**[添付ファイルの不明なマルウェアの応答**] セクション\>を **オフ** セーフ)。

メールボックスが適用可能なすべての前提条件を満たしていることを確認したら、この記事の手順を使用して、ユーザー提出メールボックスを構成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - [Microsoft 365 Defender ポータルのアクセス許可で組織の](permissions-microsoft-365-security-center.md)**管理** または **セキュリティ管理者**。

- Exchange Online PowerShell にアクセスする必要があります。 使用しようとしているアカウントに powerShell Exchange Onlineアクセスできない場合は、送信メールボックスを指定するときに次のようなエラーが表示されます。

  > ドメイン内の電子メール アドレスを指定する

  Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Onlineのクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Microsoft 365 Defender ポータルを使用して、ユーザー申請メールボックスを構成する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー] &ルール** \> **の [脅威ポリシー** \> **] [ユーザーが報告したメッセージの設定**] の [**その他]** セクションに移動します。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

2. [**ユーザー申請]** ページで表示される内容は、[**Microsoft Outlook レポート メッセージ] ボタン** の設定が **[オフ]** または **[オン]** のどちらであるかによって決まります。

   - **Microsoft Outlook[レポート メッセージ] ボタン** \> **を**![オンに切り替えます。](../../media/scc-toggle-on.png): レポート メッセージ アドイン、レポート フィッシング アドイン、または組み込みのレポートをOutlook on the webで使用し、次の設定を構成する場合は、このオプションを選択します。
     - **報告されたメッセージの送信先**: 次のいずれかのオプションを選択します。
       - **Microsoft**: ユーザー提出メールボックスは使用されません (報告されたすべてのメッセージは Microsoft に送信されます)。
       - **Microsoft と組織のメールボックス**: 表示されるボックスに、既存のExchange Online メールボックスのメール アドレスを入力します。 配布グループは許可されません。 ユーザーの提出は、分析のために Microsoft と、分析する管理者またはセキュリティ運用チームのカスタム メールボックスの両方に送信されます。
       - **組織のメールボックス**: 表示されるボックスに、既存のExchange Online メールボックスのメール アドレスを入力します。 配布グループは許可されません。 このオプションは、最初にメッセージを分析するために管理者またはセキュリティ運用チームのみに移動する場合に使用します。 管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。

          > [!IMPORTANT]
          > 米国政府機関 (GCC、GCC High、DoD) は、**自分の組織のメールボックス** のみを構成できます。 他の 2 つのオプションは無効になっています。
          >
          > 組織がカスタム メールボックスのみに送信するように構成されている場合、報告されたメッセージは再スキャン用に送信されず、ユーザー報告メッセージ ポータルの結果は常に空になります。

       **[報告されたメッセージの送信**] で選択した値に関係なく、次の設定を使用できます。

       - **ユーザーが自分のメッセージを Microsoft に報告するかどうかを選択できるようにする**
       - **[ユーザーが使用できるレポート オプションの選択** ] セクション: 次のオプションのうち、少なくとも 1 つを選択します。
         - **メッセージを送信する前に質問する**
         - **常にメッセージを報告する**
         - **メッセージを報告しない**

          > [!CAUTION]
          > Outlook on the webメールボックス ポリシーを使用して[Outlook on the webで迷惑メール レポートを無効にした](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)が、以前の設定のいずれかを構成して Microsoft にメッセージを報告した場合、ユーザーはレポート メッセージ アドインまたはフィッシング報告アドインを使用して、Outlook on the webで Microsoft にメッセージを報告できます。

     **Microsoft Outlook レポート メッセージ ボタン** の設定![を **オンのままに**](../../media/scc-toggle-on.png)して、エンド ユーザーが検疫ポータルから誤検知メッセージを報告できるようにします。

     - **[ユーザー レポート エクスペリエンス] セクション**
       - **[レポート] タブの前** : [ **タイトル** ] ボックスと [ **メッセージ本文** ] ボックスに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 変数 %type% を使用して、送信の種類 (迷惑メールやフィッシングなど) を含めることができます。
       - **[レポート] タブの後** : [ **タイトル** ] と [ **確認] メッセージ** ボックスに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 変数 %type% を使用して、送信の種類を含めることができます。
       - **ユーザーがフィッシングを報告した場合にのみ表示** する:メールがフィッシングとして報告された場合にのみメッセージを表示する場合は、このオプションをオンにします。 そうでない場合は、チェックされたメッセージが任意の種類のレポートに対して表示されます。

       ページに示すように、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。

          > 電子メールは、分析のためにそのまま Microsoft に送信されます。 一部の電子メールには、個人情報や機密情報が含まれている場合があります。

   - **Microsoft Outlook レポート メッセージ ボタン** \> **をオフ**![に切り替えます。](../../media/scc-toggle-off.png)このオプションは、レポート メッセージ アドイン、レポート フィッシング アドイン、または組み込みのレポートの代わりにサード パーティ製のレポート ツールをOutlook on the webで使用する場合に選択し、次の設定を構成します。
     - **[このカスタム メールボックスを使用して、ユーザーから報告された申請を受信する**] を選択します。 表示されるボックスに、電子メールを受信できる既存のExchange Online メールボックスのメール アドレスを入力します。

   - **[検疫レポート メッセージ] ボタン**: エンド ユーザーが検疫からメッセージを報告できるようにする場合は、この機能を有効にします。

3. 完了したら、[ **確認**] をクリックします。 これらの値をクリアするには、[ **復元**] をクリックします。

## <a name="third-party-reporting-tools"></a>サード パーティのレポート ツール

サード パーティのメッセージ レポート ツールを構成して、報告されたメッセージをカスタム メールボックスに送信できます。 これを行うには、[**Microsoft Outlook レポート メッセージ] ボタン** の設定を **[オフ]** に設定し、**自分の組織のメールボックス** を任意のOffice 365 メールボックスに設定します。

唯一の要件は、元のメッセージが .EML または .カスタム メールボックスに送信されるメッセージの MSG 添付ファイル (圧縮されていない) (元のメッセージをカスタム メールボックスに転送するだけではありません)。 

 > [!NOTE]
 > 電子メールに複数のメール添付ファイルが存在する場合、送信は破棄されます。 1 つのメール添付ファイルを含むメールのみがサポートされます。

メッセージの書式設定の要件については、次のセクションで説明します。 書式設定は省略可能ですが、所定の形式に従わない場合、レポートは常にフィッシングとして送信されます。

## <a name="message-submission-format"></a>メッセージ送信形式

元の添付メッセージを正しく識別するために、カスタム メールボックスに送信されるメッセージには特定の書式設定が必要です。 メッセージがこの形式を使用しない場合、添付された元のメッセージは常にフィッシング送信として識別されます。

元の添付メッセージの報告された理由を指定する場合、カスタム メールボックスに送信されるメッセージ (添付ファイルを変更しない) は、件名 (封筒タイトル) で次のいずれかのプレフィックスで始まる必要があります。

- 1|または迷惑メール:
- 2|または迷惑ではない:
- 3|またはフィッシング:

次に例を示します。

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- これらのメッセージはどちらも、件名に基づいて迷惑メールとして報告されています。
- 残りは無視されます。

この形式に従わないメッセージは、申請ポータルに正しく表示されません。
