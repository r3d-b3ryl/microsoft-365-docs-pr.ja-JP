---
title: 攻撃シミュレーション トレーニングのインサイトとレポート
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 管理者は、Microsoft 365 Defender ポータルでの攻撃シミュレーション トレーニングがユーザーにどのような影響を与えるかを学習し、シミュレーションとトレーニングの結果から分析情報を得ることができます。
ms.technology: mdo
ms.openlocfilehash: 72ed46d1676f4abd97ecd4fccfe4ef20d971f0b3
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649455"
---
# <a name="insights-and-reports-for-attack-simulation-training-in-defender-for-office-365"></a>Defender for Office 365での攻撃シミュレーション トレーニングのインサイトとレポート

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

[Microsoft Defender for Office 365プラン 2](defender-for-office-365.md) **に適用されます**

Microsoft Defender for Office プラン 2 またはMicrosoft 365 E5の攻撃シミュレーション トレーニングでは、シミュレーションの結果と対応するトレーニングから分析情報とレポートを提供します。 この情報を使用すると、ユーザーの脅威の準備の進行状況と、今後の攻撃に備えるために推奨される次の手順に関する情報が得られます。

インサイトとレポートは、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの次の場所で利用できます。

- [ **概要** ] タブ。
- [シミュレーション] タブ **のシミュレーションの** 詳細。

この記事の残りの部分では、使用可能な情報について説明します。

攻撃シミュレーション トレーニングの概要については、「攻撃シミュレーション トレーニング[を使用した概要](attack-simulation-training-get-started.md)」を参照してください。

## <a name="insights-and-reports-on-the-overview-tab-of-attack-simulation-training"></a>攻撃シミュレーション トレーニングの [概要] タブのインサイトとレポート

**[概要**] タブに移動するには、Microsoft 365 Defender ポータル<https://security.microsoft.com>を開き、[**電子メール & コラボレーション** \> **攻撃シミュレーション トレーニング**] に移動し、[**概要**] タブが選択されていることを確認します (既定値)。 **攻撃シミュレーション トレーニング** ページの **[概要**] タブに直接移動するには、<https://security.microsoft.com/attacksimulator?viewid=overview>.

このセクションの残りの部分では、攻撃シミュレーション トレーニングの [ **概要** ] タブで使用できる情報について説明します。

### <a name="recent-simulations-card"></a>最近のシミュレーション カード

[**概要**] タブ **の [最近** 使ったシミュレーション] カードには、組織で作成または実行した最後の 3 つのシミュレーションが表示されます。

シミュレーションを選択して詳細を表示できます。

**[すべてのシミュレーションを表示]** を選択すると、[シミュレーション] タブ **に** 移動します。

**[シミュレーションの起動] を選択すると、シミュレーション** 作成ウィザードが開始されます。 詳細については、「[Defender for Office 365でのフィッシング攻撃のシミュレート](attack-simulation-training.md)」を参照してください。

:::image type="content" source="../../media/attack-sim-training-overview-recent-simulations-card.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの [概要] タブにある [最近使ったシミュレーション] カード" lightbox="../../media/attack-sim-training-overview-recent-simulations-card.png":::

### <a name="behavior-impact-on-compromise-rate-card"></a>侵害率カードに対する動作の影響

[**概要**] タブ **の [侵害率] カードに対する動作の影響** は、Microsoft 365の履歴データと比較して、ユーザーがシミュレーションにどのように応答したかを示します。 これらの分析情報を使用すると、同じユーザー グループに対して複数のシミュレーションを実行することで、ユーザーの脅威の準備状況の進行状況を追跡できます。

グラフ データ自体には、次の情報が表示されます。

- **予測される侵害率**<sup>\*</sup>: 他のすべてのMicrosoft 365組織で同じ種類のペイロードを使用する攻撃シミュレーション トレーニング シミュレーションの平均侵害率。
- **実際の侵害率**<sup>\*</sup>: シミュレーションのために落ちたユーザーの実際の割合。

グラフ内のデータ ポイントにマウス ポインターを合わせると、実際のパーセンテージ値が表示されます。

カードには、次の概要情報も表示されます。

- **フィッシングの影響を受けにくいユーザー**: シミュレートされた攻撃によって侵害された実際のユーザー数と、予測される侵害率の差。 この数のユーザーは、今後同様の攻撃によって侵害される可能性が低くなります。
- **x% が予測レートより優れている**: 予測される侵害率とは対照的に、ユーザーが全体的にどのように行ったかを示します。

