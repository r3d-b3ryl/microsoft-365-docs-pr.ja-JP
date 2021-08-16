---
title: 管理と API の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint の管理ツールと API カテゴリについて説明します。
keywords: オンボーディング、api、siem、rbac、access、portal、統合、調査、応答、エンティティ、エンティティ、ユーザー コンテキスト、アプリケーション コンテキスト、ストリーミング
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 49a9d668182a065f3b0a5168f14ed9c7472e00ac37615518c31a252d22191861
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53902796"
---
# <a name="overview-of-management-and-apis"></a>管理と API の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)


Defender for Endpoint は、お客様がプラットフォームを簡単に採用できるよう、さまざまなオプションをサポートしています。

お客様の環境や構造が異なることがあります。 Defender for Endpoint は、さまざまなお客様の要件に合わせて柔軟性ときめ細かな制御で作成されました。

## <a name="endpoint-onboarding-and-portal-access"></a>エンドポイントのオンボーディングとポータル アクセス

デバイスオンボーディングは、クライアント デバイス用の Microsoft エンドポイント マネージャー と Microsoft Intune、サーバー デバイス用の Azure Defender に完全に統合され、構成、展開、監視の完全なエンドツーエンドエクスペリエンスを提供します。 さらに、Microsoft Defender for Endpoint では、デバイス管理に使用されるグループ ポリシーや他のサード パーティ製ツールもサポートしています。

Defender for Endpoint は、役割ベースのアクセス制御 (RBAC) の柔軟性を通じて、ポータルにアクセスできるユーザーが見て実行できる機能を詳細に制御します。 RBAC モデルは、セキュリティ チーム構造のすべての機能をサポートします。

- グローバルに分散した組織とセキュリティ チーム
- 階層モデルのセキュリティ運用チーム
- 単一のグローバル セキュリティ運用チームによる完全に分離された部門

## <a name="available-apis"></a>使用可能な API
Microsoft Defender for Endpoint ソリューションは、統合対応プラットフォームの上に構築されています。

Defender for Endpoint は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。 これらの API を使用すると、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。

![使用可能な API のイメージと Microsoft Defender for Endpoint での統合](images/mdatp-apis.png)

Defender for Endpoint API は、次の 3 つのグループにグループ化できます。

- エンドポイント API 用 Microsoft Defender
- 生データ ストリーミング API
- SIEM 統合

## <a name="microsoft-defender-for-endpoint-apis"></a>エンドポイント API 用 Microsoft Defender

Defender for Endpoint は、構造化された、明確で使いやすいモデルのデータと機能を公開する、ユーザーまたは SaaS アプリケーションのコンテキストでのアクセスを許可する標準の Azure AD ベースの認証および承認モデルを通じて公開される、レイヤー化された API モデルを提供します。 API モデルは、エンティティと機能を一貫性のある形式で公開するように設計されています。

Defender for Endpoint の API の概要については、このビデオをご覧ください。
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

Investigation **API** は、Defender for Endpoint の豊富さを公開します。計算エンティティまたは 'profiled' エンティティ (デバイス、ユーザー、ファイルなど) と、エンティティに関連する動作を記述する個別イベント (プロセスの作成やファイルの作成など) を公開し、クエリ ベースのデータへのアクセスを許可する調査インターフェイスを介してデータにアクセスできます。 詳細については、「サポートされている [API」を参照してください](exposed-apis-list.md)。

応答 **API** では、サービスとデバイスでアクションを実行する機能が公開され、顧客はインジケーターの取り込み、設定の管理、アラートの状態の管理、デバイスの応答アクション (ネットワークからのデバイスの分離、ファイルの検疫など) をプログラムで実行できます。

## <a name="raw-data-streaming-api"></a>生データ ストリーミング API

Defender for Endpoint raw data streaming API は、お客様が単一のデータ ストリーム内で発生するリアルタイム イベントとアラートをインスタンスから出荷する機能を提供し、低遅延で高スループットの配信メカニズムを提供します。

Defender for Endpoint イベント情報は、長期的なデータ保持のために Azure ストレージに直接プッシュされ、視覚化サービスや追加のデータ処理エンジンによって使用される Azure Event Hubs にプッシュされます。

詳細については、「Raw [data streaming API」を参照してください](raw-data-export.md)。

新しいストリーミング Microsoft 365 Defender API には、デバイス イベントに加えて、電子メールイベントとアラート イベントが含まれています。
詳細については、「ストリーミング[API Microsoft 365 Defenderを参照してください](../defender/streaming-api.md)。

## <a name="siem-api"></a>SIEM API

セキュリティ情報とイベント管理 (SIEM) 統合を有効にした場合、SIEM ソリューションを使用するか、検出 REST API に直接接続することで、Microsoft Defender セキュリティ センター から検出を取得できます。 これにより、値が事前に設定された SIEM コネクタ アクセスの詳細セクションがアクティブ化され、アプリケーションが Azure Active Directory (Azure AD) テナントの下に作成されます。 詳細については [、「SIEM 統合」を参照してください](enable-siem-integration.md)。

## <a name="related-topics"></a>関連トピック

- [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
- [サポートされている API](exposed-apis-list.md)
- [テクニカル パートナーの機会](partner-integration.md)