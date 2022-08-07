---
title: スパム、フィッシング、悪意のあるメールとしてユーザーが報告した電子メール設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 07/19/2022
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 管理者は、カスタム メールボックス (ユーザー送信メールボックスとも呼ばれます) を識別して、ユーザーによって報告されるスパムおよびフィッシング メッセージを収集する方法について説明します。 その他の設定では、ユーザーがメッセージを報告するときに、レポート エクスペリエンスが完了します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e09b5f7d6f34ac1daa98430f1bc868b4ca644777
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276308"
---
# <a name="user-reported-message-settings"></a>ユーザーから報告されたメッセージの設定

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineメールボックスを持つ Microsoft 365 組織では、悪意のあるメッセージや悪意のないメッセージを報告したときに、カスタム _メールボックス (ユーザー送信メールボックス_ とも呼ばれます) にメールを送信できます。 ユーザーがサポートされているレポート オプションを使用して電子メール メッセージを報告する場合、管理者は、報告されたメッセージをユーザー送信メールボックスに送信するように、組織内のユーザー報告メッセージ設定を構成できます。 ユーザーが報告したメッセージをインターセプト (ユーザー送信メールボックスのみに送信) するようにユーザー送信メールボックスを構成したり、ユーザーが Microsoft にメッセージを報告するときにユーザーから報告されたメッセージのコピーを受信したりできます。 これらの設定は、以前は _ユーザー申請ポリシー_ と呼ばれていた。

ユーザーが報告したメッセージ設定とユーザー送信メールボックスは、次のメッセージ レポート オプションで機能します。

