---
title: 組織の脆弱性 - 脅威と脆弱性の管理
description: 組織内で実行されているソフトウェアで見つかった弱点の一般的な脆弱性と公開 (CVE) ID を一覧表示します。 Microsoft Defender for Endpoint 脅威と脆弱性の管理機能によって検出されます。
keywords: Microsoft Defender for Endpoint脅威& 脆弱性の管理、脅威と脆弱性の管理、Microsoft Defender for Endpoint tvm の弱点ページ、tvm を介した弱点の検出、tvm の脆弱性リスト、tvm の脆弱性の詳細
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a2f3db3a28755c5e2bce46f7134eb1c977d1aa0a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476645"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>組織の脆弱性 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!IMPORTANT]
> 脅威と脆弱性の管理は、アプリケーションとコンポーネントの Log4j の脆弱性を特定するのに役立ちます。 [詳細情報](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM) を参照してください。

脅威と脆弱性の管理は、Defender for Endpoint のエンドポイント保護で同じシグナルを使用して、脆弱性をスキャンして検出します。

[ **弱点]** ページには、一般的な脆弱性と公開 (CVE) ID を一覧表示することで、デバイスが公開されるソフトウェアの脆弱性が一覧表示されます。 重大度、一般的な脆弱性スコアリング システム (CVSS) の評価、組織内の有病率、対応する侵害、脅威の分析情報などを表示することもできます。

> [!NOTE]
> 脆弱性に正式な CVE-ID が割り当てられていない場合、脆弱性名は脅威と脆弱性の管理によって割り当てられます。

> [!TIP]
> 新しい脆弱性イベントに関する電子メールを取得するには、「[Microsoft Defender for Endpointで脆弱性の電子メール通知を構成](configure-vulnerability-email-notifications.md)する」を参照してください。

## <a name="navigate-to-the-weaknesses-page"></a>[弱点] ページに移動する

[弱点] ページには、いくつかの異なる方法でアクセスします。

- [Microsoft 365 Defender ポータル](portal-overview.md)の **[脆弱性管理**] ナビゲーション メニューから **[弱点**] を選択する
- グローバル検索

### <a name="navigation-menu"></a>[ナビゲーション] メニュー

**[脆弱性管理**] ナビゲーション メニューに移動し、[**弱点**] を選択して CVE の一覧を開きます。

### <a name="vulnerabilities-in-global-search"></a>グローバル検索の脆弱性

1. グローバル検索ドロップダウン メニューに移動します。
2. **探している** 一般的な脆弱性と公開 (CVE) ID で [脆弱性とキー] を選択し、検索アイコンを選択します。 **[弱点]** ページが開き、探している CVE 情報が表示されます。

:::image type="content" source="images/tvm-vuln-globalsearch.png" alt-text="ドロップダウン オプションの脆弱性が選択されたグローバル検索ボックス" lightbox="images/tvm-vuln-globalsearch.png":::

3. CVE を選択して、脆弱性の説明、詳細、脅威の分析情報、公開されたデバイスなど、詳細情報を含むポップアップ パネルを開きます。

**[弱点**] ページで残りの脆弱性を確認するには、「CVE」と入力し、検索を選択します。

## <a name="weaknesses-overview"></a>弱点の概要

公開されているデバイスの脆弱性を修復して、資産と組織へのリスクを軽減します。 **[公開デバイス] 列に** 0 が表示されている場合は、危険にさらされていないことを意味します。

:::image type="content" source="images/tvm-weaknesses-overview.png" alt-text="弱点のランディング ページ" lightbox="images/tvm-weaknesses-overview.png":::

### <a name="breach-and-threat-insights"></a>侵害と脅威の分析情報

アイコンの色が赤の場合は、[脅威] 列に関連する侵害と **脅威** の分析情報を表示します。

 > [!NOTE]
 > 継続的な脅威に関連付けられている推奨事項に常に優先順位を付けます。 これらの推奨事項には、脅威分析情報アイコン ![の赤いバグの単純な描画が付いています。](images/tvm_bug_icon.png) および侵害分析情報アイコン ![ターゲットに当たる矢印の単純な描画.](images/tvm_alert_icon.png).

侵害分析情報アイコンは、組織で脆弱性が見つかった場合に強調表示されます。
![アイコンの上にマウス ポインターを置いたときに表示される可能性がある侵害分析情報テキストの例。 この 1 つは、「アクティブなアラートの可能性は、この推奨事項に関連付けられます。](images/tvm-breach-insights.png)

脅威分析情報アイコンは、組織で見つかった脆弱性に関連する悪用がある場合に強調表示されます。 アイコンの上にマウス ポインターを置くと、脅威が悪用キットの一部であるか、特定の高度な永続的なキャンペーンやアクティビティ グループに接続されているかが示されます。 利用可能な場合は、ゼロデイの悪用ニュース、開示、または関連するセキュリティ アドバイザリを含む Threat Analytics レポートへのリンクがあります。

