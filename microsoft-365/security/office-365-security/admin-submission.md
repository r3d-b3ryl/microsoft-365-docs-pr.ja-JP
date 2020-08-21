---
title: 管理者の送信
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの申請ポータルを使用して、不審なメール、必要なフィッシング メール、スパム、スキャンのために Microsoft に有害な可能性のあるメッセージ、URL、ファイルを送信する方法を学習できます。
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845968"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する

Exchange Online にメールボックスがある Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの提出ポータルを使用して、スキャンのメール メッセージ、URL、および添付ファイルを Microsoft に送信できます。

メールを送信すると、受信メールをテナントに許可した可能性のあるポリシーに関する情報の他に、メール内の URL や添付ファイルが調べられます。 メールが許可されている場合があるポリシーには、個々のユーザーの差出人セーフ リストや、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) などのテナント レベル ポリシーが含まれます。

電子メール メッセージ、URL、および添付ファイルを Microsoft に送信するその他の方法については、「レポート [メッセージとファイルを Microsoft に送信する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [Submission] (提出) ページに **直接移動するには** 、次を使用します <https://protection.office.com/reportsubmission> 。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 提出ポータルに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- ユーザーがメッセージおよびファイルを Microsoft に送信する方法の詳細については、「レポート メッセージと [ファイルを Microsoft に送信する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>不審な内容を Microsoft に報告する

1. セキュリティ/コンプライアンス &で、[脅威**Threat management**の管理 \> **の送信] に移動**し、管理者の [送信]**タブで送信中であることを確認**し、[新規送信] を**クリックします**。

2. 表示 **される新しい** 申請ポップアップを使用して、次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信します。

### <a name="submit-a-questionable-email-to-microsoft"></a>問題のないメールを Microsoft に送信する

1. [Object **Type] セクションで****、[Email] を選択します**。 [Submission **format] (提出の** 形式) セクションで、次のいずれかのオプションを使用します。

   - **ネットワーク メッセージ ID:** これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id ヘッダー内で取得** できる GUID 値です。

   - **[File]:**[Choose **file] をクリックします**。 開いたダイアログで,.eml ファイルまたは .msg ファイルを探して選択し、[開く] をクリック **します**。

2. [受信者 **]** セクションで、ポリシー チェックの実行に対して 1 名以上の受信者を指定します。 ポリシー チェックでは、ユーザー ポリシーまたは組織ポリシーに合格したメールのバイパスが確認されます。

3. [送信 **の理由] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていないべきか**

   - **スパム、フィッシ****ング、** マルウェア**を**選択**します**。 不満の場合は、最善のジュージングを使う必要があります。

4. 提出時にポリシーが必要なためフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。

   1 つ以上のポリシーが渡されないためにフィルターがバイパスしなかった場合、スキャンは数分で完了します。 [状態] リンクをクリックすると、提出に関する追加情報が表示されます。 これには、ポリシー チェックの結果と、再スキャンの確認結果が含まれます。 Office 365 ATP フル フィルター スタックを介した電子メールは再度実行されませんが、メール、URL、ファイルの特定の属性に基づいて部分的な再スキャンが実行されます。

5. 完了したら、送信ボタンを **クリック** します。

![URL の送信の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Microsoft に対する必要な URL の送信

1. [ **オブジェクトの種類] セクション** で **、[URL] を選択します**。 表示されるボックスに、完全な URL (たとえば、) を入力します <https://www.fabrikam.com/marketing.html> 。

2. [送信 **の理由] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていないべきか**

   - **ブロックされる: フィ**ッ **シングまたはマルウェアを** 選 **います**。

3. 完了したら、送信ボタンを **クリック** します。

![メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Microsoft に対して必要なファイルを提出する

1. [Object **Type] セクションで****、[Attachment] を選択します**。

2. [ **ファイルの選択] をクリックします**。 開いたダイアログで、ファイルを検索して選択し、[開く] をクリック **します**。

3. [送信 **の理由] セクション** で、次のいずれかのオプションを選択します。

   - **ブロックされていないべきか**

   - **ブロックされている必要があるのは、****マルウェアが**この選択肢の 1 つで、自動的に選択されます。

4. 完了したら、送信ボタンを **クリック** します。

![添付ファイルの送信の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>管理者の申請を表示する

セキュリティ/コンプライアンス &で、[脅威**Threat management**の管理 \> **の送信] に移動**し、管理者の [送信]**タブで送信中であることを確認**し、[新規送信] を**クリックします**。

ページの上部で、開始日、終了日を入力できます。(既定では) [サブミッション **ID]** (各提出に割り当てられている GUID 値) でフィルター処理するには、ボックスに値を入力して ![ [更新] ボタンをクリックします ](../../media/scc-quarantine-refresh.png) 。 Update

フィルター条件を変更するには、[Submission **ID] ボタンをクリック** し、次のいずれかの値を選択します。

- **Sender**
- **サブジェクト/URL/ファイル名**
- **送信元**
- **提出の種類**
- **状態**

![管理者の申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。 表示されるダイアログで、.csv ファイルを保存します。

グラフの下には、電子メール (既定 **)、URL、****添付**ファイルの 3 つのタブ**があります**。

### <a name="view-admin-email-submissions"></a>管理者メールの提出を表示する

[電子メール **] タブを** クリックします。

ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。

- **Date**
- **提出 ID**: 各申請に割り当てられる GUID 値です。
- **送信元**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **提出の種類**
- **配信理由**
- **状態**<sup>\*</sup>
- **コントロールの種類**
- **コントロール ソース**

  <sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。

### <a name="view-admin-url-submissions"></a>管理 URL の提出の表示

**[URL] タブを**クリックします。

ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。

- **Date**
- **Submission ID**
- **送信元**<sup>\*</sup>
- [**URL**<sup>\*</sup>]
- **提出の種類**
- **状態**<sup>\*</sup>

  <sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。

### <a name="view-admin-attachment-submissions"></a>管理者の添付ファイルの送信を表示する

[添付ファイル **] タブをクリック** します。

ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。

- **Date**
- **Submission ID**
- **送信元**<sup>\*</sup>
- **ファイル名**<sup>\*</sup>
- **提出の種類**
- **状態**<sup>\*</sup>

  <sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。

## <a name="view-user-submissions-to-microsoft"></a>Microsoft へのユーザーの申請を表示する

迷惑メール報告アドインを展開 [した場合、またはユーザーが](enable-the-report-message-add-in.md)Outlook on the web の組み込みのレポートを使用している [場合は](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)、[ユーザーの送信] タブで、どのユーザーが報告を **行うかを確認** できます。

1. セキュリティ コンプライアンス センター&、[脅威管理 **の送信]** \> **に移動します**。

2. [User **submissions] (ユーザーの提出) タブを** 選び、[New submission] (新 **しい申請) をクリックします**。

ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。

- **送信済み**
- **送信元**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **提出の種類**

<sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。

ページの上部に表示されているのは、開始日、終了日を入力できます。また、(既定の場合) ボックスに **値を入力して** [更新] ボタンをクリックすると、送信者 ![ によってフィルター処理できます ](../../media/scc-quarantine-refresh.png) 。 Update

フィルター条件を変更するには、[送信者] **ボタンをクリック** し、次の値のいずれかを選択します。

- **送信元ドメイン**
- **[件名]**
- **送信元**
- **提出の種類**
- [**Sender IP (送信者の IP)**]

![ユーザー申請のフィルター オプション](../../media/user-submissions-filter-options.png)

結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。 表示されるダイアログで、.csv ファイルを保存します。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>カスタム メールボックスへのユーザー送信を表示する

ユーザーから報告された [メッセージを受信するように](user-submission.md) カスタム メールボックスを構成した場合は、レポート メールボックスに配信されたメッセージを表示して送信することもできます。

1. セキュリティ コンプライアンス センター&、[脅威管理 **の送信]** \> **に移動します**。

2. [カスタム メールボックス **] タブを選択** します。

ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。

- **送信済み**
- **送信元**<sup>\*</sup>
- **[件名]**<sup>\*</sup>
- **Sender**
- [**Sender IP (送信者の IP)**<sup>\*</sup>]
- **提出の種類**

ページの上部で、開始日、終了日を入力できます。また、[更新] ボタンをクリックして **[送信** 日] に値を ![ 入力することでフィルター処理できます ](../../media/scc-quarantine-refresh.png) 。 Update

結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。 表示されるダイアログで、.csv ファイルを保存します。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>カスタム メールボックスから Microsoft にメッセージを送信する

Microsoft にメッセージを送信せずにユーザーから報告されたメッセージを取得するようにカスタム メールボックスを構成した場合は、特定のメッセージを検索して分析用に Microsoft に送信できます。 これにより、ユーザーの申請が効率的に管理者の申請に移動されます。

カスタム メールボックス **タブで** 、一覧からメッセージを選択し、[ **操作]** ボタンをクリックして、次のいずれかを選択します。

- **レポートのクリーンなレポート**
- **レポート フィッシング**
- **マルウェアの報告**
- **迷惑メール報告**

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
