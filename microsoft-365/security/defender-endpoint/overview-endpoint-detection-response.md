---
title: エンドポイントの検出および応答機能の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint のエンドポイント検出および応答機能について説明します。
keywords: エンドポイントの Microsoft Defender、エンドポイントの検出と応答、応答、検出、サイバーセキュリティ、保護
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
ms.openlocfilehash: 23f093ba5f93bd8763ae27526dbeb77a16f3c5cd
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655925"
---
# <a name="overview-of-endpoint-detection-and-response"></a>エンドポイントでの検出と対応の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint endpoint detection and response capabilitis provide advanced attack detections are near real-time and actionable. セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。

脅威が検出されると、システムでアラートが生成され、アナリストが調査します。 同じ攻撃技法のアラートや同じ攻撃者によるアラートは、_incident_ と呼ばれるエンティティに集約されます。 この方法でアラートを集約すると、アナリストは脅威への総合的な調査や対応が簡単にできるようになります。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4o1j5]

「侵害を想定する」という考え方にインスパイアされた Defender for Endpoint は、継続的に行動サイバー テレメトリを収集します。 これには、プロセス情報、ネットワーク活動、カーネルおよびメモリ マネージャーの詳細分析、ユーザー ログイン活動、レジストリとファイル システムの変更内容などが含まれます。 この情報は 6 か月間保存されるため、アナリストは攻撃の開始時点まで時間を遡ることができます。 そのアナリストは各種ビューをピボットして、複数のベクトルから調査に取り組むことができます。

対応機能により、影響を受けているエンティティに対策を講じることで、すばやく脅威に対処できるようになります。

## <a name="related-topics"></a>関連項目

- [セキュリティ運用ダッシュボード](security-operations-dashboard.md)
- [インシデント キュー](view-incidents-queue.md)
- [アラート キュー](alerts-queue.md)
- [デバイスの一覧](machines-view-overview.md)
