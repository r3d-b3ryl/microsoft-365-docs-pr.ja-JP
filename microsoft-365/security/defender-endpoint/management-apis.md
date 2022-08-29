---
title: 管理と API の概要
ms.reviewer: ''
description: Microsoft Defender for Endpointの管理ツールと API カテゴリについて説明します
keywords: オンボード, API, siem, rbac, アクセス, ポータル, 統合, 調査, 応答, エンティティ, エンティティ, ユーザー コンテキスト, アプリケーション コンテキスト, ストリーミング
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
ms.custom: api
ms.openlocfilehash: 493f83c3ba2e607a09d89e3570cbd4b0f65f6bfb
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327247"
---
# <a name="overview-of-management-and-apis"></a>管理と API の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)


Defender for Endpoint では、お客様がプラットフォームを簡単に採用できるように、さまざまなオプションがサポートされています。

顧客の環境と構造が異なる可能性があることを認識し、さまざまな顧客の要件に合わせて柔軟性ときめ細かな制御を備えた Defender for Endpoint が作成されました。

## <a name="endpoint-onboarding-and-portal-access"></a>エンドポイントのオンボードとポータル へのアクセス

デバイスオンボーディングは、クライアント デバイスと Microsoft Defender for server デバイスの Microsoft エンドポイント マネージャーとMicrosoft Intuneに完全に統合され、構成、展開、監視の完全なエンド ツー エンドエクスペリエンスを提供します。 さらに、Microsoft Defender for Endpointでは、デバイス管理に使用されるグループ ポリシーやその他のサードパーティツールがサポートされています。

Defender for Endpoint では、ポータルにアクセスできるユーザーがロールベースのアクセス制御 (RBAC) の柔軟性を通じて表示および実行できる内容をきめ細かく制御できます。 RBAC モデルでは、すべての種類のセキュリティ チーム構造がサポートされます。

- グローバルに分散された組織とセキュリティ チーム
- 階層型モデル のセキュリティ運用チーム
- 1 つの一元化されたグローバル セキュリティ運用チームを持つ完全に分離された部門

## <a name="available-apis"></a>使用可能な API

Microsoft Defender for Endpoint ソリューションは、統合対応プラットフォームの上に構築されています。

Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API を使用すると、Defender for Endpoint 機能に基づいてワークフローを自動化し、イノベーションを行えます。

:::image type="content" source="images/mdatp-apis.png" alt-text="Microsoft Defender for Endpointで使用可能な API と統合" lightbox="images/mdatp-apis.png":::

Defender for Endpoint API は、次の 3 つにグループ化できます。

- Microsoft Defender for Endpoint API
- 生データ ストリーミング API
- SIEM 統合

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API

Defender for Endpoint は、構造化された、明確で使いやすいモデルでデータと機能を公開する階層化された API モデルを提供し、標準の Azure AD ベースの認証と承認モデルを通じて公開され、ユーザーまたは SaaS アプリケーションのコンテキストでアクセスできます。 API モデルは、エンティティと機能を一貫した形式で公開するように設計されました。

Defender for Endpoint の API の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

**調査 API** では、Defender for Endpoint の豊富さが公開されます。計算されたエンティティまたは "プロファイリング済み" エンティティ (デバイス、ユーザー、ファイルなど) と個別のイベント (プロセスの作成やファイルの作成など) が公開されます。通常、エンティティに関連する動作が記述され、調査インターフェイスを介してデータにアクセスできるようになり、クエリベースのデータへのアクセスが可能になります。 詳細については、「 [サポートされている API」を参照](exposed-apis-list.md)してください。

**応答 API** では、サービスとデバイスでアクションを実行する機能が公開され、ユーザーはインジケーターの取り込み、設定の管理、アラートの状態の管理、デバイスのプログラムによる応答アクション (ネットワークからのデバイスの分離、検疫ファイルなど) を実行できます。

## <a name="raw-data-streaming-api"></a>生データ ストリーミング API

Defender for Endpoint 生データ ストリーミング API を使用すると、1 つのデータ ストリーム内で発生したインスタンスからリアルタイムのイベントとアラートを送信し、待機時間が短くスループットの高い配信メカニズムを提供できます。

Defender for Endpoint イベント情報は、長期的なデータ保持のために Azure Storage に直接プッシュされるか、視覚化サービスまたは追加のデータ処理エンジンによって使用するためにAzure Event Hubsされます。

詳細については、「 [生データ ストリーミング API](raw-data-export.md)」を参照してください。

新しい Microsoft 365 Defender Streaming API には、デバイス イベントに加えて、電子メール イベントとアラート イベントが含まれています。
詳細については、「[Microsoft 365 Defender ストリーミング API](../defender/streaming-api.md)」を参照してください。

## <a name="siem-api"></a>SIEM API

セキュリティ情報とイベント管理 (SIEM) 統合を有効にすると、SIEM ソリューションを使用するか、または検出 REST API に直接接続することで、検出をMicrosoft 365 Defenderからプルできます。 これにより、事前に設定された値を含む SIEM コネクタ アクセスの詳細セクションがアクティブ化され、Azure Active Directory (Azure AD) テナントの下にアプリケーションが作成されます。 

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
- [サポートされている API](exposed-apis-list.md)
- [テクニカル パートナーの機会](partner-integration.md)
