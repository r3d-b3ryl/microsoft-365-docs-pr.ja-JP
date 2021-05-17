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
ms.openlocfilehash: 321e27f22295a4da17d0eb37b477a1dc7b779d38
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644766"
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

- [Web 上の Outlookに](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)組み込みのレポート (以前は Outlook Web App)

- [iOS と Android Outlookの組み込みレポート](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > web 上の[](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)Outlook でレポートが無効になっている場合、ここでユーザーの申請を有効にすると、その設定が上書きされ、ユーザーは web 上の Outlookでメッセージを報告できます。

指定したメールボックスにメッセージを転送するサード パーティ製のメッセージ レポート ツールを構成することもできます。

Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。

## <a name="custom-mailbox-prerequisites"></a>カスタム メールボックスの前提条件

ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。

- スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。 [「EAC を使用して、SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を **-1** に設定するメッセージの SCL を設定するメール フロー ルールを作成する」を参照してください。

- カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。 [Defender [for セーフ](set-up-safe-attachments-policies.md)の添付ファイル ポリシーの設定Office 365を使用して、セーフ 添付ファイルポリシーを作成し、[添付ファイルの不明なマルウェアの応答] の [セーフ]**を設定します**。

- カスタム メールボックス内のメッセージの URL スキャンを無効にします。 [[Defender for Office 365](set-up-safe-links-policies.md)で セーフ リンク ポリシーを設定する] を使用して、[メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する] の設定を [オフ] に設定して セーフ リンク ポリシーを作成 **します**。

- マルウェアゼロ時間自動削除を無効にするマルウェア対策ポリシーを作成します。 「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) センター」を参照してマルウェア対策ポリシーを作成し、[マルウェアゼロ時間 **自動削除** ] を [オフ] に **設定します**。

- スパム フィルター ポリシーを作成して、カスタム メールボックス内のスパムとフィッシングのゼロ時間自動削除 (ZAP) を無効にします。 「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)センター」を参照してスパム対策ポリシーを作成し、[スパム ZAP とフィッシング **ZAP** のオン] チェック ボックス **をオフにします**。

- カスタム メールボックスで迷惑メール ルールを無効にします。 迷惑[メール ルールを無効にするには、Exchange Onlineの](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール設定を構成するを使用します。 無効にすると、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できません **メッセージ** を迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。

メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、セキュリティ & コンプライアンス センターを使用してユーザー申請 [メールボックスを構成](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) します (この記事)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ユーザー申請] ページに **直接移動するには** 、 を使用します <https://protection.office.com/userSubmissionsReportMessage> 。

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。
  - **[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。

- PowerShell へのアクセスExchange Online必要です。 使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。

  > ドメイン内の電子メール アドレスを指定する

  PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [クライアント アクセス ルール (Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>コンプライアンス センターのセキュリティ &を使用して、ユーザー申請メールボックスを構成する

1. セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー \> **の [ユーザー** の申請 \> **] に移動します**。

2. 表示される **[ユーザーの申請]** ページで、次のいずれかのオプションを選択します。

      1. **Outlook (推奨)** のレポート メッセージ機能を有効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートを使用する場合は、このオプションを選択し、次の設定を構成します。

    - **エンド ユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。 表示される **[確認メッセージのカスタマイズ** ] フライアウトで、次の設定を構成します。

        - **提出前**: [**タイトル**] および [確認] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。  変数 %type% を使用して、申請の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。

          既に説明した通り、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。

          > 電子メールは分析のために Microsoft に送信されます。 一部の電子メールには、個人情報または機密情報が含まれている場合があります。

        - **申請後:**[展開] ![ アイコンをクリックします ](../../media/scc-expand-icon.png) 。 [タイトル **] および** **[確認** ] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 変数 %type% を使用して、申請の種類を含めできます。

      完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[ユーザー申請] **ページ** の [復元 **] をクリック** します。
    
    - **エンド ユーザーレポートオプションをカスタマイズする**: このリンクをクリックします。 表示される **[エンドユーザーレポート オプションのカスタマイズ]** フライアウトで、[迷惑メールレポートオプション] の説明テキストを入力します。 
    
      [ **メッセージの報告時に表示するオプション] で、** 次のオプションの中から少なくとも 1 つを選択します。
        - **レポートを送信する前に確認する**
        - **レポートを自動的に送信する**
        - **レポートを送信しない**
       
      完了したら、**[保存]** をクリックします。

        - **報告されたメッセージを送信する**: 次のいずれかの選択を行います。

        - **Microsoft (推奨)**: ユーザー申請メールボックスが使用されていません (報告されたメッセージはすべて Microsoft に送信されます)。

        - **Microsoft とカスタム メールボックスの** 両方 : 表示されるボックスに、既存のメールボックスの電子メール Exchange Onlineします。 配布グループは許可されません。 ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。

        - **カスタム メールボックスのみ**: 表示されるボックスに、既存のメールボックスの電子メール アドレスをExchange Onlineします。 配布グループは許可されません。 このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。 管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。

          > [!NOTE]
          > 米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。 他の 2 つのオプションは無効になっています。

          > [!NOTE]
          > 組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。

      完了したら、[確認] を **クリックします**。

      > [!CAUTION]
      > web メールボックス ポリシーで Outlook を使用して web 上の[Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)で迷惑メール報告を無効にしたが、Microsoft にメッセージを報告する前の設定のいずれかを構成した場合、ユーザーはレポート メッセージ アドインまたはレポート フィッシング アドインを使用して、Web 上の Outlook で Microsoft にメッセージを報告できます。


    2. **Outlook** のレポート メッセージ機能を無効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を構成します。

       [この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。 表示されるボックスに、既存のメールボックスの電子メール アドレスを入力します。Office 365。 これは、電子メールを受信できる既存Exchange Onlineメールボックスである必要があります。

       完了したら、[確認] を **クリックします**。

## <a name="message-submission-format"></a>メッセージ送信形式

カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。 申請の件名 (封筒のタイトル) は、次の形式である必要があります。

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction は次のいずれかの整数値です。

- 1: 迷惑メール
- 2: 迷惑メールではない
- 3: フィッシング

次の例では、次の手順を実行します。

- メッセージがフィッシングとして報告されています。
- ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。
- Sender IP は 167.220.232.101 です。
- From アドレスが test@contoso.com。
- メッセージの件名は"フィッシング申請のテスト" です。

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

この形式に従ってないメッセージは、申請ポータルに正しく表示されません。
