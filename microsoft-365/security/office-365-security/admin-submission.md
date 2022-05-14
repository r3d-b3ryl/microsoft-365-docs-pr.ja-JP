---
title: 提出を管理する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: seo-marvel-apr2020
description: 管理者は、Microsoft 365 Defender ポータルの提出ポータルを使用して、疑わしいメール、フィッシング詐欺の疑いのあるメール、スパム、その他有害な可能性のあるメッセージ、URL、電子メールの添付ファイルを再スキャン用に Microsoft に送信する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8e9faf6114551725dc1fc3b8b6af173bbe1e21b4
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417954"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に送信する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Exchange Online メールボックスを持つ組織Microsoft 365管理者は、Microsoft 365 Defender ポータルの申請ポータルを使用して、電子メール メッセージ、URL、添付ファイルをスキャン用に Microsoft に送信できます。

分析のために電子メール メッセージを送信すると、次の情報が表示されます。

- **電子メール認証チェック**: 電子メール認証が配信されたときに成功したか失敗したかの詳細。
- **ポリシー ヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報。サービス フィルターの判定をオーバーライドします。
- **ペイロードの評価/起爆**: メッセージ内の URL と添付ファイルを最新の状態で確認します。
- **グレーデラー分析**: メッセージが悪意のあるかどうかを確認するために、人間の採点者によって行われたレビュー。

> [!IMPORTANT]
> ペイロードの評価/デトネーションとグレーデラーの分析は、すべてのテナントで行われるわけではありません。 データがコンプライアンスのためにテナント境界から離れることが想定されていない場合、情報が組織外に出ないようにブロックされます。

電子メール メッセージ、URL、添付ファイルを Microsoft に送信するその他の方法については、「 [メッセージとファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

この短いビデオでは、Microsoft Defender for Office 365で管理者の提出を使用して評価のために Microsoft にメッセージを送信する方法について説明します。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBLPn]

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

