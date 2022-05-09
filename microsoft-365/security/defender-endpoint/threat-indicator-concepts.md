---
title: Microsoft Defender for Endpointの脅威インテリジェンスの概念を理解する
description: 組織のカスタム脅威アラートを作成し、脅威インテリジェンスに関する概念をMicrosoft Defender for Endpoint
keywords: 脅威インテリジェンス, アラート定義, 侵害の指標, ioc
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
ms.openlocfilehash: 440f788c4adb757013611bb05621b4eb4f4e9715
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302448"
---
# <a name="understand-threat-intelligence-concepts"></a>脅威インテリジェンスの概念を理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

高度なサイバーセキュリティ攻撃は、複数の複雑な悪意のあるイベント、属性、コンテキスト情報で構成されます。 これらのアクティビティのうち、疑わしいと見なされるアクティビティの特定と決定は、困難な作業になる可能性があります。 業界固有の既知の属性と異常なアクティビティに関する知識は、観察された動作を疑わしいと呼ぶタイミングを知る上で基本的なものです。

Microsoft 365 Defenderを使用すると、組織内で起こり得る攻撃アクティビティを追跡するのに役立つカスタム脅威アラートを作成できます。 疑わしいイベントにフラグを設定して手がかりをまとめ、攻撃チェーンを停止する可能性があります。 これらのカスタム脅威アラートは、組織にのみ表示され、追跡するように設定したイベントにフラグが設定されます。

カスタム脅威アラートを作成する前に、アラート定義の背後にある概念と侵害のインジケーター (IOC) とその間の関係を把握しておくことが重要です。

## <a name="alert-definitions"></a>アラート定義
アラート定義はコンテキスト属性であり、サイバーセキュリティ攻撃の可能性がある早期の手がかりを識別するためにまとめて使用できます。 通常、これらのインジケーターは、攻撃の目的を達成するために攻撃者が実行したアクティビティ、特性、およびアクションの組み合わせです。 これらの属性の組み合わせを監視することは、攻撃に対する有利なポイントを獲得し、攻撃者の目標に到達する前にイベントのチェーンに干渉する可能性がある場合に重要です。

## <a name="indicators-of-compromise-ioc"></a>侵害のインジケーター (IOC)
IOC は、ネットワークまたはデバイスが既に侵害されていることを示す個別に既知の悪意のあるイベントです。 アラート定義とは異なり、これらのインジケーターは侵害の証拠と見なされます。 攻撃が既に実行され、流出などの目的に達した後によく見られます。 また、フォレンジック調査では、IOC を追跡することも重要です。 攻撃チェーンに介入できない場合もありますが、これらのインジケーターを収集すると、将来の攻撃に対してより優れた防御を作成するのに役立ちます。

## <a name="relationship-between-alert-definitions-and-iocs"></a>アラート定義と IOC の関係
Microsoft 365 DefenderとMicrosoft Defender for Endpointのコンテキストでは、アラート定義は IOC のコンテナーであり、特定の IOC 一致に対して発生するメタデータを含むアラートを定義します。 アラート定義の一部として、さまざまなメタデータが提供されます。 攻撃のアラート定義名、重大度、説明などのメタデータは、他のオプションと共に提供されます。

各 IOC は、その型、値、およびアクションに基づいて具体的な検出ロジックを定義します。このロジックは、照合方法を決定します。 これは、Microsoft 365 Defender コンソールで検出をアラートとして表示する方法を定義する特定のアラート定義にバインドされます。

IOC の例を次に示します。
- 型: Sha1
- 値: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- アクション: 等しい

IOC は、アラート定義と多対 1 のリレーションシップを持ち、アラート定義に対応する多数の IOC を持つことができます。


## <a name="related-topics"></a>関連項目
- [インジケーターの管理](manage-indicators.md)
