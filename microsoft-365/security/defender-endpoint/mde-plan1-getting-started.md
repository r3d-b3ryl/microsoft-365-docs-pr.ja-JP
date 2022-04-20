---
title: Microsoft Defender for Endpoint プラン 1 を使用した概要
description: Defender for Endpoint プラン 1 を使用概要。 Defender for Cloudを使用し、アラートとデバイスを管理し、レポートを表示する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-get-started
ms.openlocfilehash: d332cbf32f5423fb16abb158f9a30a18c2391a22
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939347"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender for Endpoint プラン 1 を使用した概要

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) を使用すると、検出された脅威に関する情報の表示、アラートとインシデントの管理、検出された脅威に対する必要なアクションの実行、デバイスの管理を行うことができます。 Microsoft 365 Defender ポータルでは、Defender for Endpoint プラン 1 で取得する脅威保護機能との対話を開始できます。 次のセクションでは、作業を開始する方法について説明します。

- [Microsoft 365 Defender ポータル](#the-microsoft-365-defender-portal)
- [アラート&インシデントの表示と管理](#view-and-manage-incidents--alerts)
- [デバイスの管理](#manage-devices)
- [レポートの表示](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータル

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) では、アラートの表示、デバイスの管理、レポートの表示を行います。 Microsoft 365 Defender ポータルにサインインすると、次の図に示すようにホーム ページから開始します。

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Microsoft 365 Defenderのポータル" lightbox="../../media/mde-p1/m365-defender-portal.png":::

ホーム ページには、検出されたアラート、デバイスの状態、脅威のスナップショット集計ビューがセキュリティ チームに提供されます。 Defender for Cloudは、セキュリティ運用チームが探している情報をすばやく簡単に見つけられるように設定されています。

> [!NOTE]
> この記事に示す例は、Microsoft 365 Defender ポータルに表示されているものとは異なる場合があります。 ポータルに表示される内容は、ライセンスとアクセス許可によって異なります。 さらに、セキュリティ チームは、カードを追加、削除、並べ替えることで、組織のポータルをカスタマイズできます。

### <a name="cards-highlight-key-information-and-include-recommendations"></a>カードはキー情報を強調表示し、推奨事項を含めます

ホーム ページには、次の図に示すアクティブインシデント カードなどのカードが含まれています。

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="アクティブなインシデント カード" lightbox="../../media/mde-p1/active-incidents-card.png":::

カードには、詳細情報を表示するために選択できるリンクまたはボタンと共に、一目で情報が表示されます。 アクティブインシデント カードの例を参照して、[ **すべてのインシデントを表示]** を選択してインシデントの一覧に移動できます。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="インシデントの一覧" lightbox="../../media/mde-p1/incidents.png":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>ナビゲーション バーを使用すると、アラートやアクション センターなどを簡単に見つけることができます

画面の左側にあるナビゲーション バーを使用すると、インシデント、アラート、アクション センター、レポート、および設定の間を簡単に移動できます。 次の表では、ナビゲーション バーについて説明します。<br/><br/>

| ナビゲーション バー項目 | 説明 |
|:---|:---|
| **ホーム** | [Microsoft 365 Defender ポータル](../defender/microsoft-365-security-center-mde.md)のホーム ページに移動します。 |
| **インシデント&アラート** | 展開してインシデントとアラート **を** 表示 **します**。 |
| **インシデント&アラート** > **事件** | **インシデント** の一覧に移動します。 インシデントは、アラートがトリガーされたり、脅威が検出されたりしたときに作成されます。 既定では、[インシデント] リスト **には** 過去 30 日間のデータが表示され、最新のインシデントが最初に表示されます。 <br/><br/> 詳細については、「 [インシデント」](view-incidents-queue.md)を参照してください。 |
| **インシデント&アラート** > **アラート** | アラートの一覧 ( **アラート** キューとも呼ばれます) に移動 **します**。 アラートは、疑わしい、または悪意のあるファイル、プロセス、または動作が検出されたときにトリガーされます。 既定では、 **アラート** の一覧には過去 30 日間のデータが表示され、最新のアラートが最初に一覧表示されます。 <br/><br/> 詳細については、「 [アラート](alerts-queue.md)」を参照してください。 |
| **アクション センター** | 修復アクションと手動応答アクションを追跡するアクション センターに移動します。 アクション センターでは、次のようなアクティビティが追跡されます。 <br/>- Microsoft Defender ウイルス対策悪意のあるファイルが検出され、そのファイルをブロックまたは削除します。 <br/>- セキュリティ チームがデバイスを分離します。<br/>- Defender for Endpoint は、ファイルを検出して検疫します。 <br/><br/> 詳細については、「 [アクション センター」を](auto-investigation-action-center.md)参照してください。 |
| **セキュア スコア** | 組織のセキュリティ体制の表現と、改善アクションとメトリックの一覧を表示します。 <br/><br/> 詳細については、「 [Microsoft Secure Score](../defender/microsoft-secure-score.md)」を参照してください。 |
| **ラーニング ハブ** | アクセスできるラーニング パスの一覧に移動し、Microsoft 365セキュリティ機能の詳細を確認します。  |
| **エンドポイント** > **検索** | 特定のデバイスをデバイス名で検索できるページに移動します。 結果の一覧では、リスク レベルや正常性状態などの詳細を一目で確認できます。 |
|  **エンドポイント** > **デバイス インベントリ** | Defender for Endpoint にオンボードされているデバイスの一覧に移動します。 露出レベルやリスク レベルなど、デバイスに関する情報を提供します。 <br/><br/> 詳細については、「 [デバイス インベントリ](machines-view-overview.md)」を参照してください。 |
|  **エンドポイント** > **構成&ベースライン** | 展開して **、セキュリティ ベースライン** と **構成管理** を表示します。 |
|  **エンドポイント** > **構成&ベースライン** > **セキュリティ ベースライン** | セキュリティ ベースラインは、推奨されるセキュリティ設定を効率的かつ効果的に適用するのに役立つ、事前に構成されたポリシーと設定のグループです。 ベースラインには、業界のベスト プラクティスに基づく設定が含まれます。 既定の設定をそのまま使用することも、組織のニーズに合わせてベースラインをカスタマイズすることもできます。 <br/><br/> 詳細については、「[セキュリティ ベースラインを使用してIntuneでWindows 10デバイスを構成する](/mem/intune/protect/security-baselines)」を参照してください。 |
|  **エンドポイント** > **構成&ベースライン** > **構成管理** | **[デバイス構成管理**] ページに移動し、オンボードされたデバイスに関する情報を表示し、より多くのデバイスをオンボードする手順を実行できます。 |
| **レポート** | [脅威対策レポート](threat-protection-reports.md)、[デバイスの正常性とコンプライアンス](machine-reports.md) レポート、[Web](web-protection-overview.md) 保護レポートなど、レポートに移動します。 |
| **正常性** | **サービス正常性** と **メッセージ センター** へのリンクが含まれます。  |
| **健康** > **サービス正常性** | Microsoft 365 管理センターの [サービス正常性] ページに移動します。 このページでは、組織のサブスクリプションで利用可能なすべてのサービスの正常性状態を表示できます。   |
| **健康** > **メッセージ センター** | Microsoft 365 管理センターのメッセージ センターに移動します。 メッセージ センターでは、計画的な変更に関する情報を提供します。 各メッセージには、今後の予定、ユーザーへの影響、変更の管理方法が説明されています。 |  
| **ロール&アクセス許可** | Microsoft 365 Defender ポータルを使用するためのアクセス許可を付与できます。 アクセス許可は、Azure Active Directory (Azure AD) のロールを通じて付与されます。 ロールを選択すると、ポップアップ ウィンドウが表示されます。 ポップアップには、ロール グループ内のメンバーを追加または削除できるAzure ADへのリンクが含まれています。 <br/><br/> 詳細については、「 [ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。  |
| **設定** | Microsoft 365 Defender ポータルの全般設定 (**セキュリティ センター** として一覧表示) と Defender for Endpoint (エンドポイントとして一覧表示) **に** 移動します。 <br/><br/> 詳細については、「[設定](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)」を参照してください。 |
| **その他のリソース** | Azure Active Directoryや Microsoft Purview コンプライアンス ポータルなど、その他のポータルとセンターの一覧を表示します。 <br/><br/> 詳細については、 [Microsoft セキュリティ ポータルと管理センターに関するページを](../defender/portals.md)参照してください。 |

> [!TIP]
> 詳細については、[Microsoft 365 Defender ポータルの概要](../defender/microsoft-365-security-center-mde.md)を参照してください。

## <a name="view-and-manage-incidents--alerts"></a>アラート&インシデントを表示および管理する

Microsoft 365 Defender ポータルにサインインするときは、インシデントとアラートを必ず表示して管理してください。 **インシデント** の一覧から開始します。 次の図は、重大度が高いもの、重大度が中程度のインシデントを含むインシデントの一覧を示しています。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="インシデントの一覧":::

インシデントを選択すると、インシデントに関する詳細が表示されます。 詳細には、トリガーされたアラート、影響を受けたデバイスとユーザーの数、その他の詳細が含まれます。 次の図は、インシデントの詳細の例を示しています。

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="インシデントの詳細" lightbox="../../media/mde-p1/single-incident.png":::

**[アラート]**、[**デバイス]**、[**ユーザー]** タブを使用して、トリガーされたアラート、影響を受けたデバイス、影響を受けたユーザー アカウントなどの詳細情報を表示します。 そこから、デバイスの分離、ファイルの停止や隔離などの手動応答アクションを実行できます。

> [!TIP]
> **インシデント** ビューの使用の詳細については、「インシデントの [管理](manage-incidents.md)」を参照してください。

## <a name="manage-devices"></a>デバイスを管理する

組織のデバイスを表示および管理するには、ナビゲーション バーの [ **エンドポイント**] で [ **デバイス インベントリ**] を選択します。 次の図に示すように、デバイスの一覧が表示されます。

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="デバイス一覧" lightbox="../../media/mde-p1/device-inventory.png":::

一覧には、アラートが生成されたデバイスが含まれます。 既定では、表示されるデータは過去 30 日間で、最新のアイテムが最初に一覧表示されます。 デバイスを選択すると、デバイスの詳細が表示されます。 次の図に示すように、ポップアップ ウィンドウが開きます。

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="選択したデバイスの詳細" lightbox="../../media/mde-p1/device-inventory-selecteddevice.png":::

ポップアップ ウィンドウには、デバイスのアクティブなアラートなどの詳細が表示され、デバイスの分離などのアクションを実行するためのリンクが含まれます。

デバイスにアクティブなアラートがある場合は、ポップアップ ウィンドウにアラートを表示できます。 個々のアラートを選択すると、アラートの詳細が表示されます。 または、 **デバイスの分離** などのアクションを実行して、デバイスをさらに調査しながら、他のデバイスに感染するリスクを最小限に抑えることができます。

> [!TIP]
> 詳細については、「 [Defender for Endpoint デバイスの一覧でデバイスを調査する」を参照してください](investigate-machines.md)。

## <a name="view-reports"></a>レポートの表示

Defender for Endpoint プラン 1 では、Microsoft 365 Defender ポータルで複数のレポートを使用できます。 レポートにアクセスするには、次の手順に従います。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション バーで、[レポート] を選択 **します**。

3. 一覧からレポートを選択します。 次の 3 つのレポートが表示されます。

   - 脅威に対する保護のレポート
   - デバイス正常性レポート
   - Web 保護レポート

> [!TIP]
> 詳細については、「 [脅威保護レポート」を](threat-protection-reports.md)参照してください。

### <a name="threat-protection-report"></a>脅威に対する保護のレポート

脅威の防止レポートにアクセスするには、Microsoft 365 Defender ポータルで **[レポート**] を選択し、[**脅威の保護**] を選択します。 Threat Protection レポートには、アラートの傾向、状態、カテゴリなどが表示されます。 ビューは、次の図に示すように、 **アラートの傾向** と **アラートの状態** という 2 つの列に配置されます。

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="脅威に対する保護のレポート" lightbox="../../media/mde-p1/threat-protection-report.png":::

下にスクロールすると、各一覧のすべてのビューが表示されます。

- 既定では、[ **アラートの傾向** ] 列のビューには過去 30 日間のデータが表示されますが、過去 3 か月間、過去 6 か月間、またはカスタム時間範囲 (最大 180 日間) のデータを表示するようにビューを設定できます。
- **[アラートの状態**] 列のビューは、前の営業日のスナップショットです。

> [!TIP]
> 詳細については、 [Defender for Endpoint の脅威保護レポートに関するページを参照してください](threat-protection-reports.md)。

### <a name="device-health-report"></a>デバイス正常性レポート

デバイス正常性レポートにアクセスするには、Microsoft 365 Defender ポータルで **[レポート**] を選択し、[**デバイスの正常性**] を選択します。 デバイス正常性レポートには、組織内のデバイス間の正常性状態とウイルス対策が表示されます。 [脅威保護レポート](#threat-protection-report)と同様に、次の図に示すように、ビューは **デバイスの傾向** と **デバイスの概要** という 2 つの列に配置されます。

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="デバイス正常性レポート" lightbox="../../media/mde-p1/device-health-report.png":::

下にスクロールすると、各一覧のすべてのビューが表示されます。 既定では、[ **デバイスの傾向** ] 列のビューには過去 30 日間のデータが表示されますが、ビューを変更して、過去 3 か月間、過去 6 か月間、またはカスタム時間範囲 (最大 180 日間) のデータを表示できます。 **デバイスの概要** ビューは、前の営業日のスナップショットです。

> [!TIP]
> 詳細については、「デバイスの [正常性](machine-reports.md)」を参照してください。

### <a name="web-protection-report"></a>Web 保護レポート

デバイス正常性レポートにアクセスするには、Microsoft 365 Defender ポータルで [**レポート**] を選択し、[**Web 保護**] を選択します。 Web 保護レポートには、次の図に示すように、悪意のある URL やブロックされた URL へのアクセス試行など、時間の経過と共に検出が表示されます。

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Web 保護レポート" lightbox="../../media/mde-p1/web-protection-report.png":::

下にスクロールして、Web 保護レポートのすべてのビューを表示します。 一部のビューには、詳細を表示したり、脅威保護機能を構成したり、Defender for Endpoint の例外として機能するインジケーターを管理したりするためのリンクが含まれます。

> [!TIP]
> 詳細については、「 [Web 保護](web-protection-overview.md)」を参照してください。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpointプラン 1 の管理](mde-p1-maintenance-operations.md)
- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)
