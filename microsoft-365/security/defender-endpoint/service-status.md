---
title: Microsoft Defender for Endpoint サービスの正常性を確認する
description: Microsoft Defender for Endpoint Service の正常性を確認し、サービスに問題が発生していないかを確認し、解決された以前の問題を確認します。
keywords: ダッシュボード、サービス、問題、サービス正常性、現在の状態、状態履歴、影響の概要、予備的な根本原因、解決時間、解決時間、予想される解決時間
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
ms.technology: mde
ms.openlocfilehash: c38cacb253fa8a78a5dfd28cb98bcc753ab84af2bb8387b83b6de09617985cad
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53894097"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a>Microsoft Defender for Endpoint サービスの正常性を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-servicestatus-abovefoldlink)

**サービス正常性は** 、Defender for Endpoint サービスの現在の状態に関する情報を提供します。 サービスの正常性が正常か、現在の問題が発生した場合に確認できます。 問題がある場合は、問題が検出された時期、根本的な予備的な原因、予想される解決時間などの情報が表示されます。

また、解決された過去の問題に関する情報や、問題が解決された日時などの詳細も表示されます。 サービスに問題がない場合は、正常な状態が表示されます。

サービス正常性の詳細を表示するには、セキュリティ操作ダッシュボードからタイルをクリックするか、ナビゲーション ウィンドウから[サービス正常性] メニューを選択します。

[ **サービス正常性の詳細** ] ページには、次のタブがあります。

- **現在の状態**
- **状態履歴**

## <a name="current-status"></a>現在の状態

[ **現在の状態]** タブには、Defender for Endpoint サービスの現在の状態が表示されます。 サービスがスムーズに実行されている場合は、正常なサービスの正常性が表示されます。 問題が見られる場合は、問題に関するより良い洞察を得るために、次のサービスの詳細が表示されます。

- 問題が検出された日時
- 問題の簡単な説明
- 更新時間
- 影響の概要
- 予備的な根本原因
- 次の手順
- 予想される解決時間

問題の進行状況に関する更新プログラムは、問題が解決されるにつれてページに反映されます。 更新された推定解決時間や次の手順などの情報に関する更新プログラムが表示されます。

問題が解決すると、[状態の履歴] タブに **記録** されます。

## <a name="status-history"></a>状態履歴

[ **状態の履歴]** タブには、表示および解決されたすべての履歴問題が反映されます。 解決された問題の詳細と、解決中に含まれるその他の情報が表示されます。

### <a name="related-topic"></a>関連トピック

- [セキュリティ操作ダッシュボードの表示](security-operations-dashboard.md)
