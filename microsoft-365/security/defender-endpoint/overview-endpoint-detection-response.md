---
title: エンドポイントでの検出と対応機能の概要
ms.reviewer: ''
description: Microsoft Defender for Endpointのエンドポイントでの検出と対応機能について説明します
keywords: Microsoft Defender for Endpoint、エンドポイントでの検出と対応、応答、検出、サイバーセキュリティ、保護
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
ms.openlocfilehash: cf09e20b0f11713152070b12c30efc4820d6678c
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167756"
---
# <a name="overview-of-endpoint-detection-and-response"></a>エンドポイントでの検出と対応の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint エンドポイントでの検出と対応機能は、ほぼリアルタイムで実行可能な高度な攻撃検出を提供します。 セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。

脅威が検出されると、システムでアラートが生成され、アナリストが調査します。 同じ攻撃技法のアラートや同じ攻撃者によるアラートは、_incident_ と呼ばれるエンティティに集約されます。 この方法でアラートを集約すると、アナリストは脅威への総合的な調査や対応が簡単にできるようになります。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4o1j5]

"侵害を想定する" 考え方に着想を得て、Defender for Endpoint は行動サイバー テレメトリを継続的に収集します。 これには、プロセス情報、ネットワーク活動、カーネルおよびメモリ マネージャーの詳細分析、ユーザー ログイン活動、レジストリとファイル システムの変更内容などが含まれます。 この情報は 6 か月間保存されるため、アナリストは攻撃の開始時点まで時間を遡ることができます。 そのアナリストは各種ビューをピボットして、複数のベクトルから調査に取り組むことができます。

対応機能により、影響を受けているエンティティに対策を講じることで、すばやく脅威に対処できるようになります。

## <a name="related-topics"></a>関連項目

- [セキュリティ運用ダッシュボード](security-operations-dashboard.md)
- [インシデント キュー](view-incidents-queue.md)
- [アラート キュー](alerts-queue.md)
- [デバイスの一覧](machines-view-overview.md)
