---
title: データストレージの場所を確認し、データ保持設定を更新する
description: Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する
keywords: データ、ストレージ、設定、保持、更新
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b83e6682ce0c11d076e0bbef60fdef365c9be564
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471103"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

オンボーディング プロセス中に、ウィザードによって Defender for Endpoint のデータストレージと保持設定が表示されます。 

オンボーディングが完了すると、[データ保持設定] ページで選択内容を確認できます。

## <a name="verify-data-storage-location"></a>データストレージの場所を確認する
セットアップ フェーズ [中に](production-deployment.md)、データを保存する場所を選択したとします。 

[設定データの保持] に移動すると、データの **場所**  >  **を確認できます**。

## <a name="update-data-retention-settings"></a>データ保持設定の更新

データ保持設定を更新できます。 既定では、保持期間は 180 日です。 

1. ナビゲーション ウィンドウで、[設定データ保持 **]**  >  **を選択します**。

2. ドロップダウン リストからデータ保持期間を選択します。

    > [!NOTE]
    > その他の設定は編集できません。

3. [設定 **の保存] をクリックします**。


## <a name="related-topics"></a>関連項目
- [データ保持設定の更新](data-retention-settings.md)
- [Defender for Endpoint でアラート通知を構成する](configure-email-notifications.md)
- [高度な機能を構成する](advanced-features.md)