- [レポート メッセージ アドイン](enable-the-report-message-add-in.md)
- [レポート フィッシング アドイン](enable-the-report-phish-add-in.md)
- [サード パーティのレポート ツール](#third-party-reporting-tools-options)

ユーザーが報告したメッセージを Microsoft に直接送信するのではなく、ユーザー送信メールボックスに配信することで、管理者は Microsoft の [ **申請]** ページでメッセージを選択的かつ手動で <https://security.microsoft.com/reportsubmission>報告できます。 詳細については、「[管理提出](admin-submission.md)」を参照してください。

  > [!NOTE]
  > [Outlook on the webで](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーから報告されたメッセージを有効にすると、その設定が上書きされ、ユーザーは再びOutlook on the webでメッセージを報告できるようになります。

## <a name="configuration-requirements-for-the-user-submissions-mailbox"></a>ユーザー申請メールボックスの構成要件

開始する前に、次の手順で説明するように、ユーザーが報告したメッセージがフィルター処理されずにユーザー送信メールボックスに配信されるように、Exchange Online ProtectionとDefender for Office 365を構成する必要があります。

- ユーザー提出メールボックスを SecOps メールボックスとして識別します。 手順については、「[Microsoft 365 Defender ポータルを使用して、高度な配信ポリシーで SecOps メールボックスを構成](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy)する」を参照してください。

- 次の設定を使用して、ユーザー申請メールボックスのカスタムマルウェア対策ポリシーを作成します。

  - マルウェアのゼロ時間自動消去 (ZAP) をオフにします (**[保護設定]** セクション \> [ **マルウェアのゼロ時間自動消去を有効にする** ] が選択されていないか `-ZapEnabled $false` 、PowerShell で)。

  - 一般的な添付ファイルのフィルター処理を無効にします (**[保護の設定]** セクション [ **共通添付ファイル フィルター** が選択されていないか`EnableFileFilter $false`、PowerShell で有効にする] セクション\>)。
  
  手順については、「 [マルウェア対策ポリシーを作成する](configure-anti-malware-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-malware-policies)」を参照してください。

- ユーザー提出メールボックスが **Standard** または **Strict** の事前設定済みセキュリティ ポリシーに含まれていないかどうかを確認します。 手順については、「 [事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

- **Defender for Office 365**: 次の追加設定を構成します。

  - **組み込みの保護** プリセット セキュリティ ポリシーからユーザー提出メールボックスを除外します。 手順については、「 [事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

  - 動的配信を含む安全な添付ファイルのスキャンがオフになっているユーザー提出メールボックスの安全な添付ファイル ポリシーを作成します ([**安全な添付ファイルの不明なマルウェアの応答** の **設定]** \> セクション\>**はオフ** または `-Enable $false` PowerShell で)。 手順については、「[Microsoft Defender for Office 365で安全な添付ファイル ポリシーを設定](set-up-safe-attachments-policies.md)する」を参照してください。

  - 電子メールでのセーフ リンク スキャンがオフになっているユーザー送信メールボックスのセーフ リンク ポリシーを作成します (**[URL &クリック保護設定**\>をオンにする **: セーフ リンクは、ユーザーが電子メール内のリンクをクリックした場合、または** `EnableSafeLinksForEmail $false` PowerShell で既知の悪意のあるリンクの一覧を確認します)。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

メールボックスがこれらの要件を満たしていることを確認したら、この記事の残りの手順を使用して、ユーザー提出メールボックスとその他のユーザーが報告したメッセージ設定を特定します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。

  - [Microsoft 365 Defender ポータルのアクセス許可で組織の](permissions-microsoft-365-security-center.md)**管理** または **セキュリティ管理者**。

- Exchange Online PowerShell にアクセスする必要があります。 使用しようとしているアカウントに powerShell Exchange Onlineアクセスできない場合は、送信メールボックスを指定するときに次のようなエラーが表示されます。

  > ドメイン内の電子メール アドレスを指定する

  Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。

  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Onlineのクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox-for-email"></a>Microsoft 365 Defender ポータルを使用して、電子メールのユーザー送信メールボックスを構成する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー] &ルール** \> **の [脅威ポリシー** \> **] [ユーザーが報告したメッセージの設定**] の [**その他]** セクションに移動します。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

2. [ **ユーザー申請]** ページで表示される内容は、 **Microsoft Outlook の [レポート メッセージ] ボタン** の切り替えによって大きく決まります。

   - **に** ![トグル オン.](../../media/scc-toggle-on.png): Microsoft 統合レポート エクスペリエンスを使用します。これには、レポート メッセージ アドイン、レポート フィッシング アドイン、またはOutlook on the webの組み込みレポートが含まれます。

     この設定を使用すると、ユーザーは検疫ポータルから誤検知メッセージを報告することもできます。

   - **オフ** ![オフに切り替えます。](../../media/scc-toggle-off.png): Microsoft 統合レポート エクスペリエンスの代わりに、サード パーティ製のメッセージ レポート ツールを使用します。

関連する構成オプションについては、次のセクションで説明します。

### <a name="microsoft-integrated-reporting-experience-options"></a>Microsoft 統合レポート エクスペリエンス オプション

**[Microsoft Outlook レポート メッセージ] ボタン** が **[オン**![] になっている](../../media/scc-toggle-on.png)場合は、[**ユーザー申請**] ページで次の設定を使用できます。

- **[報告されたメッセージを送信する** ] セクション: 次のいずれかのオプションを選択します。

  - **Microsoft**: ユーザー レポートは、分析のために Microsoft に直接移動します。 Microsoft 365 Defender ポータルを使用して、送信者、受信者、報告元、ユーザー レポートからのメッセージの詳細などのメタデータのみがテナント管理者に提供されます。

  - **Microsoft と組織のメールボックス**: 表示されるボックスに、ユーザー送信メールボックスとして使用する既存のExchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。 ユーザー申請は分析のために Microsoft に送信され、管理者またはセキュリティ運用チームが分析するユーザー提出メールボックスに送信されます。

  - **組織のメールボックス**: 表示されるボックスに、既存のExchange Online メールボックスのメール アドレスを入力します。 配布グループは許可されません。 ユーザー申請は、分析する管理者またはセキュリティ運用チームのユーザー提出メールボックスにのみ移動します。 管理者が手動でメッセージを送信しない限り、メッセージは分析のために Microsoft に送信されません。

  > [!IMPORTANT]
  > 米国政府機関 (GCC、GCC High、DoD) 組織では、[ **報告されたメッセージを送信する** ] セクションで使用できる唯一の選択肢は **、[自分の組織] メールボックスです**。 他の 2 つのオプションは淡色表示されます。
  >
  > [Outlook on the webメールボックス ポリシー](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/configure-outlook-web-app-mailbox-policy-properties)を使用してOutlook on the webで迷惑メール レポートを無効にしたが、**Microsoft** または **Microsoft と組織のメールボックス** を選択した場合、ユーザーはレポート メッセージ アドインまたはフィッシング報告アドインを使用して、Outlook on the webで Microsoft にメッセージを報告できます。
  >
  > **[自分の組織のメールボックス**] を選択した場合、[**送信]** ページ<https://security.microsoft.com/reportsubmission>の [**ユーザーが報告したメッセージ] タブに報告されたメッセージ** が表示されます。 ただし、メッセージが再スキャンされなかったため、これらのメッセージの **結果** 値は常に空になります。
  >
  > [攻撃シミュレーション トレーニング](attack-simulation-training-get-started.md)またはサード パーティ製品を使用してフィッシング シミュレーションを行う場合は、この記事の「ユーザー提出メールボックスの構成要件」セクションで説明したように、[ユーザー提出メールボックスを](#configuration-requirements-for-the-user-submissions-mailbox) SecOps メールボックスとして構成する必要があります。 そうしないと、メッセージを報告するユーザーがフィッシング シミュレーション 製品でトレーニングの割り当てをトリガーする可能性があります。

  選択した内容に関係なく、[ **報告されたメッセージを送信** する] セクションでも次の設定を使用できます。

  - **ユーザーがレポートするかどうかを選択できるようにする**: この設定は、[ **ユーザーが使用できるレポート オプションの選択] セクションで使用できるオプションを** 制御します。

    - **ユーザーがレポートを選択するかどうかを選択** できるようにする: [ **ユーザーが使用できるレポート オプション** の選択] セクションで、設定の一部、すべて、または一部を選択できます。
    - ユーザーがレポートを選択しない **かどうかを選択** できるようにする: [**ユーザーが使用できるレポート オプション** の選択] セクションで選択できる設定は 1 つだけです。

    - **[ユーザー] セクションで使用できるレポート オプションを選択** します。
      - **メッセージを送信する前に質問する**
      - **常にメッセージを報告する**
      - **メッセージを報告しない**

- **[ユーザー レポート エクスペリエンス** ] セクション: 次の設定を使用できます。

  ページに示すように、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。

  > 電子メールは、分析のためにそのまま Microsoft に送信されます。 一部の電子メールには、個人情報や機密情報が含まれている場合があります。

  - **[レポート] タブの前** : [ **タイトル** ] ボックスと [ **メッセージ本文** ] ボックスに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 この変数 `%type%` を使用して、送信の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めることができます。
  - **[レポート] タブの後** : [ **タイトル** ] と [ **確認] メッセージ** ボックスに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。 この変数 `%type%` を使用して、送信の種類を含めることができます。

  - **ユーザーがフィッシングを報告する場合にのみ表示** する: このオプションを選択すると、ユーザーがメッセージをフィッシングとして報告した場合にのみ **、[レポート前** ] 通知と **[レポート後** ] 通知が表示されます。 それ以外の場合は、報告されたすべてのメッセージに対する通知が表示されます。

- **管理者レビュー結果のEmail通知** セクション: 次の設定を使用できます。

  - **送信者として使用Office 365メール アドレスを指定** します。 この設定を選択し、表示されるボックスに電子メール アドレスを入力します。
  
  - **通知をカスタマイズ** する: 管理者が報告されたメッセージをレビューしてマークした後に送信される電子メール通知をカスタマイズするには、このリンクをクリックします。

    表示される **[カスタマイズの確認メッセージ** ] ポップアップで、次の設定を構成します。

    - **[フィッシング]**、[ **迷惑メール]** 、[ **脅威が見つかりません** ] タブ: [一部、なし、またはすべてのタブの **結果の確認] テキスト** に、使用するカスタム テキストを入力します。
    - **[フッター** ] タブ: 次のオプションを使用できます。
      - **フッター テキスト**: 使用するカスタム メッセージ フッター テキストを入力します。
      - **会社のロゴを表示** する: このオプションを選択する前に、組織の [Microsoft 365 テーマをカスタマイズ](../../admin/setup/customize-your-organization-theme.md) してカスタム ロゴをアップロードする手順に従う必要があります。

  **[確認メッセージのカスタマイズ**] ポップアップが完了したら、[**確認**] をクリックします。

- **検疫セクションで潜在的な脅威を報告するときに、組織のエクスペリエンスをカスタマイズ** します。

  **[検疫レポート メッセージ] ボタン**: この設定が **[オン]** ![トグルオンになっていることを確認します。](../../media/scc-toggle-on.png) を使用して、ユーザーが検疫からメッセージを報告できるようにします。 それ以外の場合は、この設定 **をオフに**![切り替えます](../../media/scc-toggle-off.png)。.

**[ユーザー申請**] ページが終了したら、[保存] をクリック **します**。 設定を直前の値に復元するには、[ **復元**] をクリックします。

### <a name="third-party-reporting-tools-options"></a>サード パーティのレポート ツール オプション

Microsoft 統合レポート エクスペリエンスを無効にして、サード パーティのメッセージ レポート ツールを使用して、報告されたメッセージをユーザー提出メールボックスに送信できます。

唯一の要件は、元のメッセージが非圧縮として含まれることです。EML または .ユーザー送信メールボックスに送信されるメッセージ内の MSG 添付ファイル。 つまり、元のメッセージをユーザー送信メールボックスに転送しないでください。

> [!NOTE]
> メッセージに複数のメール添付ファイルが存在する場合、送信は破棄されます。 1 つのメール添付ファイルを含むメッセージのみがサポートされます。

メッセージの書式設定の要件については、次のセクションで説明します。 書式設定は省略可能ですが、報告されたメッセージは所定の形式に従っていません。報告されたメッセージは常にフィッシングとして識別されます。

**[Microsoft Outlook レポート メッセージ] ボタン** が **[オフ]** ![になっている場合は、オフに切り替えます。](../../media/scc-toggle-off.png) [ **ユーザー申請** ] ページでは、次の設定を使用できます。

- **Microsoft と組織のメールボックス**: 表示されるボックスに、ユーザー送信メールボックスとして使用する既存のExchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。

- **検疫セクションで潜在的な脅威を報告するときに、組織のエクスペリエンスをカスタマイズ** します。

  **[検疫レポート メッセージ] ボタン**: この設定が **[オン]** ![トグルオンになっていることを確認します。](../../media/scc-toggle-on.png) を使用して、ユーザーが検疫からメッセージを報告できるようにします。 それ以外の場合は、この設定 **をオフに**![切り替えます](../../media/scc-toggle-off.png)。.

**[ユーザー申請**] ページが終了したら、[保存] をクリック **します**。 設定を直前の値に復元するには、[ **復元**] をクリックします。

#### <a name="message-submission-format"></a>メッセージ送信形式

元の添付メッセージを正しく識別するために、カスタム メールボックスに送信されるメッセージには特定の書式設定が必要です。 メッセージがこの形式を使用しない場合、元の添付メッセージは常にフィッシングとして識別されます。

元の添付メッセージが報告された理由を指定するには、ユーザー送信メールボックスに送信されたメッセージが次の条件を満たしている必要があります。

- 元のメッセージ添付ファイルは変更されません。
- ユーザー送信メールボックスに送信されるメッセージの件名 (封筒のタイトル) は、次のいずれかのプレフィックス値で始まる必要があります。
  - `1|` または `Junk:`。
  - `2|` または `Not junk:`。
  - `3|` または `Phishing:`。

  以下に例を示します。

  - `3|This text in the Subject line is ignored by the system`
  - `Not Junk:This text in the Subject line is also ignored by the system`

  この形式に従わないメッセージは、[ **送信]** ページの <https://security.microsoft.com/reportsubmission>[.
