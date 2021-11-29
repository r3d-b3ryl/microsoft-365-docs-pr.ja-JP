---
title: データストレージの場所を確認し、データ保持設定を更新する
description: Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する
keywords: データ、ストレージ、設定、保持、更新
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fb27a097f2f9dfd26e1b611c56be6d078ecadc52
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217449"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のデータストレージの場所を確認し、データ保持設定を更新する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-gensettings-abovefoldlink)

オンボーディング プロセス中に、ウィザードによって Defender for Endpoint のデータストレージと保持設定が表示されます。 

オンボーディングが完了すると、[データ保持設定] ページで選択内容を確認できます。

## <a name="verify-data-storage-location"></a>データストレージの場所を確認する
セットアップ フェーズ [中に](production-deployment.md)、データを保存する場所を選択したとします。 


[エンドポイント データの保持] **([** 全般] の下設定に移動して、データの場所 \>  \> を確認 **できます**。


## <a name="update-data-retention-settings"></a>データ保持設定の更新

データ保持設定を更新できます。 既定では、保持期間は 180 日です。 

1. ナビゲーション ウィンドウで、[エンドポイント データの保持]**設定**[全般] の下にある [ エンドポイント \>  \> **データ保持**] を **選択します**。

2. ドロップダウン リストからデータ保持期間を選択します。

    > [!NOTE]
    > その他の設定は編集できません。

3. [設定 **の保存] をクリックします**。

## <a name="related-topics"></a>関連トピック
- [データ保持設定の更新](data-retention-settings.md)
- [Defender for Endpoint でアラート通知を構成する](configure-email-notifications.md)
- [高度な機能を構成する](advanced-features.md)
