---
title: Microsoft Defender for Endpoint のセンサーの正常性状態を確認する
description: デバイスのセンサーの正常性を確認して、構成が誤り、非アクティブ、またはセンサー データを報告していないデバイスを特定します。
keywords: センサー、センサーの正常性、構成ミス、非アクティブ、センサー データなし、センサー データ、通信障害、通信障害
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904166"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のセンサーの正常性状態を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

[ **センサーの問題があるデバイス] タイル** は、[セキュリティ操作] ダッシュボードに表示されます。 このタイルは、センサー データを提供し、Defender for Endpoint サービスと通信する個々のデバイスの機能に関する情報を提供します。 注意が必要なデバイスの数を報告し、問題のあるデバイスを特定し、既知の問題を修正するためのアクションを実行するのに役立ちます。

タイルには、サービスに適切に報告されていないデバイスの数に関する情報を提供する 2 つの状態インジケーターがあります。
- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性があります。また、修正が必要な構成エラーが発生している可能性があります。
- **非** アクティブ - 過去 1 か月で 7 日間以上 Defender for Endpoint サービスへの報告を停止したデバイス。

グループをクリックすると、[デバイス] リストが表示 **され、選択** に従ってフィルター処理されます。

![センサーの問題があるデバイスタイルのスクリーンショット](images/atp-devices-with-sensor-issues-tile.png)

[ **デバイス] リスト** で、正常性状態リストを次の状態でフィルター処理できます。
- **Active** - Defender for Endpoint サービスに対してアクティブにレポートしているデバイス。
- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性がありますが、修正する必要がある構成エラーがあります。 構成が正しく設定されていないデバイスには、次の問題の 1 つまたは組み合わせが含まれます。
  - **センサー データなし** - デバイスがセンサー データの送信を停止しました。 制限付きアラートは、デバイスからトリガーできます。
  - **通信障害** - デバイスと通信する機能が損なわれる。 ディープ分析用のファイルの送信、ファイルのブロック、ネットワークからのデバイスの分離、デバイスとの通信が必要なその他のアクションが機能しない場合があります。
- **非** アクティブ - Defender for Endpoint サービスへのレポートを停止したデバイス。

エクスポート機能を使用して、リスト全体を CSV 形式で **ダウンロード** できます。 フィルターの詳細については、「デバイスリストの [表示と整理」を参照してください](machines-view-overview.md)。

>[!NOTE]
>リストを CSV 形式でエクスポートして、フィルター処理されていないデータを表示します。 CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。

![[デバイス] リスト ページのスクリーンショット](images/atp-devices-list-page.png)

構成が正しく設定されていないデバイスまたは非アクティブなデバイスをクリックすると、デバイスの詳細を表示できます。

## <a name="related-topic"></a>関連トピック
- [Defender for Endpoint で不健康なセンサーを修正する](fix-unhealthy-sensors.md)
