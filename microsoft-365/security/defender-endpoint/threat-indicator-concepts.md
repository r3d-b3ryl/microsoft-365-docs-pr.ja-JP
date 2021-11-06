---
title: Microsoft Defender for Endpoint の脅威インテリジェンスの概念を理解する
description: 組織のカスタム脅威アラートを作成し、Microsoft Defender for Endpoint の脅威インテリジェンスに関する概念を学ぶ
keywords: 脅威インテリジェンス、アラート定義、侵害の指標、ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 0451d875f149a875872f5d5a32d3580015dbfb0e
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2021
ms.locfileid: "60804882"
---
# <a name="understand-threat-intelligence-concepts"></a>脅威インテリジェンスの概念を理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)

高度なサイバーセキュリティ攻撃は、複数の複雑な悪意のあるイベント、属性、コンテキスト情報で構成されます。 これらのアクティビティの中で疑わしいと見なされるアクティビティを特定して決定すると、困難な作業になる可能性があります。 業界固有の既知の属性と異常なアクティビティに関する知識は、観測された動作を疑わしいと呼ぶ場合を知る上で基本的です。

このMicrosoft 365 Defender、組織で発生する可能性のある攻撃アクティビティを追跡するのに役立つカスタム脅威アラートを作成できます。 疑わしいイベントにフラグを立て、手がかりをまとめ、攻撃チェーンを停止できます。 これらのカスタム脅威アラートは組織にのみ表示され、追跡に設定したイベントにフラグを設定します。

カスタム脅威アラートを作成する前に、アラート定義と侵害の指標 (IOC) の背後にある概念と、その間の関係を理解することが重要です。

## <a name="alert-definitions"></a>アラートの定義
アラート定義はコンテキスト属性で、サイバーセキュリティ攻撃の可能性に関する早期の手がかりを特定するためにまとめて使用できます。 通常、これらのインジケーターは、攻撃の目的を達成するために攻撃者が実行したアクティビティ、特性、およびアクションの組み合わせです。 これらの属性の組み合わせを監視すると、攻撃に対する視点を得て、攻撃者の目標に達する前に一部のイベントに干渉する可能性があります。

## <a name="indicators-of-compromise-ioc"></a>侵害の指標 (IOC)
IOC は、ネットワークまたはデバイスが既に侵害されているという個別の既知の悪意のあるイベントです。 アラート定義とは異なり、これらのインジケーターは侵害の証拠と見なされます。 多くの場合、攻撃が既に実行され、その目的に達した後 (例: exfiltration など) 見られます。 IOC の追跡は、捜査の際にも重要です。 攻撃チェーンに介入できない場合でも、これらのインジケーターを収集すると、将来の攻撃に対する防御の向上に役立ちます。

## <a name="relationship-between-alert-definitions-and-iocs"></a>アラート定義と IOC の関係
Microsoft 365 Defender と Microsoft Defender for Endpoint のコンテキストでは、アラート定義は IOC のコンテナーであり、特定の IOC の一致に対して発生するメタデータを含むアラートを定義します。 アラート定義の一部として、さまざまなメタデータが提供されます。 攻撃のアラート定義名、重大度、説明などのメタデータは、他のオプションと共に提供されます。

各 IOC は、その種類、値、およびアクションに基づいて具体的な検出ロジックを定義し、その一致方法を決定します。 特定のアラート定義にバインドされ、検出がメッセージ コンソールにアラートとして表示される方法Microsoft 365 Defenderされます。

IOC の例を次に示します。
- 種類: Sha1
- 値: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Action: Equals

IOC は、アラート定義と多対 1 の関係を持ち、アラート定義に対応する IOC を多数持つ可能性があります。


## <a name="related-topics"></a>関連項目
- [インジケーターの管理](manage-indicators.md)
