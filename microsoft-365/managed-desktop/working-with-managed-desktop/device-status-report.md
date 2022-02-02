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
ms.openlocfilehash: 14c83d007d2506e0e85c156f4d738f78f91fad75
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321029"
---
# <a name="device-status-report"></a>デバイスの状態レポート

このレポートは、登録済みのすべてのデバイスの状態を集計して、Microsoft Managed Desktop サービスの使用を示します。

過去 28 日間のアクティビティと、デバイスの更新を維持する機能に基づいて、デバイスを分類します。

できるだけ早くWindows更新するには、デバイスが次の条件を実行する必要があります。

- インターネットに接続する。
- 休止状態ではありません。
- 少なくとも 6 時間は一時停止されません。この 2 つが連続している必要があります。

ただし、これらの要件を満たしないデバイスが更新される可能性があります。 それらを満たすデバイスは、更新される可能性が最も高い。

:::image type="content" source="../../media/mmd-device-status.png" alt-text="左上にデバイスのアクティビティ状態のドーナツ グラフを表示するレポート、レポートを生成するボタンを使用して右上にフィルターを表示する、および下部に沿った詳細の表を表示する":::

## <a name="device-status-labels"></a>デバイスの状態ラベル

次のラベルを使用してデバイスの状態を報告します。

| デバイスの状態ラベル | 説明 |
| ------ | ------ |
| ユーザーの準備ができました | サービスに正常に登録され、ユーザーに提供する準備ができているデバイス。|
| Active | 使用されているデバイス。 <ul><li>最新のセキュリティ更新プログラムリリースのアクティビティ条件 (6 時間、連続 2 回) を満たしています。</li> <li>過去 5 日間に少なくとも 1 Microsoft Intuneにチェックインしました。</li></ul> |
| 同期済み | 過去 28 日以内に Intune でチェックインされているデバイス。
| 同期が取れな | 使用されているが、過去 28 日間に Intune にチェックインしていないデバイス。 |
| Other | ラベルは、通常、デバイスの登録中に発生する可能性があるいくつかのエラー状態を集計します。 詳細については、「デバイス登録の [トラブルシューティング」を参照してください](../get-started/register-devices-self.md#troubleshooting-device-registration)。 |
