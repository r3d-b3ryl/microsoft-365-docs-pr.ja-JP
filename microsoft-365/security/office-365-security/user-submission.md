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
description: 管理者は、ユーザーによって報告されるスパムメールやフィッシングメールを収集するメールボックスを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a39c6a3b287933ff79f94b00e364d7a45378bd1f
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933085"
---
# <a name="user-submissions-policy"></a>ユーザー申請ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

メールボックスMicrosoft 365組織Exchange Online、悪意のあるメッセージまたは悪意ないメッセージを受信するメールボックスを指定できます。 ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信することができます。 この機能は、次のメッセージ レポート オプションで動作します。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)
- [レポートフィッシング アドイン](enable-the-report-phish-add-in.md)
- [サードパーティのレポート ツール](#third-party-reporting-tools)

Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。

  > [!NOTE]
  > web 上の[](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)Outlook でレポートが無効になっている場合、ここでユーザーの申請を有効にすると、その設定が上書きされ、ユーザーは web 上の Outlookでメッセージを報告できます。

## <a name="custom-mailbox-prerequisites"></a>カスタム メールボックスの前提条件

ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。

- スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。 [「EAC を使用してメッセージの SCL を設定し、SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を [スパム フィルターのバイパス] に設定するメール フロー ルールを **作成する」を参照してください**。

- [添付ファイルセーフスキャン](set-up-safe-attachments-policies.md)がオフになっているカスタム メールボックスを含む セーフ 添付ファイル ポリシーを作成します (セーフ **添付** ファイルの不明なマルウェア応答セクション \> **オフ**)。

- セーフ リンク [スキャン](set-up-safe-links-policies.md)がオフになっているカスタム メールボックスを含む セーフ リンク ポリシーを作成します ([メッセージ] セクションで不明な可能性のある悪意のある **URL** のアクションを選択 \> **します**)。

- [マルウェアの](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)ゼロ時間自動削除 (ZAP) がオフになっているカスタム メールボックスを含むマルウェア対策ポリシーを作成します **([** 保護設定] セクション [マルウェアの 0 時間自動削除を有効にする] は \> 選択されません)。

- [](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)スパム用 ZAP とフィッシング用 ZAP がオフになっているカスタム メールボックスを含むスパム対策ポリシーを作成します (ゼロ時間自動削除セクション [有効な 0 時間自動削除 \> **(ZAP) は** 選択されません)。

- カスタム メールボックスで迷惑メール ルールを無効にします。 迷惑[メール ルールを無効にするには、Exchange Onlineの](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール設定を構成するを使用します。 無効にした後、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できませんメッセージを迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。

メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、この記事の手順を使用してユーザー申請メールボックスを構成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。 [申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - **Defender ポータル** の **組織** の管理 [またはセキュリティMicrosoft 365管理者です](permissions-in-the-security-and-compliance-center.md)。
  - **[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。

- PowerShell へのアクセスExchange Online必要です。 使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。

  > ドメイン内の電子メール アドレスを指定する

  PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [クライアント アクセス ルール (Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Defender ポータルMicrosoft 365を使用してユーザー申請メールボックスを構成する

1. [Defender Microsoft 365] ポータルで、[ポリシー] &[脅威ポリシー **] [その他**] セクション [ユーザーが報告したメッセージの設定] [ユーザーの申請] \>  \>  \>  \> **に移動します**。

2. [ユーザーの **申請] ページ** で、表示される情報は **、[Microsoft** レポート メッセージ] Outlook設定が [オフ] または [オン] のOutlook **によって** 決 **まります**。

   - **[Microsoft Outlook レポート メッセージ] ボタン** \>**On** ![トグルオン: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートを使用する場合は、このオプションを選択し、次の設定 ](../../media/scc-toggle-on.png) を構成します。
     - **報告されたメッセージを送信する**: 次のいずれかのオプションを選択します。
       - **Microsoft**: ユーザー申請メールボックスは使用されません (報告されたメッセージはすべて Microsoft に送信されます)。
       - **Microsoft と組織のメールボックス**: 表示されるボックスに、既存のメールボックスの電子メール Exchange Onlineします。 配布グループは許可されません。 ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。
       - **組織のメールボックス**: 表示されるボックスに、既存のメールボックスのメール アドレスをExchange Onlineします。 配布グループは許可されません。 このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。 管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。

          > [!IMPORTANT]
          >
          > 米国政府機関 (GCC、GCC、DoD) は、自分の組織のメールボックス **のみを構成できます**。 他の 2 つのオプションは無効になっています。
          >
          > 組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。

       [報告されたメッセージの送信先] で選択した値に関係 **なく、次** の設定を使用できます。

       - **ユーザーが自分のメッセージを Microsoft に報告する場合の選択を許可する**
       - **[ユーザーが使用できるレポート オプションを選択** する] セクション: 次のオプションの中から少なくとも 1 つを選択します。
         - **メッセージを送信する前に確認する**
         - **常にメッセージを報告する**
         - **メッセージを報告しない**

          > [!CAUTION]
          > web メールボックス ポリシーで Outlook を使用して web 上の[Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)で迷惑メール報告を無効にしたが、Microsoft にメッセージを報告するように以前の設定を構成した場合、ユーザーはレポート メッセージ アドインまたはレポート フィッシング アドインを使用して、web 上の Outlook で Microsoft にメッセージを報告できます。

     - **[ユーザー レポートエクスペリエンス] セクション**
       - **[レポート** の前に]タブ: [タイトル] および [メッセージ] 本文ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 変数 %type% を使用して、申請の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。
       - **[レポート後**] タブ:  [タイトル] および [確認] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 変数 %type% を使用して、申請の種類を含めできます。

       ページに示すように、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。

          > 電子メールは分析のために Microsoft に送信されます。 一部の電子メールには、個人情報または機密情報が含まれている場合があります。

   - **[Microsoft Outlook レポート メッセージ] ボタン** \>**Off** ![トグルオフ: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を ](../../media/scc-toggle-off.png) 構成します。
     - [この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。 表示されるボックスに、メールを受信できる既存のメールボックスのExchange Onlineを入力します。

   完了したら、[確認] を **クリックします**。 これらの値をクリアするには、[復元] を **クリックします。**

## <a name="third-party-reporting-tools"></a>サードパーティのレポート ツール

サード パーティ製のメッセージ レポート ツールを構成して、報告されたメッセージをカスタム メールボックスに送信できます。 唯一の要件は、元のメッセージがカスタム メールボックスに送信されるメッセージの添付ファイルとして含まれる場合です (元のメッセージをカスタム メールボックスに転送するだけではない)。

メッセージの書式設定の要件については、次のセクションで説明します。 書式設定は省略可能ですが、指定された形式に従う場合、レポートは常にフィッシングとして送信されます。

## <a name="message-submission-format"></a>メッセージ送信形式

元の添付メッセージを正しく識別するには、カスタム メールボックスに送信されるメッセージには、特定の書式が必要です。 メッセージでこの形式を使用しない場合、添付された元のメッセージは常にフィッシング申請として識別されます。

元の添付メッセージを正しく識別するために、カスタム メールボックスに送信されるメッセージは、Subject (Envelope Title) に次の構文を使用する必要があります。

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction は次のいずれかの整数値です。

- 1: 迷惑メール
- 2: 迷惑メールではない
- 3: フィッシング

この例では、次の値を使用します。

- メッセージがフィッシングとして報告されています。
- ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。
- Sender IP は 167.220.232.101 です。
- From アドレスが test@contoso.com。
- メッセージの件名は"フィッシング申請のテスト" です。

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

この形式に従らないメッセージは、申請ポータルに正しく表示されません。
