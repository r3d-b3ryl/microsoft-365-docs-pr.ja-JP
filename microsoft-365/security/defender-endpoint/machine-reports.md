---
title: Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート
description: デバイスの正常性とコンプライアンス レポートを使用して、デバイスの正常性状態の検出、ウイルス対策状態、OS プラットフォーム、およびWindows 10バージョンを追跡する
keywords: 正常性状態, ウイルス対策, OS プラットフォーム, Windows 10 バージョン, バージョン, 正常性, コンプライアンス, 状態
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
ms.openlocfilehash: d171db0d5009cc32c34c3bf95da907221f275410
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789274"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策 

**プラットフォーム**
- Windows
- Mac OS
- Linux
- iOS
- Android

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスの状態レポートには、組織内のデバイスに関する高度な情報が表示されます。 このレポートには、センサーの正常性状態、ウイルス対策状態、OS プラットフォーム、およびWindows 10 (およびWindows 11) バージョンを示す傾向のある情報が含まれています。

ダッシュボードは、次の 2 つのセクションに構成されています。

:::image type="content" source="images/device-reports.png" alt-text="デバイス レポート" lightbox="images/device-reports.png":::


<br>

****

|Section|説明|
|---|---|
|1|デバイスの傾向|
|2|デバイスの概要 (現在の日)|
|||

## <a name="device-trends"></a>デバイスの傾向

既定では、デバイスの傾向には、最新の 1 日で終わる 30 日間のデバイス情報が表示されます。 組織で発生している傾向をより適切に把握するために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、ドロップダウン オプションから時間範囲を選択します。

- 30 日間
- 3か月
- 6 か月
- カスタム

> [!NOTE]
> これらのフィルターは、デバイスの傾向セクションにのみ適用されます。 デバイスの概要セクションには影響しません。

## <a name="device-summary"></a>デバイスの概要

デバイスの傾向はデバイス情報の傾向を示しますが、デバイスの概要には、現在の日付の範囲のデバイス情報が表示されます。

> [!NOTE]
> 概要セクションに反映されるデータの範囲は、現在の日付の 180 日前です。 たとえば、今日の日付が 2019 年 3 月 27 日の場合、概要セクションのデータには、2018 年 9 月 28 日から 2019 年 3 月 27 日までの数値が反映されます。
>
> [傾向] セクションに適用されたフィルターは、[概要] セクションには適用されません。

[デバイスの傾向] セクションでは、対応するフィルターを適用してデバイスの一覧にドリルダウンできます。 たとえば、センサー正常性状態カードの [非アクティブ] バーをクリックすると、センサーの状態が非アクティブなデバイスのみが表示される結果が表示されるデバイスの一覧が表示されます。

## <a name="device-attributes"></a>デバイス属性

レポートは、次のデバイス属性を表示するカードで構成されます。

- **正常性状態**: デバイス上のセンサーの状態に関する情報を表示し、アクティブなデバイス、通信の障害が発生しているデバイス、非アクティブなデバイス、またはセンサー データが見つからないデバイスの集計ビューを提供します。
- **アクティブなWindows 10 デバイスのウイルス対策の状態: デバイス** の数とMicrosoft Defender ウイルス対策の状態を示します。
- **OS プラットフォーム**: 組織内に存在する OS プラットフォームの分布を示します。
- **Windows 10 バージョン**: 組織内のWindows 10 デバイスとそのバージョンの分布を示します。

## <a name="filter-data"></a>データをフィルター処理する

特定の属性を持つデバイスを含めたり除外したりするには、指定されたフィルターを使用します。

デバイス属性から適用するフィルターを複数選択できます。

> [!NOTE]
> これらのフィルターは、レポート **内のすべての** カードに適用されます。

たとえば、アクティブなセンサーの正常性状態を持つデバイスWindows 10に関するデータを表示するには、次のようにします。

1. [ **フィルター] > [センサーの正常性状態] > [アクティブ] です**。
2. 次に、**OS プラットフォーム > Windows 10** を選択します。
3. **[適用]** を選択します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-topic"></a>関連トピック

- [脅威に対する保護のレポート](threat-protection-reports.md)
