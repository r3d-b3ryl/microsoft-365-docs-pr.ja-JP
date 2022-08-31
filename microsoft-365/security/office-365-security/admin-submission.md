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
description: 管理者は、Microsoft 365 Defender ポータルで申請ポータルを使用して、ブロックされた正当なメール、疑わしい電子メール、疑わしいフィッシングメール、スパム、その他の潜在的に有害なメッセージ、URL、電子メールの添付ファイルを再スキャン用に Microsoft に送信する方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b5b54a0d6d8e760d392578997461be44a19cf92a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480539"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-legitimate-email-getting-blocked-and-email-attachments-to-microsoft"></a>送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当なメール、および電子メールの添付ファイルを Microsoft に送信する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Exchange Online メールボックスを持つ Microsoft 365 組織では、管理者は、Microsoft 365 Defender ポータルの申請ポータルを使用して、電子メール メッセージ、URL、添付ファイルを Microsoft に送信してスキャンできます。

分析のために電子メール メッセージを送信すると、次の情報が表示されます。

- **Email認証チェック**: 電子メール認証が配信されたときに成功したか失敗したかの詳細。
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

- 管理送信は、次のレートで調整されます。
  - 15 分間の最大送信数: 150 件
  - 24 時間の同じ申請: 3 件の提出
  - 15 分間の同じ申請: 1 件の提出