- Microsoft にメッセージとファイルを送信するには、次のいずれかのロールが必要です。
  - [Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)の **セキュリティ管理者** または **セキュリティ 閲覧者**。

    この記事の後半で説明するように [、カスタム メールボックスへのユーザー提出を表示するには、](#view-user-submissions-to-microsoft) これらのロールの 1 つが必要であることに注意してください。

- 管理者は、メールボックスで引き続き使用でき、ユーザーまたは別の管理者によって削除されない場合、30 日の古いメッセージを送信できます。

- 管理者の提出は、次のレートで調整されます。
  - 15 分間の最大送信数: 150 件
  - 24 時間の同じ申請: 3 件の提出
  - 15 分間の同じ申請: 1 件の提出

- ユーザーが Microsoft にメッセージとファイルを送信する方法の詳細については、「メッセージ [とファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>疑わしいコンテンツを Microsoft に報告する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信]** ページで、レポートするコンテンツの種類に基づいて [ **電子メール** ] タブまたは [ **電子メールの添付ファイル** または **URL**  ] タブが選択されていることを確認し、[分析用に Microsoft に送信] をクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. 次のセクションで説明するように、それぞれの種類のコンテンツ (電子メール、URL、または電子メールの添付ファイル) を送信するように表示される分析ポップアップに **対して Microsoft に送信** を使用します。

   > [!NOTE]
   > ファイルと URL の送信は、データが環境から離れることを許可しないクラウドでは使用できません。 [ファイル] または [URL] を選択する機能は淡色表示されます。

### <a name="notify-users-from-within-the-portal"></a>ポータル内からユーザーに通知する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Email & collaboration** \> **Submissions]** の [**申請]** ページに移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **ユーザーが報告したメッセージ** ] タブを選択し、マークして通知するメッセージを選択します。

3. [ **マークを付けて通知** ] ドロップダウンを選択し、[ **脅威が見つかりません** \> **フィッシング]** または [ **迷惑メール**] を選択します。

   :::image type="content" source="../../media/unified-submission-user-reported-message.png" alt-text="[申請] ページ" lightbox="../../media/unified-submission-user-reported-message.png":::

報告されたメッセージは、偽陽性または偽陰性としてマークされます。 メッセージを報告したユーザーには、ポータル内から電子メール通知が自動的に送信されます。

### <a name="submit-a-questionable-email-to-microsoft"></a>Microsoft に質問のあるメールを送信する

1. [ **送信の種類の選択** ] ボックスで、ドロップダウン リストで **[電子メール** ] が選択されていることを確認します。

2. [ **ネットワーク メッセージ ID の追加または電子メール ファイルのアップロード** ] セクションで、次のいずれかのオプションを使用します。
   - **電子メール ネットワーク メッセージ ID を追加します**。これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id** ヘッダーまたは検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。
   - **電子メール ファイル (.msg または .eml) をアップロード**: [ファイルの **参照**] をクリックします。 開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[ **開く**] をクリックします。

3. [ **問題のある受信者を選択** する] ボックスで、ポリシー チェックを実行する受信者を指定します。 ポリシー チェックでは、ユーザーまたは組織のポリシーが原因で、電子メールがスキャンをバイパスしたかどうかが決定されます。

4. [ **Microsoft に送信する理由の選択]** セクションで、次のいずれかのオプションを選択します。
   - **ブロックされていない必要があります (False positive)**
   - **ブロックされている必要があります (False negative)**: 電子 **メールが表示されるセクションとして分類されている必要があります** 。次のいずれかの値を選択します (不明な場合は、最善の判断をしてください)。
     - **フィッシング**
     - **マルウェア**
     - **スパム**

5. 完了したら、**[送信]** をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-flyout-email.png" alt-text="新しい URL 送信プロセス" lightbox="../../media/submission-flyout-email.png":::

### <a name="send-a-suspect-url-to-microsoft"></a>疑わしい URL を Microsoft に送信する

1. [ **送信の種類の選択** ] ボックスで、ドロップダウン リストから **[URL] を** 選択します。

2. 表示される **[URL** ] ボックスに、完全な URL (たとえば) `https://www.fabrikam.com/marketing.html`を入力します。

3. [ **Microsoft に送信する理由の選択]** セクションで、次のいずれかのオプションを選択します。
   - **ブロックされていない必要があります (False positive)**
   - **ブロックされている必要があります (False negative)**: **[この URL は表示されるセクションとして分類されている必要があります** ] で、次のいずれかの値を選択します (わからない場合は、最善の判断をしてください)。
     - **フィッシング**
     - **マルウェア**

4. 完了したら、**[送信]** をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-url-flyout.png" alt-text="新しい電子メール送信プロセス" lightbox="../../media/submission-url-flyout.png":::

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>疑わしい電子メールの添付ファイルを Microsoft に送信する

1. [ **送信の種類の選択** ] ボックスで、ドロップダウン リストから [ **電子メールの添付ファイル** ] を選択します。

2. 表示される [ **ファイル** ] セクションで、[ **ファイルの参照**] をクリックします。 開いたダイアログで、ファイルを見つけて選択し、[ **開く**] をクリックします。

3. [ **Microsoft に送信する理由の選択]** セクションで、次のいずれかのオプションを選択します。
   - **ブロックされていない必要があります (False positive)**
   - **ブロックされている必要があります (False negative)**: **[このファイルは表示されるセクションとして分類されている必要があります** ] で、次のいずれかの値を選択します (不明な場合は、最善の判断をしてください)。
     - **フィッシング**
     - **マルウェア**

4. 完了したら、**[送信]** をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-file-flyout.png" alt-text="新しい添付ファイルの送信プロセス" lightbox="../../media/submission-file-flyout.png":::

> [!NOTE]
> マルウェア フィルターによってメッセージの添付ファイルがマルウェア アラート Text.txt ファイルに置き換えられた場合は、元の添付ファイルを含む検疫から元のメッセージを送信する必要があります。 検疫の詳細と、マルウェアの誤検知を含むメッセージを解放する方法については、「 [管理者としての検疫済みメッセージとファイルの管理](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="view-admin-submissions-to-microsoft"></a>Microsoft に対する管理者の提出を表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信]** ページで、[ **電子メール**、 **URL**、または **電子メールの添付ファイル** ] タブが選択されていることを確認します。

   - 使用可能な列ヘッダーをクリックすると、エントリを並べ替えることができます。 [ **列のカスタマイズ** ] をクリックすると、最大 7 つの列が表示されます。 既定値にはアスタリスク (<sup>\*</sup>) が付いています。
     - **申請名**<sup>\*</sup>
     - **[送信者]**<sup>\*</sup>
     - **[受信者]**
     - **送信日**<sup>\*</sup>
     - **送信の理由**<sup>\*</sup>
     - **ステータス**<sup>\*</sup>
     - **結果**<sup>\*</sup>
     - **フィルターの判定**
     - **配信/ブロックの理由**
     - **申請 ID**
     - **ネットワーク メッセージ ID/オブジェクト ID**
     - **方向**
     - [**Sender IP (送信者の IP)**]
     - **一括準拠レベル (BCL)**
     - **宛先**
     - **ポリシー アクション**
     - **提出者**
     - **フィッシング シミュレーション**
     - **タグ**<sup>\*</sup>
     - **許可**

     完了したら、**[適用]** をクリックします。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-customize-columns.png" alt-text="管理者申請の [新しいカスタマイズ] 列オプション" lightbox="../../media/admin-submission-customize-columns.png":::

   - エントリをフィルター処理するには、[フィルター] をクリック **します**。 使用できるフィルターは次のとおりです。
     - **送信日**: **開始日** と **終了日**。
     - **申請 ID**: すべての申請に割り当てられる GUID 値。
     - **ネットワーク メッセージ ID**
     - **Sender**
     - **[受信者]**
     - **名前**
     - **提出者**
     - **送信の理由**
     - **状態**
     - **Tags**

     完了したら、**[適用]** をクリックします。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-filters.png" alt-text="管理者申請の [新しいフィルター] オプション" lightbox="../../media/admin-submission-filters.png":::

   - エントリをグループ化するには、[ **グループ化** ] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。
     - **なし**
     - **Type**
     - **理由**
     - **状態**
     - **結果**
     - **Tags**

   - エントリをエクスポートするには、[ **エクスポート**] をクリックします。 表示されるダイアログで、.csv ファイルを保存します。

### <a name="admin-submission-result-details"></a>管理者提出結果の詳細

管理者の提出で送信されたメッセージが確認され、申請の詳細ポップアップに結果が表示されます。

- 配信時に送信者のメール認証に失敗した場合。
- メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。
- 現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。
- 採点者からのフィードバック。

オーバーライドが見つかった場合、結果は数分で使用可能になります。 電子メール認証に問題がない場合、または配信がオーバーライドの影響を受けなかった場合、採点者からのフィードバックには最大 1 日かかる可能性があります。

## <a name="view-user-submissions-to-microsoft"></a>Microsoft へのユーザー申請を表示する

[レポート メッセージ アドイン](enable-the-report-message-add-in.md)、[レポート フィッシング アドイン](enable-the-report-phish-add-in.md)、またはユーザーが組 [み込みのレポートをOutlook on the webで使用している](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)場合は、[**ユーザー報告メッセージ**] タブでレポートしているユーザーを確認できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **ユーザーが報告したメッセージ** ] タブを選択します。

   - 使用可能な列ヘッダーをクリックすると、エントリを並べ替えることができます。 [ **列のカスタマイズ** ] をクリックしてオプションを表示します。 既定値にはアスタリスク (<sup>\*</sup>) が付いています。

     - **メールの件名**<sup>\*</sup>
     - **報告者**<sup>\*</sup>
     - **報告日**<sup>\*</sup>
     - **[送信者]**<sup>\*</sup>
     - **報告された理由**<sup>\*</sup>
     - **結果**<sup>\*</sup>
     - **メッセージ報告 ID**
     - **ネットワーク メッセージ ID**
     - [**Sender IP (送信者の IP)**]
     - **レポート元**
     - **フィッシング シミュレーション**
     - **管理者申請に変換済み**
     - **タグ**<sup>\*</sup>
     - **マーク済み**<sup>\*</sup>
     - **マーク付き**
     - **マークされた日付**

     完了したら、**[適用]** をクリックします。

   - エントリをフィルター処理するには、[フィルター] をクリック **します**。 使用できるフィルターは次のとおりです。
     - **報告日**: **開始日** と **終了日**。
     - [**レポート作成者**]
     - **メールの件名**
     - **メッセージ報告 ID**
     - **ネットワーク メッセージ ID**
     - **Sender**
     - **報告された理由**: **迷惑メール**、**フィッシング**、**スパム** ではない
     - **報告元**: **Microsoft アドイン** または **サード パーティアドイン**
     - **フィッシング シミュレーション**: **はい** または **いいえ**
     - **管理者申請に変換**: **はい** または **いいえ**
     - **Tags**

     完了したら、**[適用]** をクリックします。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-reported-messages.png" alt-text="ユーザー申請の [新しいフィルター] オプション" lightbox="../../media/admin-submission-reported-messages.png":::

   - エントリをグループ化するには、[ **グループ化** ] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。
     - **なし**
     - **理由**
     - **Sender**
     - [**レポート作成者**]
     - **結果**
     - **レポート元**
     - **フィッシング シミュレーション**
     - **管理者申請に変換済み**
     - **Tags**

   - エントリをエクスポートするには、[ **エクスポート**] をクリックします。 表示されるダイアログで、.csv ファイルを保存します。

> [!NOTE]
> 組織がユーザーから報告されたメッセージをカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは **ユーザー報告メッセージ** に表示されますが、結果は常に空になります (再スキャンされなかったため)。

### <a name="undo-user-submissions"></a>ユーザーの申請を元に戻す

ユーザーがカスタム メールボックスに不審な電子メールを送信すると、ユーザーと管理者は送信を元に戻すオプションを持っていません。 ユーザーが電子メールを回復する場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーで回復できます。

### <a name="converting-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>ユーザーが報告したメッセージをカスタム メールボックスから管理者の提出に変換する

Microsoft にメッセージを送信せずにユーザーから報告されたメッセージをインターセプトするようにカスタム メールボックスを構成した場合は、分析のために特定のメッセージを見つけて Microsoft に送信できます。

[ **ユーザーから報告されたメッセージ** ] タブで、一覧でメッセージを選択し、[ **分析のために Microsoft に送信**] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。

- **クリーンなレポート**
- **フィッシングを報告する**
- **マルウェアを報告する**
- **スパムを報告する**
- **トリガー調査**

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/admin-submission-main-action-button.png" alt-text="[アクション] ボタンの [新規] オプション" lightbox="../../media/admin-submission-main-action-button.png":::
