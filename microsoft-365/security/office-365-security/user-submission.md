---
title: ユーザー申請ポリシー
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、ユーザーによって報告されたスパムおよびフィッシングメールを収集するメールボックスを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287271"
---
# <a name="user-submissions-policy"></a>ユーザー申請ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online メールボックスを持つ Microsoft 365 組織では、ユーザーが悪意のあるまたは悪意はないと報告するメッセージを受信するメールボックスを指定できます。 ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピーを受信 (カスタム メールボックスと Microsoft に送信) することができます。 この機能は、次のメッセージ報告オプションで動作します。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)

- [フィッシング報告アドイン](enable-the-report-phish-add-in.md)

- [Outlook on the web の](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 組み込みレポート (旧称: Outlook Web App)

- [iOS および Android 用の Outlook の組み込みレポート](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Outlook on [the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)でレポートが無効になっている場合、ここでユーザーの送信を有効にすると、その設定が上書きされ、ユーザーは Outlook on the web でメッセージを再び報告できます。

指定したメールボックスにメッセージを転送するサード パーティ製のメッセージ報告ツールを構成することもできます。

ユーザーが報告したメッセージを Microsoft に直接ではなくカスタム メールボックスに配信すると、管理者は管理者の送信を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。

## <a name="custom-mailbox-prerequisites"></a>カスタム メールボックスの前提条件

次の記事を使用して、ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成します。

- スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルター処理をスキップします。 [「EAC を使用して、SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を **-1** に設定するメッセージの SCL を設定するメール フロー ルールを作成する」を参照してください。

- カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。 [Office 365](set-up-atp-safe-attachments-policies.md)の Defender で安全な添付ファイルポリシーの設定を使用して、安全な添付ファイルの設定が [オフ] に設定された安全な添付ファイル ポリシー **を作成します**。

- カスタム メールボックス内のメッセージの URL スキャンを無効にします。 [Office 365](set-up-atp-safe-links-policies.md)の Defender で安全なリンク ポリシーの設定を使用して、メッセージ内の悪意のある可能性のある不明な URL に対するアクションをオフに設定した安全なリンク ポリシーを作成 **します**。

- マルウェア対策ポリシーを作成して、マルウェアゼロアワー自動消去を無効にします。 「 [セキュリティ/コンプライアンス センター&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 使用してマルウェア対策ポリシーを作成し、マルウェアゼロアワー **自動** 消去をオフに設定する」を **参照してください**。

- スパム フィルター ポリシーを作成して、カスタム メールボックスでスパムとフィッシングのゼロアワー自動消去 (ZAP) を無効にします。 「Security [& Compliance Center](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)を使用してスパム対策ポリシーを作成し、スパム ZAP とフィッシング **ZAP** の **オン** チェック ボックスをオフにする」を参照してください。

- カスタム メールボックスの迷惑メール ルールを無効にします。 [迷惑メール ルールを無効にするには、Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)メールボックスで迷惑メール設定を構成するを使用します。 無効にすると、EOP はスパム フィルターの条件アクションに基づいてメッセージを [迷惑メール] フォルダーに移動できません。メッセージを [迷惑メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動します。

メールボックスが該当する前提条件を満たしていることを確認した後、セキュリティ [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) コンプライアンス センターを使用してユーザー送信メールボックスを構成します (この記事内)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage> .

- ユーザーの提出の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。
  - Exchange Online **での**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。

- Exchange Online PowerShell にアクセスする必要があります。 使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合、送信メールボックスを指定すると、次のようなエラーが表示されます。

  > ドメイン内のメール アドレスを指定する

  Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Exchange Online のクライアント アクセス規則](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>セキュリティ/コンプライアンス センター&使用して、ユーザーの送信メールボックスを構成する

1. セキュリティ/コンプライアンス センター&、脅威 **管理ポリシーのユーザー提出に** \>  \> **移動します**。

2. 表示される **[ユーザーの提出** ] ページで、次のいずれかのオプションを選択します。

   1. **Outlook** のレポート メッセージ機能を有効にする (推奨) : Outlook on the web でレポート メッセージ アドイン、Report Phishing アドイン、または組み込みのレポートを使用する場合は、このオプションを選択し、次の設定を構成します。

      - **エンド ユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。 表示される **[確認メッセージの** カスタマイズ] フライアウトで、次の設定を構成します。

      - **Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in. 変数 %type% を使用して、提出の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。

        既に説明した通り、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。

        > 電子メールは分析のために Microsoft に送信されます。 一部のメールには、個人情報や機密情報が含まれている場合があります。

      - **After submission**: Click ![ Expand icon ](../../media/scc-expand-icon.png) . [タイトル **]** **および** [確認] メッセージ ボックスに、レポート メッセージ アドインまたは Report Phishing アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 提出の種類を含めるには、変数 %type% を使用できます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[ **ユーザー** の提出] ページで [元 **に戻す] をクリック** します。

      - **報告されたメッセージの送信先**: 次のいずれかの選択を行います。

        - **Microsoft (推奨)**: ユーザー送信メールボックスは使用されません (報告されたメッセージはすべて Microsoft に送信されます)。

        - **Microsoft とカスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 ユーザーの送信は、分析のために Microsoft に送信され、管理者またはセキュリティ運用チームが分析するカスタム メールボックスに移動します。

        - **カスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを送信する場合に使用します。 管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。

        > [!NOTE]
        > 米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。 その他の 2 つのオプションは無効です。

      完了したら、[確認] をクリック **します**。

      > [!CAUTION]
      > Outlook on the web メールボックス ポリシーを使用して [Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) で迷惑メール報告を無効にしているが、Microsoft にメッセージを報告する前の設定のいずれかを構成した場合、ユーザーはレポート メッセージ アドインまたは Report Phishing アドインを使用して Outlook on the web の Microsoft にメッセージを報告できます。

   - **Outlook** の [メッセージの報告] 機能を無効にする: Outlook on the web のレポート メッセージ アドイン、フィッシング報告アドイン、または組み込みのレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を構成します。

      [この **カスタム メールボックスを使用して、報告されたユーザーの提出を受信する] を選択します**。 表示されるボックスに、既存のメールボックスが既に 365 に存在する電子メール Office入力します。 これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。

      完了したら、[確認] をクリック **します**。

## <a name="message-submission-format"></a>メッセージ送信形式

カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。 提出の件名 (封筒のタイトル) は、次の形式である必要があります。

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction は、次のいずれかの整数値です。

- 1: 迷惑メール
- 2: 迷惑メールではない
- 3: フィッシング

次の例では、

- メッセージがフィッシングとして報告されています。
- ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。
- Sender IP は 167.220.232.101 です。
- From アドレスがtest@contoso.com。
- メッセージの件名は「フィッシングの送信のテスト」です。

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

この形式に従ってないメッセージは、提出ポータルに正しく表示されません。