:::image type="content" source="../../media/attack-sim-training-overview-behavior-impact-card.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの [概要] タブの [侵害率カードに対する動作の影響]" lightbox="../../media/attack-sim-training-overview-behavior-impact-card.png":::

より詳細なレポートを表示するには、[ **シミュレーションとトレーニングの有効性レポートの表示**] をクリックします。 このレポートについては、 [この記事の後半で説明します](#training-efficacy-tab-for-the-attack-simulation-report)。

### <a name="simulation-coverage-card"></a>シミュレーション カバレッジ カード

**[概要**] タブの **[シミュレーション カバレッジ**] カードには、シミュレーションを受け取った組織内のユーザー (**シミュレートされたユーザー**) と、シミュレーションを受けていないユーザー (**シミュレートされていないユーザー**) の割合が表示されます。 グラフのセクションにマウス ポインターを合わせると、各カテゴリの実際のユーザー数を確認できます。

**[シミュレーション以外のユーザーに対してシミュレーションを起動** する] を選択すると、シミュレーション作成ウィザードが開始され、シミュレーションを受け取っていないユーザーが **[ターゲット ユーザー**] ページで自動的に選択されます。 詳細については、「[Defender for Office 365でのフィッシング攻撃のシミュレート](attack-simulation-training.md)」を参照してください。

**[シミュレーション カバレッジ レポートの表示**] を選択すると、[攻撃シミュレーション レポートの [ユーザー カバレッジ] タブに移動します](#user-coverage-tab-for-the-attack-simulation-report)。

:::image type="content" source="../../media/attack-sim-training-overview-sim-coverage-card.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの [概要] タブの [シミュレーション カバレッジ] カード" lightbox="../../media/attack-sim-training-overview-sim-coverage-card.png":::

### <a name="training-completion-card"></a>トレーニング完了カード

[**概要**] タブの **[トレーニング完了**] カードは、シミュレーションの結果に基づいてトレーニングを受けたユーザーの割合を次のカテゴリに分類します。

- **Completed**
- **処理中**
- **不完全**

グラフのセクションにマウス ポインターを合わせると、各カテゴリの実際のユーザー数を確認できます。

[ **トレーニング完了レポートの表示** ] を選択すると、 [攻撃シミュレーション レポートの [トレーニング完了] タブに移動します](#training-completion-tab-for-the-attack-simulation-report)。

### <a name="repeat-offenders-card"></a>繰り返し違反者カード

[**概要**] タブの [**繰り返し違反者**] カードには、繰り返し違反者に関する情報が表示されます。 _繰り返し違反者_ とは、連続したシミュレーションによって侵害されたユーザーです。 連続するシミュレーションの既定の数は 2 ですが、攻撃シミュレーション トレーニングの **[設定**] タブで<https://security.microsoft.com/attacksimulator?viewid=setting>値を変更できます。

グラフでは、 [シミュレーションの種類](attack-simulation-training.md#select-a-social-engineering-technique)別に繰り返し違反者データが整理されます。

- **All**
- **マルウェアの添付ファイル**
- **マルウェアへのリンク**
- **資格情報の収集**
- **添付ファイル内のリンク**
- **ドライブバイ URL**

[ **繰り返し違反者レポートの表示** ] を選択すると、 [攻撃シミュレーション レポートの [繰り返し違反者] タブに移動します](#repeat-offenders-tab-for-the-attack-simulation-report)。

### <a name="recommendations-card"></a>おすすめ カード

[**概要**] タブ **の [おすすめ**] カードには、実行するさまざまな種類のシミュレーションが表示されます。

**[起動]** を選択すると、シミュレーション作成ウィザードが開始され、指定されたシミュレーションの種類が **[手法の選択**] ページで自動的に選択されます。 詳細については、「[Defender for Office 365でのフィッシング攻撃のシミュレート](attack-simulation-training.md)」を参照してください。

:::image type="content" source="../../media/attack-sim-training-overview-recommendations-card.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの [概要] タブの [おすすめ カード]" lightbox="../../media/attack-sim-training-overview-recommendations-card.png":::

### <a name="attack-simulation-report"></a>攻撃シミュレーション レポート

[表示] をクリックすると、[**概要**] タブから **攻撃シミュレーション レポート** を開くことができます **。この** 記事で説明されている多くのカードで使用できるレポート ボタン。 レポートに直接移動するには、 <https://security.microsoft.com/attacksimulationreport>

#### <a name="training-efficacy-tab-for-the-attack-simulation-report"></a>攻撃シミュレーション レポートの [トレーニングの有効性] タブ

[ **攻撃シミュレーション] レポート** ページで、[ **トレーニングの効果** ] タブが既定で選択されます。 このタブには、 **侵害率カードに対する動作への影響** と同じ情報と、シミュレーション自体からの追加コンテキストが表示されます。

:::image type="content" source="../../media/attack-sim-report-training-efficacy-view.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション レポートの [トレーニングの有効性] タブ" lightbox="../../media/attack-sim-report-training-efficacy-view.png":::

グラフには、 **予測された侵害率** と **実際の侵害率が表示されます**。 グラフ内のセクションにマウス ポインターを合わせると、実際のパーセンテージ値が表示されます。

グラフの下の詳細テーブルは、次の情報を示しています。

- **シミュレーション名**
- **シミュレーション手法**
- **シミュレーションの戦術**
- **侵害率の予測**
- **実際の侵害率**
- **対象となる合計ユーザー数**
- **クリックされたユーザーの数**

使用できる列見出しをクリックすると、結果を並べ替えることができます。

[ **列のカスタマイズ** ] をクリックして、表示される列を削除します。 完了したら、**[適用]** をクリックします。

[検索] アイコン](../../media/m365-cc-sc-search-icon.png)**の [検索**] ボックスを使用して![、**シミュレーション名** または **シミュレーション手法** で結果をフィルター処理します。 ワイルドカードはサポートされていません。

[エクスポート] アイコンを ![クリックした場合。](../../media/m365-cc-sc-download-icon.png) **[レポートのエクスポート]** ボタンをクリックすると、レポート生成の進行状況が完了の割合として表示されます。 開いたダイアログで、.csv ファイルを開き、.csv ファイルを保存し、選択内容を記憶することができます。

#### <a name="user-coverage-tab-for-the-attack-simulation-report"></a>攻撃シミュレーション レポートの [ユーザー カバレッジ] タブ

:::image type="content" source="../../media/attack-sim-report-user-coverage-view.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション レポートの [ユーザー カバレッジ] タブ" lightbox="../../media/attack-sim-report-user-coverage-view.png":::

[ **ユーザー カバレッジ** ] タブのグラフには、[ **シミュレートされたユーザー** ] と [ **シミュレートされていないユーザー] が表示されます**。 グラフ内のデータ ポイントにマウス ポインターを合わせると、実際の値が表示されます。

グラフの下の詳細テーブルは、次の情報を示しています。

- **Username**
- **電子メール アドレス**
- **シミュレーションに含まれる**
- **最後のシミュレーションの日付**
- **最後のシミュレーション結果**
- **クリックされた回数**
- **侵害された数**

使用できる列見出しをクリックすると、結果を並べ替えることができます。

[ **列のカスタマイズ** ] をクリックして、表示される列を削除します。 完了したら、**[適用]** をクリックします。

[検索] アイコン](../../media/m365-cc-sc-search-icon.png)**の [検索**] ボックスを使用して![、**ユーザー名** または **メール アドレス** で結果をフィルター処理します。 ワイルドカードはサポートされていません。

[エクスポート] アイコンを ![クリックした場合。](../../media/m365-cc-sc-download-icon.png) **[レポートのエクスポート]** ボタンをクリックすると、レポート生成の進行状況が完了の割合として表示されます。 開いたダイアログで、.csv ファイルを開き、.csv ファイルを保存し、選択内容を記憶することができます。

#### <a name="training-completion-tab-for-the-attack-simulation-report"></a>攻撃シミュレーション レポートの [トレーニング完了] タブ

:::image type="content" source="../../media/attack-sim-report-training-completion-view.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション レポートの [トレーニング完了] タブ" lightbox="../../media/attack-sim-report-training-completion-view.png":::

[**トレーニング完了**] タブのグラフには、**完了、****進行中**、および **不完全** なシミュレーションの数が表示されます。 グラフ内のセクションにマウス ポインターを合わせると、実際の値が表示されます。

グラフの下の詳細テーブルは、次の情報を示しています。

- **Username**
- **電子メール アドレス**
- **シミュレーションに含まれる**
- **最後のシミュレーションの日付**
- **最後のシミュレーション結果**
- **完了した最新のトレーニングの名前**
- **完了日**
- **すべてのトレーニング**

使用できる列見出しをクリックすると、結果を並べ替えることができます。

[ **列のカスタマイズ** ] をクリックして、表示される列を削除します。 完了したら、**[適用]** をクリックします。

[フィルター] アイコンをクリック ![します。](../../media/m365-cc-sc-filter-icon.png) **フィルター処理** して、次の 1 つ以上の値でグラフと詳細テーブルをフィルター処理します。

- **Completed**
- **処理中**
- **All**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

[検索] アイコン](../../media/m365-cc-sc-search-icon.png)**の [検索**] ボックスを使用して![、**ユーザー名** または **メール アドレス** で結果をフィルター処理します。 ワイルドカードはサポートされていません。

[エクスポート] アイコンを ![クリックした場合。](../../media/m365-cc-sc-download-icon.png) **[レポートのエクスポート]** ボタンをクリックすると、レポート生成の進行状況が完了の割合として表示されます。 開いたダイアログで、.csv ファイルを開き、.csv ファイルを保存し、選択内容を記憶することができます。

#### <a name="repeat-offenders-tab-for-the-attack-simulation-report"></a>攻撃シミュレーション レポートの [違反者の繰り返し] タブ

:::image type="content" source="../../media/attack-sim-report-repeat-offenders-view.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション レポートの [繰り返し違反者] タブ" lightbox="../../media/attack-sim-report-repeat-offenders-view.png":::

_繰り返し違反者_ とは、連続したシミュレーションによって侵害されたユーザーです。 連続するシミュレーションの既定の数は 2 ですが、攻撃シミュレーション トレーニングの **[設定**] タブで<https://security.microsoft.com/attacksimulator?viewid=setting>値を変更できます。

[ **違反者の繰り返し** ] タブで、グラフは [シミュレーションの種類](attack-simulation-training.md#select-a-social-engineering-technique)別に繰り返し違反者データを整理します。

- **All**
- **資格情報の収集**
- **マルウェアの添付ファイル**
- **添付ファイル内のリンク**
- **マルウェアへのリンク**
- **ドライブバイ URL**

グラフ内のデータ ポイントにマウス ポインターを合わせると、実際の値が表示されます。

グラフの下の詳細テーブルは、次の情報を示しています。

- **ユーザー**
- **繰り返し数**
- **シミュレーションの種類**
- **シミュレーション**

使用できる列見出しをクリックすると、結果を並べ替えることができます。

[ **列のカスタマイズ** ] をクリックして、表示される列を削除します。 完了したら、**[適用]** をクリックします。

[フィルター] アイコンをクリック ![します。](../../media/m365-cc-sc-filter-icon.png) **フィルター処理** して、シミュレーションの種類の値の一部または全部でグラフと詳細テーブルをフィルター処理します。

- **資格情報の収集**
- **マルウェアの添付ファイル**
- **添付ファイル内のリンク**
- **マルウェアへのリンク**
- **ドライブバイ URL**

フィルターの構成が完了したら、[ **適用**]、[ **キャンセル]**、または **[フィルターのクリア**] をクリックします。

[検索] アイコン](../../media/m365-cc-sc-search-icon.png)**の [検索**] ボックスを使用して![、任意の列値で結果をフィルター処理します。 ワイルドカードはサポートされていません。

[エクスポート] アイコンを ![クリックした場合。](../../media/m365-cc-sc-download-icon.png) **[レポートのエクスポート]** ボタンをクリックすると、レポート生成の進行状況が完了の割合として表示されます。 開いたダイアログで、.csv ファイルを開き、.csv ファイルを保存し、選択内容を記憶することができます。

## <a name="insights-and-reports-in-the-simulation-details-of-attack-simulation-training"></a>攻撃シミュレーション トレーニングのシミュレーションの詳細に関するインサイトとレポート

**[シミュレーション**] タブに移動するには、Microsoft 365 Defender ポータルを<https://security.microsoft.com>開き、[**電子メール & コラボレーション** \> **攻撃シミュレーション トレーニング**] に移動し、[**シミュレーション**] タブを選択します。**[攻撃シミュレーション トレーニング**] ページ **の [シミュレーション**] タブに直接移動するには、.<https://security.microsoft.com/attacksimulator?viewid=simulations>

一覧からシミュレーションを選択すると、詳細ページが開きます。 このページには、予想されるシミュレーションの構成設定 (状態、起動日、使用されたペイロードなど) が含まれています。

このセクションの残りの部分では、シミュレーションの詳細ページで使用できる分析情報とレポートについて説明します。

### <a name="simulation-impact-section"></a>[シミュレーションの影響] セクション

シミュレーションの詳細ページの **[シミュレーションへの影響** ] セクションには、シミュレーションによって完全にだまされたユーザーの数と、シミュレーション内のユーザーの合計数が表示されます。 表示される情報は、シミュレーションの種類によって異なります。 例として以下のようなものがあります。

- リンク: **入力された資格情報** と資格情報 **を入力しませんでした**。

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-links.png" alt-text="リンク関連のシミュレーションの詳細については、「シミュレーションへの影響」セクションを参照してください。" lightbox="../../media/attack-sim-training-sim-details-sim-impact-links.png":::

- 添付ファイル: **開いた添付ファイル** と **添付ファイルを開きませんでした**。

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-attachments.png" alt-text="添付ファイル関連のシミュレーションの詳細に関するシミュレーション影響セクション" lightbox="../../media/attack-sim-training-sim-details-sim-impact-attachments.png":::

グラフ内のセクションにマウス ポインターを合わせると、各カテゴリの実際の数値が表示されます。

### <a name="all-user-activity-section"></a>[すべてのユーザー アクティビティ] セクション

シミュレーションの詳細ページ **の [すべてのユーザー アクティビティ** ] セクションには、シミュレーションの可能な結果の数値が表示されます。 表示される情報は、シミュレーションの種類によって異なります。 例として以下のようなものがあります。

- **SuccessfullyDeliveredEmail**
- **ReportedEmail**: シミュレーション メッセージを疑わしいと報告したユーザーの数。
- リンク：
  - **EmailLinkClicked**: シミュレーション メッセージのリンクをクリックしたユーザーの数。
  - **CredSupplied**: リンクをクリックすると、資格情報を指定したユーザーの数が表示されます。

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-links.png" alt-text="リンク関連のシミュレーションの詳細については、[すべてのユーザー アクティビティ] セクション" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-links.png":::

- 添付 ファイル：
  - **AttachmentOpened**: シミュレーション メッセージで添付ファイルを開いたユーザーの数。

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png" alt-text="添付ファイル関連のシミュレーションの詳細に関する [すべてのユーザー アクティビティ] セクション" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png":::

### <a name="training-completion-section"></a>トレーニング完了セクション

シミュレーションの詳細ページの **[トレーニングの完了** ] セクションには、シミュレーションに必要なトレーニングと、トレーニングを完了したユーザーの数が表示されます。

:::image type="content" source="../../media/attack-sim-training-sim-details-training-completed.png" alt-text="添付ファイル関連のシミュレーションの詳細に関するトレーニング完了セクション" lightbox="../../media/attack-sim-training-sim-details-training-completed.png":::

## <a name="recommended-actions-section"></a>[推奨されるアクション] セクション

シミュレーションの詳細ページの **[推奨されるアクション]** セクションには、 [Microsoft Secure Score](../defender/microsoft-secure-score.md) からの推奨事項アクションと、アクションがセキュリティスコアに与える影響が表示されます。 これらの推奨事項は、シミュレーションで使用されたペイロードに基づいており、ユーザーと環境を保護するのに役立ちます。 一覧から **[改善] アクション** を選択すると、推奨されるアクションを実装する場所に移動します。

:::image type="content" source="../../media/attack-sim-training-sim-details-recommended-actions.png" alt-text="攻撃シミュレーション トレーニングに関する推奨事項アクション セクション" lightbox="../../media/attack-sim-training-sim-details-recommended-actions.png":::

## <a name="related-links"></a>関連リンク

[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

[フィッシング攻撃シミュレーションを作成する](attack-simulation-training.md)

[ユーザーをトレーニングするためのペイロードを作成する](attack-simulation-training-payloads.md)
