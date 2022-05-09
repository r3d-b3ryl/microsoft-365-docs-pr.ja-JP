---
title: Microsoft Defender for Endpointでセンサーの正常性状態を確認する
description: デバイスのセンサーの正常性を確認して、構成が誤っているか、非アクティブであるか、またはセンサー データが報告されていないかを特定します。
keywords: センサー, センサーの正常性, 不適切な構成, 非アクティブ, センサー データなし, センサー データ, 通信障害, 通信
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
# <a name="check-sensor-health-state-at-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでセンサーの正常性状態を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

**[センサーの問題があるデバイス]** タイルは、[セキュリティ操作] ダッシュボードにあります。 このタイルは、センサー データを提供し、Defender for Endpoint サービスと通信する個々のデバイスの機能に関する情報を提供します。 注意が必要なデバイスの数が報告され、問題のあるデバイスを特定し、既知の問題を修正するためのアクションを取るのに役立ちます。

タイルには、サービスに正しく報告されていないデバイスの数に関する情報を提供する状態インジケーターが 2 つあります。

- **正しく構成されていない** - これらのデバイスは、部分的に Defender for Endpoint サービスにセンサー データを報告している可能性があり、修正する必要がある構成エラーが発生する可能性があります。
- **非アクティブ** - 過去 1 か月に 7 日間以上 Defender for Endpoint サービスへのレポートを停止したデバイス。

任意のグループをクリックすると、[ **デバイス] の一覧** が表示され、選択した内容に従ってフィルター処理されます。

:::image type="content" source="images/atp-devices-with-sensor-issues-tile.png" alt-text="[センサーの問題があるデバイス] タイル" lightbox="images/atp-devices-with-sensor-issues-tile.png":::

**[デバイス] の一覧** では、次の状態で正常性状態の一覧をフィルター処理できます。

- **アクティブ** - Defender for Endpoint サービスにアクティブに報告しているデバイス。
- **正しく構成されていない** - これらのデバイスは、部分的に Defender for Endpoint サービスにセンサー データを報告している可能性がありますが、修正する必要がある構成エラーがあります。 間違って構成されたデバイスには、次のような問題のいずれかまたは組み合わせがあります。
  - **センサー データなし** - デバイスがセンサー データの送信を停止しました。 制限のあるアラートをデバイスでトリガーすることができます。
  - **通信の障害** - デバイスと通信する機能が損なわれます。 詳細分析のためのファイルの送信、ファイルのブロック、ネットワークからのデバイスの分離など、デバイスとの通信を必要とするアクションが機能しない場合があります。
- **非アクティブ** - Defender for Endpoint サービスへのレポートを停止したデバイス。

**エクスポート** 機能を使用して、リスト全体を CSV 形式でダウンロードすることもできます。 フィルターの詳細については、「 [デバイスの一覧を表示して整理する」を参照してください](machines-view-overview.md)。

> [!NOTE]
> リストを CSV 形式でエクスポートして、フィルター処理されていないデータを表示します。 CSV ファイルには、ビュー自体に適用されるフィルターに関係なく、組織内のすべてのデバイスが含まれ、組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。

:::image type="content" source="images/atp-devices-list-page.png" alt-text="[デバイス] リスト ページの [エクスポート] タブ" lightbox="images/atp-devices-list-page.png":::

正しく構成されていないデバイスまたは非アクティブなデバイスをクリックすると、デバイスの詳細を表示できます。

## <a name="see-also"></a>関連項目

- [Defender for Endpoint の異常なセンサーを修正する](fix-unhealthy-sensors.md)
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
- [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
