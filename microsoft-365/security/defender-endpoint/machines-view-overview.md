---
title: Microsoft Defender for Endpoint デバイスリストの表示と整理
description: リストの並べ替え、フィルター処理、エクスポートなど、[デバイス] リストから使用できる機能について学習し、調査を強化します。
keywords: 並べ替え、フィルター、エクスポート、csv、デバイス名、ドメイン、最後に見た、内部 IP、正常性状態、アクティブなアラート、アクティブなマルウェア検出、脅威カテゴリ、確認アラート、ネットワーク、接続、マルウェア、種類、パスワード盗み、ランサムウェア、悪用、脅威、一般的なマルウェア、望ましくないソフトウェア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87d9d768a81d8e6ddd72753fe7372f18c13254e1
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542953"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Microsoft Defender for Endpoint Devices リストの表示と整理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


[ **デバイス] リストには** 、アラートが生成されたネットワーク内のデバイスの一覧が表示されます。 既定では、キューには過去 30 日間に表示されたデバイスが表示されます。  

ドメイン、リスク レベル、OS プラットフォームなどの情報を一目で確認すると、最も危険にさらされているデバイスを簡単に識別できます。

デバイス リスト ビューをカスタマイズするために選択できるオプションは複数あります。 上部のナビゲーションでは、次の操作を実行できます。

- 列の追加または削除
- リスト全体を CSV 形式でエクスポートする
- ページごとに表示するアイテムの数を選択する
- フィルターの適用

オンボーディング プロセス中に、[ **デバイス** ] リストには、センサー データの報告を開始するデバイスが徐々に追加されます。 このビューを使用して、オンボードエンドポイントをオンラインで追跡したり、オフライン分析用の CSV ファイルとして完全なエンドポイント リストをダウンロードしたりします。

>[!NOTE]
> デバイスリストをエクスポートすると、組織内のすべてのデバイスが含まれる。 組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。 リストを CSV 形式でエクスポートすると、フィルター処理されていない方法でデータが表示されます。 CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。

![デバイスのリストを含むデバイスリストのイメージ](images/device-inventory.png)

## <a name="sort-and-filter-the-device-list"></a>デバイスリストの並べ替えとフィルター処理

次のフィルターを適用して、アラートの一覧を制限し、より集中したビューを取得できます。

### <a name="risk-level"></a>リスク レベル

リスク レベルは、デバイス上のアクティブなアラートの種類と重大度などの要因の組み合わせに基づいて、デバイスの全体的なリスク評価を反映します。 アクティブなアラートを解決し、修復アクティビティを承認し、後続のアラートを抑制すると、リスク レベルが低下する可能性があります。

### <a name="exposure-level"></a>露出レベル

露出レベルは、保留中のセキュリティ推奨事項の累積的な影響に基づいて、デバイスの現在の露出を反映します。 可能なレベルは、低、中、高です。 露出が低いということは、デバイスが悪用の影響を受けやすいという意味です。

露出レベルに 「データが使用できない」と表示される場合は、次の理由が考えられません。

- デバイスが 30 日以上レポートを停止しました 。その場合は非アクティブと見なされ、露出は計算されません
- デバイス OS はサポートされていません - Microsoft Defender for Endpoint の最小 [要件を参照してください。](minimum-requirements.md)
- 古いエージェントを持つデバイス (非常に可能性が低い)

### <a name="os-platform"></a>OS プラットフォーム

調査する OS プラットフォームのみを選択します。

### <a name="health-state"></a>正常性の状態

次のデバイスの正常性状態でフィルター処理します。

- **Active** – センサー データをサービスにアクティブに報告しているデバイス。
- **非** アクティブ – 7 日間以上信号の送信を完全に停止したデバイス。
- **正しく構成されていない** – サービスとの通信に障害が生じ、センサー データを送信できないデバイス。 構成が正しく設定されていないデバイスは、さらに次のように分類できます。
  - センサー データなし
  - 通信障害

  構成が正しく設定されていないデバイスの問題に対処する方法の詳細については、「異常なセンサーを修正する」 [を参照してください](fix-unhealthy-sensors.md)。

### <a name="antivirus-status"></a>ウイルス対策の状態

ウイルス対策の状態でデバイスをフィルター処理します。 アクティブなデバイスにのみWindows 10適用されます。

- **無効** - ウイルス&保護がオフになっています。
- **[報告しない** ] - ウイルス&保護が報告されていない場合。
- **[更新されません** ] - ウイルス&保護が最新ではない場合。

詳細については、「脅威と [脆弱性管理ダッシュボード&を参照してください](tvm-dashboard-insights.md)。

### <a name="threat-mitigation-status"></a>脅威の軽減の状態

特定の脅威の影響を受ける可能性のあるデバイスを表示するには、ドロップダウン メニューから脅威を選択し、軽減する必要がある脆弱性の側面を選択します。

特定の脅威の詳細については、「Threat [analytics」を参照してください](threat-analytics.md)。 軽減策の詳細については [、「Threat &脆弱性管理」を参照してください](next-gen-threat-and-vuln-mgt.md)。

### <a name="windows-10-version"></a>Windows 10 バージョン

調査するWindows 10バージョンのみを選択します。

### <a name="tags--groups"></a>タグ & グループ

個々のデバイスに追加したグループ化とタグ付けに基づいてリストをフィルター処理します。 「デバイス [タグの作成と管理」および「](machine-tags.md) デバイス [グループの作成と管理」を参照してください](machine-groups.md)。

## <a name="related-topics"></a>関連トピック

- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
