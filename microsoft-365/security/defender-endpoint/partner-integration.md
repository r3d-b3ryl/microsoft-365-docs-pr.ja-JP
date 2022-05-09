---
title: Microsoft Defender for Endpointパートナーの機会とシナリオ
ms.reviewer: ''
description: オープン フレームワークと豊富な API セットに基づいて既存のセキュリティ オファリングを拡張し、拡張機能とMicrosoft Defender for Endpointとの統合を構築する方法について説明します。
keywords: API、パートナー、拡張、オープン フレームワーク、API、拡張機能、統合、検出、管理、応答、脆弱性、インテリジェンス
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
ms.openlocfilehash: a06f02fe216953d6d84fea205e06a9291f8902c9
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168476"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a>Microsoft Defender for Endpointパートナーの機会とシナリオ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


パートナーは、オープン フレームワークと豊富で完全な API のセットに基づいて既存のセキュリティ オファリングを簡単に拡張し、Defender for Endpoint との拡張機能と統合を構築できます。 

API は、検出、管理、対応、脆弱性、インテリジェンスの広範なユース ケースなど、機能領域にまたがっています。 ユース ケースとニーズに基づいて、パートナーは Defender for Endpoint からデータをストリーミングまたはクエリできます。 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a>シナリオ 1: 外部アラートの関連付けと自動調査と修復
Defender for Endpoint には、インシデント対応を大規模に推進するための独自の自動調査と修復機能が用意されています。 

自動調査と対応機能を、ネットワーク セキュリティ製品や他のエンドポイント セキュリティ製品などの他のソリューションと統合すると、アラートに対処するのに役立ちます。 また、この統合により、ネットワークとデバイスの信号の相関関係を取り巻く複雑さが最小限に抑えられるので、デバイスの調査と脅威の修復アクションが効果的に合理化されます。

Defender for Endpoint は、次の形式でこのシナリオのサポートを追加します。

- 外部アラートを Defender for Endpoint にプッシュし、Defender for Endpoint からの追加のデバイス ベースのアラートと並べて表示できます。 このビューでは、アラートの完全なコンテキスト (実際のプロセスと攻撃の完全なストーリー) が提供されます。

- アラートが生成されると、企業内のすべての Defender for Endpoint で保護されたエンドポイント間で信号が共有されます。 Defender for Endpoint は、アラートに対処するために、直ちに自動化された応答またはオペレーター支援応答を受け取ります。

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a>シナリオ 2: セキュリティ オーケストレーションと自動化応答 (SOAR) の統合
オーケストレーション ソリューションは、プレイブックを構築し、Defender for Endpoint API が公開する豊富なデータ モデルとアクションを統合して、デバイス データのクエリ、デバイスの分離のトリガー、ブロック/許可、アラートの解決などの応答を調整するのに役立ちます。

## <a name="scenario-3-indicators-matching"></a>シナリオ 3: 一致するインジケーター 
侵害インジケーター (IoCs) マッチングは、すべてのエンドポイント保護ソリューションで不可欠な機能です。 この機能は Defender for Endpoint で使用でき、エンティティの防止、検出、除外に関するインジケーターの一覧を設定できます。 実行するアクションと、アクションを適用する期間を定義できます。

上記のシナリオは、プラットフォームの拡張性の例として機能します。 あなたは例に限らず、オープン フレームワークを活用して他のシナリオを見つけて探索することをお勧めします。

「[Microsoft Defender for Endpoint パートナーになる」](get-started-partner-integration.md)の手順に従って、Defender for Endpoint でソリューションを統合します。

## <a name="related-topic"></a>関連トピック
- [管理と API の概要](management-apis.md)
