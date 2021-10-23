---
title: Microsoft Defender for Endpoint のセンサーの正常性状態を確認する
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
ms.openlocfilehash: e980cc5dd2f164acf8c63aab5511423d5a38d46b
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60554998"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のセンサーの正常性状態を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

[ **センサーの問題があるデバイス] タイル** は、[セキュリティ操作] ダッシュボードに表示されます。 このタイルは、センサー データを提供し、Defender for Endpoint サービスと通信する個々のデバイスの機能に関する情報を提供します。 注意が必要なデバイスの数が報告され、問題のあるデバイスを特定し、既知の問題を修正するためのアクションを取るのに役立ちます。

タイルには、サービスに適切に報告されていないデバイスの数に関する情報を提供する 2 つの状態インジケーターがあります。

- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性があります。また、修正が必要な構成エラーが発生している可能性があります。
- **非** アクティブ - 過去 1 か月で 7 日間以上 Defender for Endpoint サービスへの報告を停止したデバイス。

グループをクリックすると、[デバイス] リストが表示 **され、選択** に従ってフィルター処理されます。

![センサーの問題があるデバイスタイルのスクリーンショット。](images/atp-devices-with-sensor-issues-tile.png)

[ **デバイス] リスト** で、正常性状態リストを次の状態でフィルター処理できます。

- **Active** - Defender for Endpoint サービスに対してアクティブにレポートしているデバイス。
- **正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性がありますが、修正する必要がある構成エラーがあります。 間違って構成されたデバイスには、次のような問題のいずれかまたは組み合わせがあります。
  - **センサー データなし** - デバイスがセンサー データの送信を停止しました。 制限のあるアラートをデバイスでトリガーすることができます。
  - **通信障害** - デバイスと通信する機能が損なわれる。 詳細分析のためのファイルの送信、ファイルのブロック、ネットワークからのデバイスの分離など、デバイスとの通信を必要とするアクションが機能しない場合があります。
- **非** アクティブ - Defender for Endpoint サービスへのレポートを停止したデバイス。

エクスポート機能を使用して、リスト全体を CSV 形式で **ダウンロード** できます。 フィルターの詳細については、「デバイスリストの [表示と整理」を参照してください](machines-view-overview.md)。

> [!NOTE]
> リストを CSV 形式でエクスポートして、フィルター処理されていないデータを表示します。 CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。

![[デバイス] リスト ページのスクリーンショット。](images/atp-devices-list-page.png)

構成が正しく設定されていないデバイスまたは非アクティブなデバイスをクリックすると、デバイスの詳細を表示できます。

## <a name="see-also"></a>関連項目

- [Defender for Endpoint で不健康なセンサーを修正する](fix-unhealthy-sensors.md)
- [クライアント アナライザーの概要](overview-client-analyzer.md)
- [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
- [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
- [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
- [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
