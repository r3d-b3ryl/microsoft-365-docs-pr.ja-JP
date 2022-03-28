---
title: Microsoft Defender for Endpoint でセンサーの正常性状態を確認する
description: デバイスのセンサーの正常性を確認して、構成が誤っている、非アクティブである、またはセンサー データを報告していないデバイスを特定します。
keywords: センサー、センサーの正常性、構成ミス、非アクティブ、センサー データなし、センサー データ、通信障害、通信障害
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: bba5fde870b2916501f4154c6ff628a0d2e3ff1f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465474"
---
# <a name="check-sensor-health-state-at-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でセンサーの正常性状態を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

[ **センサーの問題があるデバイス] タイル** は、[セキュリティ操作] ダッシュボードに表示されます。 このタイルは、センサー データを提供し、Defender for Endpoint サービスと通信する個々のデバイスの機能に関する情報を提供します。 注意が必要なデバイスの数が報告され、問題のあるデバイスを特定し、既知の問題を修正するためのアクションを取るのに役立ちます。

タイルには、サービスに適切に報告されていないデバイスの数に関する情報を提供する 2 つの状態インジケーターがあります。

- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性があります。また、修正が必要な構成エラーが発生している可能性があります。
- **非** アクティブ - 過去 1 か月で 7 日間以上 Defender for Endpoint サービスへの報告を停止したデバイス。

グループをクリックすると、[デバイス] リストが表示され、選択に従ってフィルター処理されます。

:::image type="content" source="images/atp-devices-with-sensor-issues-tile.png" alt-text="センサーの問題のタイルを持つデバイス" lightbox="images/atp-devices-with-sensor-issues-tile.png":::

[ **デバイス] リスト** で、正常性状態リストを次の状態でフィルター処理できます。

- **Active** - Defender for Endpoint サービスに対してアクティブにレポートしているデバイス。
- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性がありますが、修正する必要がある構成エラーがあります。 間違って構成されたデバイスには、次のような問題のいずれかまたは組み合わせがあります。
  - **センサー データなし** - デバイスがセンサー データの送信を停止しました。 制限のあるアラートをデバイスでトリガーすることができます。
  - **通信障害** - デバイスと通信する機能が損なわれる。 詳細分析のためのファイルの送信、ファイルのブロック、ネットワークからのデバイスの分離など、デバイスとの通信を必要とするアクションが機能しない場合があります。
- **非** アクティブ - Defender for Endpoint サービスへのレポートを停止したデバイス。

エクスポート機能を使用して、リスト全体を CSV 形式で **ダウンロード** できます。 フィルターの詳細については、「デバイスリストの [表示と整理」を参照してください](machines-view-overview.md)。

> [!NOTE]
> リストを CSV 形式でエクスポートして、フィルター処理されていないデータを表示します。 CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。

:::image type="content" source="images/atp-devices-list-page.png" alt-text="[デバイス] リスト ページの [エクスポート] タブ" lightbox="images/atp-devices-list-page.png":::

構成が正しく設定されていないデバイスまたは非アクティブなデバイスをクリックすると、デバイスの詳細を表示できます。

## <a name="see-also"></a>関連項目

- [Defender for Endpoint で不健康なセンサーを修正する](fix-unhealthy-sensors.md)
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
- [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