- ユーザーが Microsoft にメッセージとファイルを送信する方法の詳細については、「メッセージ [とファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-questionable-email-to-microsoft"></a>問題のあるメールを Microsoft に報告する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信] ページで** 、[ **電子メール** ] タブが選択されていることを確認します。

3. [ **電子メール** ] タブで、[分析用に Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** に、次の情報を入力します。

   - **申請の種類を選択します**。**Email** 値が選択されていることを確認します。

   - **ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロード** します。次のいずれかのオプションを選択します。

     - **電子メール ネットワーク メッセージ ID を追加します**。これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。

     - **電子メール ファイル (.msg または .eml) をアップロード** する: [ **ファイルの参照**] をクリックします。 開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[ **開く**] をクリックします。

   - **問題が発生した受信者を選択** します。ポリシー チェックを実行する受信者を指定します。 ポリシー チェックでは、ユーザーまたは組織のポリシーが原因で、電子メールがスキャンをバイパスしたかどうかが決定されます。

   - **Microsoft に送信する理由を選択** します。[ **ブロックされていない必要があります(False positive)]** が選択されていることを確認します。

     - **電子メールは、次のように分類されている必要があります**: **フィッシング**、 **マルウェア**、またはスパムを選択 **します**。 よくわからない場合は、最善の判断をしてください。

     - **[この送信者またはドメインからのすべてのメールをブロック** する]: このオプションを選択すると、テナント許可/ブロック リストに送信者のブロック エントリが作成されます。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

       このオプションを選択すると、次の設定を使用できます。

       - 既定では **、[送信者]** が選択されていますが、代わりに [ **ドメイン** ] を選択できます。

       - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **90 日間**
           - **有効期限が切れない**
           - **特定の日付**

       - **エントリのブロックに関する注意**: この電子メールを許可する理由に関するオプション情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

> :::image type="content" source="../../media/admin-submission-email-block.png" alt-text="Defender ポータルの [提出] ページで分析のために、Microsoft に偽陰性 (不適切な) 電子メールを送信します。" lightbox="../../media/admin-submission-email-block.png":::

> [!NOTE]
> [スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)によって誤ってブロックされたメッセージの場合、ドメイン ペアのブロック エントリはテナント許可/ブロック リストに作成されません。
>
> [ドメインまたはユーザー偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)によって誤ってブロックされたメッセージの場合、ドメインまたは送信者のブロック エントリはテナント許可/ブロック リストに作成されません。 代わりに、メッセージを検出した [フィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies)の **[信頼された送信者とドメイン] セクション** にドメインまたは送信者が追加されます。
>
> **ファイルをブロックすべきでない (誤検知)** と報告するには、「[Microsoft 365 Defender ポータルを使用して、申請ポータルでドメインと電子メール アドレスの許可エントリを作成](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)する」を参照してください。

## <a name="report-questionable-email-attachments-to-microsoft"></a>問題のある電子メールの添付ファイルを Microsoft に報告する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [**申請] ページで**、[**Email添付ファイル**] タブを選択します。

3. [**Email添付ファイル**] タブで、[分析のために Microsoft に送信] のアイコンをクリックします![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** で、次の情報を入力します。

   - **送信の種類を選択します**。**添付ファイルが選択Email** 値を確認します。

   - **ファイル**: [ **ファイルの参照]** をクリックして、送信するファイルを見つけて選択します。

     > [!NOTE]
     > ファイルの送信は、データが環境から離れることを許可しないクラウドでは使用できません。 **ファイルを参照** すると灰色で表示されます。

   - **Microsoft に送信する理由を選択** します:[ **ブロックされている必要があります(False negative)]** が選択されていることを確認します。

     - **電子メールは、次のように分類されている必要があります**: **フィッシング** または **マルウェア** を選択します。 よくわからない場合は、最善の判断をしてください。

     - **このファイルをブロック** する: このオプションを選択すると、テナント許可/ブロック リストに送信者のブロック エントリが作成されます。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

       このオプションを選択すると、次の設定を使用できます。

       - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **90 日間**
           - **有効期限が切れない**
           - **特定の日付**

       - **エントリのブロックに関する注意**: この電子メールを許可する理由に関するオプション情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

> :::image type="content" source="../../media/admin-submission-file-block.png" alt-text="Defender ポータルの [提出] ページで分析のために、Microsoft に偽陰性 (不適切な) 電子メール添付ファイルを送信します。" lightbox="../../media/admin-submission-file-block.png":::

 > [!NOTE]
 > **ファイルをブロックすべきでない (誤検知)** と報告するには、「[Microsoft 365 Defender ポータルを使用して、申請ポータルでファイルの許可エントリを作成する」を参照してください](allow-block-files.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-files-in-the-submissions-portal)。

## <a name="report-questionable-urls-to-microsoft"></a>問題のある URL を Microsoft に報告する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **URL** ] タブを選択します。

3. [ **URL] タブで** 、[分析の追加] ボタンで [Microsoft に送信] をクリック ![します。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** に、次の情報を入力します。

   - **送信の種類を選択します**。値の **URL** が選択されていることを確認します。

   - **URL**: 完全な URL (たとえば) を入力し、 `https://www.fabrikam.com/marketing.html`表示されるボックスで選択します。

     > [!NOTE]
     > URL の送信は、データが環境から離れることを許可しないクラウドでは使用できません。 **URL** は灰色で表示されます。

   - **Microsoft に送信する理由を選択** します:[ **ブロックされている必要があります(False negative)]** が選択されていることを確認します。

     - **電子メールは、次のように分類されている必要があります**: **フィッシング** または **マルウェア** を選択します。 よくわからない場合は、最善の判断をしてください。

     - **この URL をブロック** する: このオプションを選択すると、テナント許可/ブロック リストに送信者のブロック エントリが作成されます。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

       このオプションを選択すると、次の設定を使用できます。

       - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **90 日間**
           - **有効期限が切れない**
           - **特定の日付**

       - **エントリのブロックに関する注意**: この電子メールを許可する理由に関するオプション情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

> :::image type="content" source="../../media/admin-submission-url-block.png" alt-text="Defender ポータルの [申請] ページで、分析のために Microsoft に偽陰性 (不適切な) URL を送信します。" lightbox="../../media/admin-submission-url-block.png":::

 > [!NOTE]
 > **URL をブロックすべきでない (誤検知)** と報告するには、「[Microsoft 365 Defender ポータルを使用して、申請ポータルで URL の許可エントリを作成](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal)する」を参照してください。

## <a name="view-email-admin-submissions-to-microsoft"></a>Microsoft へのメール管理者の提出を表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信] ページで** 、[ **電子メール** ] タブが選択されていることを確認します。

   - 使用可能な列ヘッダーをクリックすると、エントリを並べ替えることができます。

   - [列のカスタマイズ] アイコンをクリック ![します。](../../media/m365-cc-sc-customize-icon.png) **表示する列** を選択するように列をカスタマイズします。 既定値にはアスタリスク (\*) が付いています。
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

     :::image type="content" source="../../media/admin-submission-email-customize-columns.png" alt-text="電子メール管理者の提出の列オプションをカスタマイズします。" lightbox="../../media/admin-submission-email-customize-columns.png":::

   - エントリをフィルター処理するには、[フィルター] アイコンをクリックします ![。](../../media/m365-cc-sc-filter-icon.png) **フィルター。** 次の値は、表示される **フィルター** ポップアップで使用できます。
     - **送信日**: **開始日** と **終了日** の値。
     - **申請 ID**: すべての申請に割り当てられる GUID 値。
     - **ネットワーク メッセージ ID**
     - **Sender**
     - **[受信者]**
     - **名前**
     - **提出者**
     - **送信の理由**: 値 **は迷惑メール**、 **フィッシング**、 **マルウェア**、 **スパム** ではありません。
     - **状態**: **保留中** と **完了の** 値。
     - **タグ**: 既定値は **[すべて]** か、ドロップダウン リストから [ユーザー タグ](user-tags.md) を選択します。

     完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

     :::image type="content" source="../../media/admin-submission-email-filters.png" alt-text="電子メール管理者の提出のフィルター オプション。" lightbox="../../media/admin-submission-email-filters.png":::

   - エントリをグループ化するには、[グループ] アイコンをクリックします ![。](../../media/m365-cc-sc-group-icon.png) ドロップダウン リストから次のいずれかの値を **グループ** 化して選択します。
     - **なし**
     - **理由**
     - **状態**
     - **結果**
     - **Tags**

   - エントリをエクスポートするには、[エクスポート] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **エクスポート**。 表示されるダイアログで、.csv ファイルを保存します。

## <a name="view-email-attachment-admin-submissions-to-microsoft"></a>Microsoft へのメール添付ファイル管理者の提出を表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [**申請]** ページで、[**Email添付ファイル**] タブが選択されていることを確認します。

   - 使用可能な列ヘッダーをクリックすると、エントリを並べ替えることができます。

   - [列のカスタマイズ] アイコンをクリック ![します。](../../media/m365-cc-sc-customize-icon.png) **表示する列** を選択するように列をカスタマイズします。 既定値にはアスタリスク (\*) が付いています。
     - **添付ファイルのファイル名**<sup>\*</sup>
     - **送信日**<sup>\*</sup>
     - **送信の理由**<sup>\*</sup>
     - **ステータス**<sup>\*</sup>
     - **結果**<sup>\*</sup>
     - **フィルターの判定**
     - **配信/ブロックの理由**
     - **申請 ID**
     - **オブジェクト ID**
     - **ポリシー アクション**
     - **提出者**
     - **タグ**<sup>\*</sup>
     - **許可**

     完了したら、**[適用]** をクリックします。

     :::image type="content" source="../../media/admin-submission-file-customize-columns.png" alt-text="電子メール添付ファイル管理者の送信の列オプションをカスタマイズします。":::

   - エントリをフィルター処理するには、[フィルター] アイコンをクリックします ![。](../../media/m365-cc-sc-filter-icon.png) **フィルター。** 次の値は、表示される **フィルター** ポップアップで使用できます。
     - **送信日**: **開始日** と **終了日**。
     - **申請 ID**: すべての申請に割り当てられる GUID 値。
     - **添付ファイルの名前**
     - **提出者**
     - **送信の理由**
     - **状態**
     - **タグ**: 既定値は **[すべて]** か、ドロップダウン リストから [ユーザー タグ](user-tags.md) を選択します。

     完了したら、**[適用]** をクリックします。

     :::image type="content" source="../../media/admin-submission-file-filters.png" alt-text="電子メール添付ファイル管理者の送信のフィルター オプション。":::

   - エントリをグループ化するには、[グループ] アイコンをクリックします ![。](../../media/m365-cc-sc-group-icon.png) **ドロップダウン** リストから次のいずれかの値をグループ化して選択します。
     - **なし**
     - **理由**
     - **状態**
     - **結果**
     - **Tags**

   - エントリをエクスポートするには、[エクスポート] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **エクスポート**。 表示されるダイアログで、.csv ファイルを保存します。

## <a name="view-urls-admin-submissions-to-microsoft"></a>Microsoft に対する URL 管理者の提出を表示する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **URL** ] タブが選択されていることを確認します。

   - 使用可能な列ヘッダーをクリックすると、エントリを並べ替えることができます。

   - [列のカスタマイズ] アイコンをクリック ![します。](../../media/m365-cc-sc-customize-icon.png) **表示する列** を選択するように列をカスタマイズします。 既定値にはアスタリスク (\*) が付いています。
     - [**URL**<sup>\*</sup>]
     - **送信日**<sup>\*</sup>
     - **送信の理由**<sup>\*</sup>
     - **ステータス**<sup>\*</sup>
     - **結果**<sup>\*</sup>
     - **フィルターの判定**
     - **配信/ブロックの理由**
     - **申請 ID**
     - **オブジェクト ID**
     - **ポリシー アクション**
     - **提出者**
     - **タグ**<sup>\*</sup>
     - **許可**

     完了したら、**[適用]** をクリックします。

     :::image type="content" source="../../media/admin-submission-url-customize-columns.png" alt-text="URL 管理者申請の列オプションをカスタマイズします。":::

   - エントリをフィルター処理するには、[フィルター] アイコンをクリックします ![。](../../media/m365-cc-sc-filter-icon.png) **フィルター。** 次の値は、表示される **フィルター** ポップアップで使用できます。
     - **送信日**: **開始日** と **終了日**。
     - **申請 ID**: すべての申請に割り当てられる GUID 値。
     - **URL**
     - **提出者**
     - **送信の理由**
     - **状態**
     - **タグ**: 既定値は **[すべて]** か、ドロップダウン リストから [ユーザー タグ](user-tags.md) を選択します。

     完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

     :::image type="content" source="../../media/admin-submission-url-filters.png" alt-text="URL 管理者申請のフィルター オプション。":::

   - エントリをグループ化するには、[グループ] アイコンをクリックします ![。](../../media/m365-cc-sc-group-icon.png) ドロップダウン リストから次のいずれかの値を **グループ** 化して選択します。
     - **なし**
     - **理由**
     - **状態**
     - **結果**
     - **Tags**

   - エントリをエクスポートするには、[エクスポート] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **エクスポート**。 表示されるダイアログで、.csv ファイルを保存します。

## <a name="admin-submission-result-details"></a>提出結果の詳細を管理する

管理者の提出で送信されたメッセージは、Microsoft によって確認され、提出の詳細ポップアップに表示される結果が表示されます。

- 配信時に送信者のメール認証に失敗した場合。
- メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。
- 現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。
- 採点者からのフィードバック。

オーバーライドが見つかった場合、結果は数分で使用可能になります。 電子メール認証に問題がない場合、または配信がオーバーライドの影響を受けなかった場合、採点者からのフィードバックには最大 1 日かかる可能性があります。

## <a name="view-user-submissions-to-microsoft"></a>Microsoft へのユーザー申請を表示する

[レポート メッセージ アドイン](enable-the-report-message-add-in.md)、[レポート フィッシング アドイン](enable-the-report-phish-add-in.md)、またはユーザーが組 [み込みのレポートをOutlook on the webで使用している](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)場合は、[**ユーザー報告メッセージ**] タブでレポートしているユーザーを確認できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** 、[ **ユーザーが報告したメッセージ** ] タブを選択します。

   - [列のカスタマイズ] アイコンをクリック ![します。](../../media/m365-cc-sc-customize-icon.png) **表示する列** を選択するように列をカスタマイズします。 既定値にはアスタリスク (\*) が付いています。
     - **件名Email**<sup>\*</sup>
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

   - エントリをフィルター処理するには、[フィルター] アイコンをクリックします ![。](../../media/m365-cc-sc-filter-icon.png) **フィルター。** 次の値は、表示される **フィルター** ポップアップで使用できます。
     - **報告日**: **開始日** と **終了日**。
     - [**レポート作成者**]
     - **メールの件名**
     - **メッセージ報告 ID**
     - **ネットワーク メッセージ ID**
     - **Sender**
     - **報告された理由**: 値 **が迷惑** メール、 **フィッシング**、または **スパム** ではありません。
     - **報告元**: **Microsoft アドイン** または **サード パーティ アドインの** 値。
     - **フィッシング シミュレーション**: 値は **[はい]** または **[いいえ] です**。
     - **管理者申請に変換**: 値は **[はい]** または **[いいえ]** です。
     - **タグ**: 既定値は **[すべて]** か、ドロップダウン リストから [ユーザー タグ](user-tags.md) を選択します。

     完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

     > :::image type="content" source="../../media/admin-submission-user-reported-filters.png" alt-text="ユーザー申請のフィルター オプション。" lightbox="../../media/admin-submission-user-reported-filters.png":::

   - エントリをグループ化するには、[グループ] アイコンをクリックします ![。](../../media/m365-cc-sc-group-icon.png) ドロップダウン リストから次のいずれかの値を **グループ** 化して選択します。
     - **なし**
     - **理由**
     - **Sender**
     - [**レポート作成者**]
     - **結果**
     - **レポート元**
     - **フィッシング シミュレーション**
     - **管理者申請に変換済み**
     - **Tags**

   - エントリをエクスポートするには、[エクスポート] アイコンをクリックします ![。](../../media/m365-cc-sc-download-icon.png) **エクスポート**。 表示されるダイアログで、.csv ファイルを保存します。

   - ユーザーに通知するには、「[報告されたメッセージの確認管理」を](admin-review-reported-message.md)参照してください。

> [!NOTE]
> 組織がユーザーから報告されたメッセージを [カスタム メールボックスにのみ](user-submission.md)送信するように構成されている場合、報告されたメッセージは **ユーザー報告メッセージ** に表示されますが、結果は常に空になります (再スキャンされなかったため)。

## <a name="undo-user-submissions"></a>ユーザーの申請を元に戻す

ユーザーがカスタム メールボックスに不審な電子メールを送信すると、ユーザーと管理者は送信を元に戻すオプションを持っていません。 ユーザーが電子メールを回復する場合は、削除済みアイテムまたは迷惑メール Email フォルダーで回復できます。

## <a name="convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>ユーザーが報告したメッセージをカスタム メールボックスから管理者の提出に変換する

Microsoft にメッセージを送信せずにユーザーから報告されたメッセージをインターセプトするようにカスタム メールボックスを構成した場合は、分析のために特定のメッセージを見つけて Microsoft に送信できます。

[ **ユーザーから報告されたメッセージ** ] タブで、一覧からメッセージを選択し、[分析の追加] アイコンで [Microsoft に送信] をクリックします ![。](../../media/m365-cc-sc-submit-user-reported-message-icon.png) **分析のために Microsoft に送信** し、ドロップダウン リストから次のいずれかの値を選択します。

- **クリーンなレポート**
- **フィッシングを報告する**
- **マルウェアを報告する**
- **スパムを報告する**
- **トリガー調査**

  :::image type="content" source="../../media/admin-submission-user-reported-submit-button-options.png" alt-text="[アクション] ボタンの [新規] オプション" lightbox="../../media/admin-submission-user-reported-submit-button-options.png":::

メッセージが Microsoft に報告された場合、[ **管理者に変換] の送信** 値が **[いいえ]** から **[はい**] に変わります。 管理者申請に直接アクセスするには、それぞれのユーザーが報告したメッセージの送信ポップアップ内のオーバーフロー メニューから **[変換された管理者** 申請の表示] をクリックします。

:::image type="content" source="../../media/view-converted-admin-submission.png" alt-text="ユーザーから報告されたメッセージから作成された管理者の提出を表示するオプション。":::

## <a name="view-associated-alert-for-user-and-admin-email-submissions"></a>ユーザーと管理者のメール送信に関連するアラートを表示する

> [!IMPORTANT]
> このセクションの情報は、Defender for Office 365プラン 2 以降にのみ適用されます。
>
> 現在、ユーザー申請では、フィッシングとして報告されたメッセージに対してのみアラートが生成されます。

ユーザーが報告したフィッシング メッセージと管理者のメール送信ごとに、対応するアラートが生成されます。

ユーザーが報告したフィッシング メッセージに対応するアラートを表示するには、[ **ユーザーが報告したメッセージ** ] タブを選択し、メッセージをダブルクリックして送信ポップアップを開きます。 [その他のオプション] アイコンをクリック ![します。](../../media/m365-cc-sc-more-actions-icon.png) **その他のオプション** を選択し、[  **アラートの表示**] を選択します。

:::image type="content" source="../../media/alert-from-user-submission.png" alt-text="ユーザーから報告されたフィッシング メッセージから関連するアラートを表示するオプション。":::

管理者のメール送信に対応するアラートを表示するには、[ **電子メール** ] タブを選択し、メッセージをダブルクリックして申請ポップアップを開きます。 [**電子メール エンティティを開く**] オプションで [**アラートの表示**] を選択します。

:::image type="content" source="../../media/alert-from-admin-submission.png" alt-text="管理者の申請から関連するアラートを表示するオプション。":::
