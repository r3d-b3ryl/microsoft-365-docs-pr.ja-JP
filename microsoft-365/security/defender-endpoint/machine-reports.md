---
title: Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート
description: デバイスの正常性とコンプライアンス レポートを使用して、デバイスの正常性状態の検出、ウイルス対策の状態、OS プラットフォーム、Windows 10バージョンを追跡する
keywords: 正常性状態、ウイルス対策、OS プラットフォーム、Windows 10 バージョン、バージョン、正常性、コンプライアンス、状態
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
ms.technology: mde
ms.openlocfilehash: bf89c0e57cbe14980b15ecf6f5a88f6db2b83e84
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474027"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスの状態レポートは、組織内のデバイスに関する高レベルの情報を提供します。 このレポートには、センサーの正常性状態、ウイルス対策の状態、OS プラットフォーム、Windows 10 (および 11 のWindowsが含まれます。

ダッシュボードは、次の 2 つのセクションに構成されます。

:::image type="content" source="images/device-reports.png" alt-text="デバイス レポート" lightbox="images/device-reports.png":::


<br>

****

|Section|説明|
|---|---|
|1|デバイスの傾向|
|2|デバイスの概要 (現在の日)|
|||

## <a name="device-trends"></a>デバイスの傾向

既定では、デバイスの傾向は、最新の 1 日で終了する 30 日間の期間のデバイス情報を表示します。 組織で発生している傾向についてより良い視点を得るために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、ドロップダウン オプションから時間範囲を選択します。

- 30 日間
- 3か月
- 6 か月
- Custom

> [!NOTE]
> これらのフィルターは、[デバイスの傾向] セクションにのみ適用されます。 [デバイスの概要] セクションには影響を及ぼします。

## <a name="device-summary"></a>デバイスの概要

デバイスの傾向にデバイス情報が表示される一方で、デバイスの概要には、現在の日を対象にしたデバイス情報が表示されます。

> [!NOTE]
> [概要] セクションに反映されるデータの範囲は、現在の日付の 180 日前です。 たとえば、今日の日付が 2019 年 3 月 27 日の場合、概要セクションのデータには、2018 年 9 月 28 日から 2019 年 3 月 27 日の数値が反映されます。
>
> [傾向] セクションに適用されるフィルターは、[概要] セクションには適用されません。

[デバイスの傾向] セクションでは、対応するフィルターが適用されたデバイス リストにドリルダウンできます。 たとえば、センサーの正常性状態カードの [非アクティブ] バーをクリックすると、センサーの状態が非アクティブなデバイスのみを表示する結果が表示されるデバイスの一覧が表示されます。

## <a name="device-attributes"></a>デバイス属性

レポートは、次のデバイス属性を表示するカードで構成されます。

- **正常性状態**: デバイス上のセンサーの状態に関する情報を表示し、アクティブなデバイス、通信障害、非アクティブ、またはセンサー データが見られないデバイスの集約ビューを提供します。
- **アクティブなデバイスのウイルス対策Windows 10:** デバイスの数とデバイスの状態をMicrosoft Defender ウイルス対策。
- **OS プラットフォーム:** 組織内に存在する OS プラットフォームの配布を示します。
- **Windows 10バージョン**: 組織のWindows 10デバイスとそのバージョンの配布を示します。

## <a name="filter-data"></a>データをフィルター処理する

指定されたフィルターを使用して、特定の属性を持つデバイスを含めるか除外します。

デバイス属性から適用する複数のフィルターを選択できます。

> [!NOTE]
> これらのフィルターは、 **レポート内のすべての** カードに適用されます。

たとえば、アクティブ センサーの正常性状態を持つWindows 10デバイスに関するデータを表示するには、次の方法を実行します。

1. [ **フィルター] >センサーの正常性状態が [アクティブ>します**。
2. 次に、[**OS プラットフォーム] > Windows 10**。
3. **[適用]** を選択します。

## <a name="related-topic"></a>関連トピック

- [脅威に対する保護のレポート](threat-protection-reports.md)
