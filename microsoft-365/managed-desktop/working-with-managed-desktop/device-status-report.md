---
title: デバイスの状態レポート
description: デバイスの状態について説明します
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 4071d3a76430dd34776b2d4df3eae2b32e350a11
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034847"
---
# <a name="device-status-report"></a>デバイスの状態レポート

このレポートは、登録済みのすべてのデバイスの状態を集計して、Microsoft Managed Desktop サービスの使用を示します。 過去 28 日間のアクティビティと、デバイスの更新を維持する機能に基づいて、デバイスを分類します。 Windows Update でできるだけ早く更新するには、デバイスをインターネットに接続し、休止や休止を少なくとも 6 時間行う必要はありません。そのうちの 2 つが連続している必要があります。 これらの要件を満たしないデバイスが更新される可能性はあり得るが、それらの要件を満たすデバイスは更新される可能性が最も高い。

:::image type="content" source="../../media/mmd-device-status.png" alt-text="左上にデバイスのアクティビティ状態のドーナツ グラフを表示するレポート、レポートを生成するボタンを使用して右上にフィルターを表示する、および下部に沿った詳細の表を表示する":::

次のラベルを使用してデバイスの状態を報告します。 

- **ユーザーの準備**: サービスに正常に登録され、ユーザーに提供する準備ができているデバイス 
- **Active**: 最新のセキュリティ更新プログラム リリースのアクティビティ条件 (6 時間、連続 2 回) を満たしたデバイスで、過去 5 日間に少なくとも 1 回は Microsoft Intune にチェックインしています。 
- **同期済** み : 過去 28 日以内に Intune でチェックインされているデバイス 
- **同期外**: 過去 28 日間に Intune でチェックインされていないデバイス 
- **その** 他 : カテゴリは、通常、デバイスの登録中に発生する可能性があるいくつかのエラー状態を集計します。 詳細については、「デバイス登録の [トラブルシューティング」を参照してください](../get-started/register-devices-self.md#troubleshooting-device-registration)。