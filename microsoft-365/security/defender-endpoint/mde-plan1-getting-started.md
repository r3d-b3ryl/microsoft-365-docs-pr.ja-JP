---
title: Microsoft Defender for Endpoint Plan 1 の概要 (プレビュー)
description: Defender for Endpoint Plan 1 の使用を開始します。 Defender for Cloud を使用し、アラートとデバイスを管理し、レポートを表示する方法について学習します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 10/01/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: e361c8a93d35a9e0cc589b8d47adadfe54ef141b
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111137"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1-preview"></a>Microsoft Defender for Endpoint Plan 1 の概要 (プレビュー)

> [!TIP]
> ユーザーまたは A3 Microsoft 365 E3が、Microsoft 365 E5 A5 を使用していない場合は、プレビュー プログラムに [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) サインアップしてください。

Microsoft 365 Defender ポータル ( ) を使用すると、検出された脅威に関する情報を表示し、アラートとインシデントを管理し、検出された脅威に対して必要なアクションを実行し、デバイス [https://security.microsoft.com](https://security.microsoft.com) を管理できます。 このMicrosoft 365 Defenderポータルでは、Defender for Endpoint Plan 1 (プレビュー) で取得した脅威保護機能の操作を開始できます。 次のセクションでは、開始する方法について説明します。

- [Microsoft 365 Defender ポータル](#the-microsoft-365-defender-portal)
- [インシデントとアラートの表示と管理&する](#view-and-manage-incidents--alerts)
- [デバイスの管理](#manage-devices)
- [レポートの表示](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータル

[Microsoft 365 Defender] ポータル ( [https://security.microsoft.com](https://security.microsoft.com) ) は、アラートの表示、デバイスの管理、レポートの表示を行う場所です。 次の図に示すように、Microsoft 365 Defenderポータルにサインインすると、ホーム ページから開始します。

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Microsoft 365 Defender ポータル":::

[ホーム] ページには、検出されたアラート、デバイスの状態、および脅威のスナップショット集計ビューがセキュリティ チームに提供されます。 Defender for Cloud は、セキュリティ運用チームが探している情報を迅速かつ簡単に検索できるようセットアップされています。

> [!NOTE]
> この記事に示す例は、ポータルに表示される内容と異なるMicrosoft 365 Defenderがあります。 ポータルに表示される内容は、ライセンスとアクセス許可によって異なります。 さらに、セキュリティ チームは、カードの追加、削除、および並び変更を行って、組織のポータルをカスタマイズできます。

### <a name="cards-highlight-key-information-and-include-recommendations"></a>カードは重要な情報を強調表示し、推奨事項を含める

ホーム ページには、次の図に示すアクティブ インシデント カードなどのカードが含まれます。

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="アクティブなインシデント カード":::

カードは、詳細な情報を表示するために選択できるリンクまたはボタンと共に、一目で情報を提供します。 この例のアクティブ インシデント カードを参照して、[すべてのインシデントを表示] を選択して、インシデントの一覧に移動できます。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="インシデント 一覧":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>ナビゲーション バーを使用すると、アラート、アクション センターなど、簡単に検索できます。

画面の左側のナビゲーション バーを使用すると、インシデント、アラート、アクション センター、レポート、および設定の間を簡単に移動できます。 次の表に、ナビゲーション バーについて説明します。<br/><br/>

| ナビゲーション バーアイテム | [説明] |
|:---|:---|
| **ホーム** | ポータルのホーム ページに移動Microsoft 365 Defender[します](../defender/microsoft-365-security-center-mde.md)。 |
| **インシデント&アラート** | 展開してインシデントと **アラートを****表示します**。 |
| **インシデント&アラート**  > **インシデント** | [インシデント] リスト **に移動** します。 インシデントは、アラートがトリガーまたは脅威が検出されると作成されます。 既定では、[インシデント] **リスト** には過去 30 日間のデータが表示され、最新のインシデントが最初に表示されます。 <br/><br/> 詳細については、「インシデント」 [を参照してください](view-incidents-queue.md)。 |
| **インシデント&アラート**  > **アラート** | [アラート] リスト **(アラート** キューとも呼ばれます) **に移動します**。 疑わしいファイル、プロセス、または動作が検出されると、アラートがトリガーされます。 既定では、[アラート] **リストには** 過去 30 日間のデータが表示され、最新のアラートが最初に表示されます。 <br/><br/> 詳細については、「アラート」を [参照してください](alerts-queue.md)。 |
| **アクション センター** | 修復アクションと手動応答アクションを追跡するアクション センターに移動します。 アクション センターは、次のようなアクティビティを追跡します。 <br/>- Microsoft Defender ウイルス対策ファイルを検出し、そのファイルをブロック/削除します。 <br/>- セキュリティ チームがデバイスを分離します。<br/>- Defender for Endpoint は、ファイルを検出して検疫します。 <br/><br/> 詳細については、「アクション センター [」を参照してください](auto-investigation-action-center.md)。 |
| **セキュア スコア** | 組織のセキュリティ体制の表現と、改善のアクションと指標の一覧を表示します。 <br/><br/> 詳細については [、「Microsoft Secure Score」を参照してください](../defender/microsoft-secure-score.md)。 |
| **ラーニング ハブ** | アクセスできるラーニング パスの一覧に移動し、セキュリティ機能の詳細Microsoft 365確認します。  |
| **エンドポイント**  > **検索** | 特定のデバイスをデバイス名で検索できるページに移動します。 結果の一覧では、リスク レベルや正常性状態などの詳細を一目で確認できます。 |
|  **エンドポイント**  > **デバイス インベントリ** | Defender for Endpoint にオンボードされているデバイスのリストに移動します。 デバイスの露出やリスク レベルなどの情報を提供します。 <br/><br/> 詳細については、「デバイス インベントリ [」を参照してください](machines-view-overview.md)。 |
|  **エンドポイント**  > **構成&ベースライン** | [セキュリティ基準] と **[構成管理] が****表示されます**。 |
|  **エンドポイント**  > **構成&基準**  > **セキュリティベースライン** | セキュリティ基準は、事前に構成されたポリシーと設定のグループであり、推奨されるセキュリティ設定を効率的かつ効果的に適用するのに役立ちます。 基準計画には、業界のベスト プラクティスに基づく設定が含まれます。 既定の設定を維持するか、組織のニーズに合わせて基準計画をカスタマイズできます。 <br/><br/> 詳細については[、「Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。 |
|  **エンドポイント**  > **構成&基準**  > **構成管理** | [デバイス構成管理] **ページに移動** し、オンボードデバイスに関する情報を表示し、さらに多くのデバイスをオンボードする手順を実行できます。 |
| **レポート** | 脅威保護レポート、デバイスの正常性とコンプライアンス[](threat-protection-reports.md)レポート、Web[](machine-reports.md)保護レポートなどのレポート[に移動します](web-protection-overview.md)。 |
| **正常性** | サービス正常性とメッセージ **センターへの** リンク **が含まれています**。  |
| **正常性**  > **サービスの正常性** | [サービス正常性] ページの [サービス正常性] ページにMicrosoft 365 管理センター。 このページでは、組織のサブスクリプションで利用可能なすべてのサービスの正常性状態を表示できます。   |
| **正常性**  > **メッセージ センター** | [メッセージ] ページの [メッセージ] センターに移動Microsoft 365 管理センター。 メッセージ センターは、計画された変更に関する情報を提供します。 各メッセージには、何が来ているか、ユーザーに与える影響、および変更を管理する方法が説明されています。 |  
| **ロール&アクセス許可** | ポータルを使用するためのアクセス許可を付与Microsoft 365 Defenderします。 アクセス許可は、アクセス許可 (Azure Active Directory) のAzure AD。 役割を選択すると、フライアウト ウィンドウが表示されます。 このフライアウトには、役割グループ内Azure ADメンバーを追加または削除できる場所へのリンクが含まれる。 <br/><br/> 詳細については、「役割ベースのアクセス [制御を使用してポータル アクセスを管理する」を参照してください](rbac.md)。  |
| **設定** | [セキュリティ センター] と [エンドポイントMicrosoft 365 Defender Defender for **Endpoints]** の一般的な設定に **移動します**。 <br/><br/> 詳細については、「設定」[を参照してください](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)。 |
| **その他のリソース** | その他のポータルとセンターの一覧を表示します (Azure Active Directory、Microsoft 365 コンプライアンス センター。 <br/><br/> 詳細については、「Microsoft セキュリティ [ポータルと管理センター」を参照してください](../defender/portals.md)。 |

> [!TIP]
> 詳細については、「ポータルの概要[」Microsoft 365 Defenderを参照してください](../defender/microsoft-365-security-center-mde.md)。

## <a name="view-and-manage-incidents--alerts"></a>インシデントとアラートの表示と管理&する

ポータルにサインインするMicrosoft 365 Defender、インシデントとアラートを表示および管理してください。 [インシデント] リスト **から開始** します。 次の図は、重大度が高いインシデントと中程度の重大度を持つインシデントの一覧を示しています。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="インシデント 一覧":::

インシデントを選択して、インシデントの詳細を表示します。 詳細には、トリガーされたアラート、影響を受けたデバイスとユーザーの数、その他の詳細が含まれます。 次の図は、インシデントの詳細の例を示しています。

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="インシデントの詳細":::

[アラート **]** タブ、[**デバイス**] タブ、および [ユーザー] タブを使用して、トリガーされたアラート、影響を受けたデバイス、影響を受けたユーザー アカウントなどの詳細を表示します。  そこから、デバイスの分離、ファイルの停止と隔離などの手動応答アクションを実行できます。

> [!TIP]
> インシデント ビューの使用の詳細については **、「インシデント** の管理 [」を参照してください](manage-incidents.md)。

## <a name="manage-devices"></a>デバイスを管理する

組織のデバイスを表示および管理するには、ナビゲーション バーの [ **エンドポイント**] で、[デバイス インベントリ] **を選択します**。 次の図に示すように、デバイスの一覧が表示されます。

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="デバイス一覧":::

一覧には、アラートが生成されたデバイスが含まれます。 既定では、表示されるデータは過去 30 日間で、最新のアイテムが最初に一覧表示されます。 デバイスを選択して、デバイスの詳細を表示します。 次の図に示すように、フライアウト ウィンドウが開きます。

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="選択したデバイスの詳細":::

フライアウト ウィンドウには、デバイスのアクティブなアラートなどの詳細が表示され、デバイスの分離などのアクションを実行するリンクが含まれます。

デバイスにアクティブなアラートがある場合は、それらをフライアウト ウィンドウで表示できます。 個別のアラートを選択して、詳細を表示します。 または、デバイスの分離などのアクションを実行して、他のデバイスに感染するリスクを最小限に抑えながら、デバイスをさらに調査できます。

> [!TIP]
> 詳細については、「Defender [for Endpoint devices list」の「デバイスを調査する」を参照してください](investigate-machines.md)。

## <a name="view-reports"></a>レポートの表示

Defender for Endpoint Plan 1 では、ポータルでいくつかのレポートをMicrosoft 365 Defenderできます。 レポートにアクセスするには、次の手順を実行します。

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション バーで、[レポート] を **選択します**。

3. 一覧でレポートを選択します。 次の 3 つのレポートが表示されます。

   - 脅威に対する保護のレポート
   - デバイス正常性レポート
   - Web 保護レポート

> [!TIP]
> 詳細については、「脅威保護レポート [」を参照してください](threat-protection-reports.md)。

### <a name="threat-protection-report"></a>脅威に対する保護のレポート

脅威保護レポートにアクセスするには、Microsoft 365 Defenderポータルで [レポート] を選択し、[脅威保護]**を選択します**。 脅威保護レポートには、アラートの傾向、状態、カテゴリなどが表示されます。 ビューは、次の図に示 **すように、アラート** の傾向と **アラート** の状態の 2 つの列に配置されます。

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="脅威に対する保護のレポート":::

下にスクロールすると、各リストのすべてのビューが表示されます。

- 既定では、[アラートの傾向]列のビューには過去 30 日間のデータが表示されますが、過去 3 か月、過去 6 か月、またはユーザー設定の時間範囲 (最大 180 日間) のデータを表示するビューを設定できます。
- [アラートの状態] **列のビュー** は、前の営業日のスナップショットです。

> [!TIP]
> 詳細については、「Defender [for Endpoint の脅威保護レポート」を参照してください](threat-protection-reports.md)。

### <a name="device-health-report"></a>デバイス正常性レポート

デバイス正常性レポートにアクセスするには、Microsoft 365 Defenderポータルで [レポート]を選択し、[デバイスの正常性]**を選択します**。 [デバイスの正常性] レポートには、組織内のデバイス全体の正常性状態とウイルス対策が表示されます。 脅威保護レポート[と](#threat-protection-report)同様に、ビューは次の図に示すように、デバイスの傾向とデバイスの概要の 2 つの列に配置されます。

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="デバイス正常性レポート":::

下にスクロールすると、各リストのすべてのビューが表示されます。 既定では、[デバイスの傾向]列のビューには過去 30 日間のデータが表示されますが、過去 3 か月、過去 6 か月、またはユーザー設定の時間範囲 (最大 180 日間) のデータを表示するビューを変更できます。 [ **デバイスの概要]** ビューは、前の営業日のスナップショットです。

> [!TIP]
> 詳細については、「デバイスの正常性 [」を参照してください](machine-reports.md)。

### <a name="web-protection-report"></a>Web 保護レポート

デバイス正常性レポートにアクセスするには、Microsoft 365 Defenderポータルで [レポート] を選択し、[Web 保護]**を選択します**。 Web 保護レポートには、次の図に示すように、悪意のある URL やブロックされた URL へのアクセス試行など、時間のかかる検出が表示されます。

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Web 保護レポート":::

下にスクロールすると、Web 保護レポートのすべてのビューが表示されます。 一部のビューには、詳細の表示、脅威保護機能の構成、Defender for Endpoint の例外として機能するインジケーターの管理を行えるリンクが含まれます。

> [!TIP]
> 詳細については、「Web 保護」 [を参照してください](web-protection-overview.md)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpoint Plan 1 の管理 (プレビュー)](mde-p1-maintenance-operations.md)
- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)
