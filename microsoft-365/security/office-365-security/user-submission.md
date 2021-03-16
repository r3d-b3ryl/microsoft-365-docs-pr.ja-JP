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
ms.openlocfilehash: 37b473e2cfffff3984ff81245f09e98ee18685ea
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826200"
---
# <a name="user-submissions-policy"></a>ユーザー申請ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online メールボックスを使用する Microsoft 365 組織では、悪意のあるメッセージまたは悪意ないメッセージを受信するメールボックスを指定できます。 ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信することができます。 この機能は、次のメッセージ レポート オプションで動作します。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)

- [レポートフィッシング アドイン](enable-the-report-phish-add-in.md)

- [Outlook on the web の組み](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 込みレポート (以前は Outlook Web App)

- [Outlook for iOS および Android の組み込みレポート](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Outlook on [the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)でレポートが無効になっている場合は、ここでユーザー申請を有効にすると、その設定が上書きされ、ユーザーは Outlook on the web でメッセージを再び報告できます。

指定したメールボックスにメッセージを転送するサード パーティ製のメッセージ レポート ツールを構成することもできます。

Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。

## <a name="custom-mailbox-prerequisites"></a>カスタム メールボックスの前提条件

ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。

- スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。 [「EAC を使用して、SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を **-1** に設定するメッセージの SCL を設定するメール フロー ルールを作成する」を参照してください。

- カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。 [Defender for Office [365](set-up-atp-safe-attachments-policies.md)で安全な添付ファイル ポリシーを設定する] を使用して、[安全な添付ファイルの不明なマルウェアの応答をオフにする] を設定して安全な添付ファイル ポリシー **を作成します**。

- カスタム メールボックス内のメッセージの URL スキャンを無効にします。 [[Defender for Office 365]](set-up-atp-safe-links-policies.md)で [安全なリンクポリシーを設定する] を使用して、[メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する] の [オフ] を設定して安全なリンク ポリシーを作成 **します**。

- マルウェアゼロ時間自動削除を無効にするマルウェア対策ポリシーを作成します。 「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) センター」を参照してマルウェア対策ポリシーを作成し、[マルウェアゼロ時間 **自動削除** ] を [オフ] に **設定します**。

- スパム フィルター ポリシーを作成して、カスタム メールボックス内のスパムとフィッシングのゼロ時間自動削除 (ZAP) を無効にします。 「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)センター」を参照してスパム対策ポリシーを作成し、[スパム ZAP とフィッシング **ZAP** のオン] チェック ボックス **をオフにします**。

- カスタム メールボックスで迷惑メール ルールを無効にします。 [[Exchange Online メールボックスの迷惑メール設定の構成] を使用して、](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール ルールを無効にします。 無効にすると、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できません **メッセージ** を迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。

メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、セキュリティ & コンプライアンス センターを使用してユーザー申請 [メールボックスを構成](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) します (この記事)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ユーザー申請] ページに **直接移動するには** 、 を使用します <https://protection.office.com/userSubmissionsReportMessage> 。

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。
  - Exchange **Online の**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。

- Exchange Online PowerShell にアクセスする必要があります。 使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。

  > ドメイン内の電子メール アドレスを指定する

  Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Exchange Online のクライアント アクセス ルール](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>コンプライアンス センターのセキュリティ &を使用して、ユーザー申請メールボックスを構成する

1. セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー \> **の [ユーザー** の申請 \> **] に移動します**。

2. 表示される **[ユーザーの申請]** ページで、次のいずれかのオプションを選択します。

      1. **Outlook のレポート** メッセージ機能を有効にする (推奨) : レポート メッセージ アドイン、レポート フィッシング アドイン、または Outlook on the web の組み込みレポートを使用する場合は、このオプションを選択し、次の設定を構成します。

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
        -  **レポートを送信しない** \
   完了したら、**[保存]** をクリックします。
              - **報告されたメッセージを送信する**: 次のいずれかの選択を行います。
              - **Microsoft (推奨)**: ユーザー申請メールボックスが使用されていません (報告されたメッセージはすべて Microsoft に送信されます)。
              - **Microsoft とカスタム メールボックスの** 両方 : 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。
              - **カスタム メールボックスのみ**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。 管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。

        > [!NOTE]
        > 米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。 他の 2 つのオプションは無効になっています。

      完了したら、[確認] を **クリックします**。

      > [!CAUTION]
      > [Outlook on the](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Web メールボックス ポリシーを使用して Outlook on the web で迷惑メールレポートを無効にしたが、以前の設定のいずれかを構成して Microsoft にメッセージを報告した場合、ユーザーはレポート メッセージ アドインまたはレポートフィッシング アドインを使用して Outlook on the Web で Microsoft にメッセージを報告できます。


    1. **Outlook** のレポート メッセージ機能を無効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または Outlook on the web の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を構成します。

          [この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。 表示されるボックスに、365 に既に存在する既存のメールボックスの電子メール Officeします。 これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。

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