![アイコンの上にマウス ポインターを置いたときに表示される可能性がある脅威分析情報テキスト。 この 1 つは、複数の箇条書きとリンクされたテキストを持っています。](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>脆弱性の分析情報を取得する

CVE を選択すると、ポップアップ パネルが開き、脆弱性の説明、詳細、脅威の分析情報、公開されたデバイスなどの詳細情報が表示されます。

- "OS 機能" カテゴリは、関連するシナリオで表示されます
- 公開されたデバイスを使用して、CVE ごとに関連するセキュリティに関する推奨事項にアクセスできます

 :::image type="content" source="images/tvm-weakness-flyout400.png" alt-text="[脆弱性の説明] ページ" lightbox="images/tvm-weakness-flyout400.png":::

### <a name="software-that-isnt-supported"></a>サポートされていないソフトウェア

脅威& 脆弱性の管理で現在サポートされていないソフトウェアの CVE は、[弱点] ページに引き続き表示されます。 ソフトウェアはサポートされていないため、使用できるデータは限られています。

公開されたデバイス情報は、サポートされていないソフトウェアを使用する CVE では使用できません。 [公開されているデバイス] セクションで [使用できません] オプションを選択して、サポートされていないソフトウェアでフィルター処理します。

:::image type="content" alt-text="公開されたデバイス フィルター。" source="images/tvm-exposed-devices-filter.png":::

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>他の場所で一般的な脆弱性と公開 (CVE) エントリを表示する

### <a name="top-vulnerable-software-in-the-dashboard"></a>ダッシュボードの脆弱なソフトウェアの上位

1. [脅威と脆弱性の管理 ダッシュボード](tvm-dashboard-insights.md)に移動し、**脆弱なソフトウェアの上位** ウィジェットまで下にスクロールします。 各ソフトウェアで見つかった脆弱性の数と、脅威情報、および時間の経過に伴うデバイスの露出の概要が表示されます。

   :::image type="content" source="images/tvm-top-vulnerable-software500.png" alt-text="[脆弱なソフトウェアの上位] ページの [弱点] 列" lightbox="images/tvm-top-vulnerable-software500.png":::

2. 調査するソフトウェアを選択して、ドリルダウン ページに移動します。

3. [ **検出された脆弱性** ] タブを選択します。

4. 脆弱性の詳細の詳細については、調査する脆弱性を選択してください

   :::image type="content" source="images/windows-server-drilldown.png" alt-text="Windows Server 2019 のドリルダウンの概要" lightbox="images/windows-server-drilldown.png":::

### <a name="discover-vulnerabilities-in-the-device-page"></a>デバイス ページで脆弱性を検出する

デバイス ページに関連する弱点情報を表示します。

1. Microsoft 365 Defenderナビゲーション メニュー バーに移動し、デバイス アイコンを選択します。 [ **デバイス インベントリ]** ページが開きます。

2. [ **デバイス インベントリ** ] ページで、調査するデバイス名を選択します。

   :::image type="content" source="images/tvm_machinetoinvestigate.png" alt-text="調査対象のデバイスが選択されたデバイスの一覧" lightbox="images/tvm_machinetoinvestigate.png":::

3. デバイス ページが開き、調査するデバイスの詳細と応答オプションが表示されます。

4. [ **検出された脆弱性**] を選択します。

   :::image type="content" source="images/tvm-discovered-vulnerabilities.png" alt-text="詳細と応答オプションを含む [デバイス] ページ。" lightbox="images/tvm-discovered-vulnerabilities.png":::

5. 調査する脆弱性を選択して、CVE の詳細 (脆弱性の説明、脅威の分析情報、検出ロジックなど) を含むポップアップ パネルを開きます。

#### <a name="cve-detection-logic"></a>CVE 検出ロジック

ソフトウェアの証拠と同様に、脆弱であることを示すためにデバイスに適用した検出ロジックを示すようになりました。 新しいセクションは "検出ロジック" と呼ばれ (デバイス ページで検出された脆弱性で)、検出ロジックとソースを示します。

"OS 機能" カテゴリは、関連するシナリオにも表示されます。 CVE は、特定の OS コンポーネントが有効になっている場合にのみ、脆弱な OS を実行するデバイスに影響します。 たとえば、Windows Server 2019 または Windows Server 2022 に DNS コンポーネントに脆弱性があるとします。 この新しい機能では、OS で DNS 機能が有効になっている Windows Server 2019 および Windows Server 2022 デバイスにのみこの CVE をアタッチします。

:::image type="content" source="images/tvm-cve-detection-logic.png" alt-text="デバイスで検出されたソフトウェアと KB を一覧表示する検出ロジックの例" lightbox="images/tvm-cve-detection-logic.png":::

## <a name="report-inaccuracy"></a>レポートの不正確さ

あいまい、不正確、または不完全な情報が表示された場合は、誤検知を報告します。 既に修復されたセキュリティに関する推奨事項について報告することもできます。

1. [弱点] ページで CVE を開きます。
2. [ **レポートの不正確さ]** を選択すると、ポップアップ ウィンドウが開きます。
3. ドロップダウン メニューから不正確なカテゴリを選択し、メール アドレスと不正確な詳細を入力します。
4. **[送信]** を選択します。 フィードバックはすぐに脅威と脆弱性の管理エキスパートに送信されます。

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [ソフトウェア インベントリ](tvm-software-inventory.md)
- [ダッシュボード インサイト](tvm-dashboard-insights.md)
- [Microsoft Defender for Endpointデバイスの一覧を表示および整理する](machines-view-overview.md)
