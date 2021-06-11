---
title: 管理者の申請
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 セキュリティ センターの Submits ポータルを使用して、不審なメール、フィッシングメール、スパム、その他有害な可能性のあるメッセージ、URL、および電子メールの添付ファイルを Microsoft に提出して再スキャンする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878690"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)


Exchange Online のメールボックスを持つ組織では、管理者はセキュリティ & コンプライアンス センターの申請ポータルを使用して、電子メール メッセージ、URL、添付ファイルを Microsoft に送信してスキャンできます。 Microsoft 365

電子メール メッセージを送信すると、次の情報が表示されます。

1. **電子メール認証チェック**: 電子メール認証が配信された際に合格または失敗したかどうかの詳細。
2. **ポリシーヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの評決を上書きします。
3. **ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。
4. **Grader 分析**: メッセージが悪意のあるかどうかを確認するために、人間の採点者が行うレビュー。

> [!IMPORTANT]
> ペイロード評価/デトナレーションおよび採点者分析は、すべてのテナントで行われるという問題ではありません。 データがコンプライアンスの目的でテナント境界から離れるはずではない場合、情報は組織外に出るのをブロックされます。

電子メール メッセージ、URL、添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- [セキュリティ センター] Microsoft 365開きます <https://security.microsoft.com/> 。 [申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。

- メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。

  - **セキュリティ センター** の **組織** の管理 [またはMicrosoft 365リーダー](permissions-microsoft-365-security-center.md)。

  - **[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。

    この記事で後述するように、カスタム メールボックスへの[](#view-user-submissions-to-the-custom-mailbox)ユーザー申請を表示するには、この役割グループのメンバーシップが必要です。

- ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>疑わしいコンテンツを Microsoft に報告する

1. [セキュリティ [Microsoft 365]](../defender/overview-security-center.md)で、[申請]に移動し、[分析用に送信]タブに移動し、[確認のために Microsoft に送信する]**をクリックします**。

2. 次の **セクションで説明するように** 、メッセージ、URL、または電子メールの添付ファイルを送信するために表示される [Microsoft に送信する] を使用して、確認の飛び出しを行います。

### <a name="submit-a-questionable-email-to-microsoft"></a>疑いがある電子メールを Microsoft に送信する

1. [申請 **の種類の選択] セクションで** 、[メール] を **選択します**。 [ネットワーク **メッセージ ID の追加または電子メール** ファイルのアップロード] セクションで、次のいずれかのオプションを使用します。

   - 電子メール ネットワーク メッセージ **ID** を追加する: これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。

   - **アップロードを開く: [** ファイルの参照]**をクリックします**。 開いたダイアログで、.eml ファイルまたは .msg ファイルを見つけて選択し、[開く] を **クリックします**。

   > [!NOTE]
   > 30 日という古いメッセージを送信する機能は、ユーザーのユーザーに対して Defender Office 365されています。 管理者は 7 日間だけ戻って行くことができます。

2. [問題 **を持っていた受信者の選択** ] セクションで、ポリシー チェックを実行する受信者を指定します。 ポリシー チェックは、ユーザーまたは組織のポリシーが原因で電子メールがスキャンをバイパスしたかどうかを判断します。

3. [Microsoft **に提出する理由の選択] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていない必要があります**

   - **ブロックされている必要があります**: [スパム **]、[****フィッシング]、または [マルウェア]** を **選択します**。 不明な場合は、最善の判断を下してください。

4. 完了したら、[送信] ボタン **をクリック** します。

   ![新しい URL 申請の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>疑わしい URL を Microsoft に送信する

1. [申請 **の種類の選択] セクションで****、[URL] を選択します**。 表示されるボックスに、完全な URL (たとえば) を入力 `https://www.fabrikam.com/marketing.html` します。

2. [申請 **の理由] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていない必要があります**

   - **ブロックされている必要があります**: [フィッシング] または [**マルウェア] を****選択します**。

3. 完了したら、[送信] ボタン **をクリック** します。

   ![新しいメール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>疑わしいメール添付ファイルを Microsoft に送信する

1. [申請 **の種類の選択] セクションで** 、[電子メールの添付ファイル] **を選択します**。

2. [ファイル **の選択] をクリックします**。 開いたダイアログで、ファイルを見つけて選択し、[開く] を **クリックします**。

3. [申請 **の理由] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていない必要があります**

   - **ブロックされている必要があります:****マルウェア** だけが選択され、自動的に選択されます。

4. 完了したら、[送信] ボタン **をクリック** します。

   ![新しい添付ファイルの申請の例](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>分析のために提出されたアイテムの表示

セキュリティ センター Microsoft 365に移動し、[送信済み分析] タブに移動して、自分が [送信済み]**分析タブに表示されているのを確認** します。

ページの中央にあるコマンド バーで、開始日、終了日、および (既定で) ボックスに値を入力し、[更新] ボタンをクリックして、申請 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます。 ![ ](../../media/scc-quarantine-refresh.png) Update

フィルター条件を変更するには、[フィルター] ボタン **をクリック** し、次のいずれかの値を選択します。

- **Sender**
- **件名/URL/ファイル名**
- **提出者**
- **申請の種類**
- **状態**

![管理者申請の新しいフィルター オプション](../../media/admin-submission-email-filter-options.png)

結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。 表示されるダイアログで、ファイルを保存.csvします。

グラフの下には、メール **(既定****)、URL、およびメール** 添付ファイルの 3 つの **タブがあります**。

### <a name="view-admin-email-submissions"></a>管理メールの送信を表示する

ページの下部にある **[列のカスタマイズ** ] ボタンをクリックすると、ビューに列を追加または削除できます。

- **Date**
- **申請 ID**: すべての申請に割り当てられている GUID 値。
- **提出者**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **申請の種類**
- **配信理由**
- **状態**<sup>\*</sup>

  <sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。

#### <a name="admin-submission-rescan-details"></a>管理者申請の再スキャンの詳細

管理者の申請で送信されたメッセージは再スキャンされ、提出の詳細フライアウトに結果が表示されます。

- 配信時に送信者のメール認証に失敗した場合。
- メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。
- 現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。
- 成績者からのフィードバック。

上書きが見つかった場合、再スキャンは数分で完了します。 メール認証や配信に問題が発生しない場合は、上書きによって影響を受けなかった場合、採点者からのフィードバックは最大で 1 日かかる可能性があります。

### <a name="view-admin-url-submissions"></a>管理者 URL の申請を表示する

**[URL] タブをクリック** します。

ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。

- **Date**
- **申請 ID**
- **提出者**<sup>\*</sup>
- [**URL**<sup>\*</sup>]
- **申請の種類**
- **状態**<sup>\*</sup>

  <sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。

### <a name="view-email-attachment-submissions"></a>メール添付ファイルの申請を表示する

[添付ファイル **] タブを** クリックします。

ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。

- **Date**
- **申請 ID**
- **提出者**<sup>\*</sup>
- **ファイル名**<sup>\*</sup>
- **申請の種類**
- **状態**<sup>\*</sup>

  <sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。

## <a name="view-user-submissions-to-microsoft"></a>Microsoft へのユーザー申請の表示

レポート メッセージ アドイン、レポート[](enable-the-report-message-add-in.md)フィッシング アドイン、またはユーザー[](enable-the-report-phish-add-in.md)が web 上[の Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)で組み込みのレポートを使用している場合は、[ユーザーの申請] タブでユーザーが報告している情報を確認できます。

1. セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。

2. [ユーザー申請 **] タブを選択** し、[新しい申請] **をクリックします**。

ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。

- **送信済み**
- **提出者**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **申請の種類**

<sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。

ページの上部付近では、開始日、終了日、および (既定で) ボックスに値を入力し、[更新]ボタンをクリックして Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。 Update

フィルター条件を変更するには、[送信者] ボタン **を** クリックし、次のいずれかの値を選択します。

- **送信元ドメイン**
- **[件名]**
- **提出者**
- **申請の種類**
- [**Sender IP (送信者の IP)**]

![ユーザー申請の新しいフィルター オプション](../../media/user-submissions-filter-options.png)

結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。 表示されるダイアログで、ファイルを保存.csvします。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>カスタム メールボックスへのユーザー申請の表示

**ユーザー** が報告した [メッセージを](user-submission.md) 受信するようにカスタム メールボックスを構成している場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。

1. セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。

2. [カスタム メールボックス **] タブを** 選択します。

ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。

- **送信済み**
- **提出者**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **申請の種類**

ページの上部の近くに開始日、終了日を入力し、ボックスに値を入力し、[更新]ボタンをクリックして[送信済み] でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。 Update

結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。 表示されるダイアログで、ファイルを保存.csvします。

> [!NOTE]
> 組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。

## <a name="undo-user-submissions"></a>ユーザー申請の元に戻す

ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すオプションを使用できません。 ユーザーが電子メールを回復する場合は、削除済みアイテムまたは迷惑メール フォルダーで回復できます。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>カスタム メールボックスから Microsoft にメッセージを送信する

Microsoft にメッセージを送信せずにユーザーが報告したメッセージを傍受するようにカスタム メールボックスを構成している場合は、特定のメッセージを見つけて分析のために Microsoft に送信できます。 これにより、ユーザーの申請が管理者申請に効果的に移動されます。

[ユーザー **が報告したメッセージ**] タブで、一覧でメッセージを選択し、[アクション] ボタンをクリックして、次のいずれかの選択を行います。

- **クリーンレポート**
- **フィッシングの報告**
- **マルウェアの報告**
- **スパムを報告する**

![[アクション] ボタンの [新しいオプション]](../../media/user-submission-custom-mailbox-action-button.png)
