---
title: Microsoft 365 Defender と SIEM ツールの統合
description: REST API を使用し、サポートされているセキュリティ情報とイベント管理ツールを構成して検出を受信およびプルする方法について説明します。
keywords: siem、セキュリティ情報とイベント管理ツール、splunk、arcsight、カスタム インジケーター、rest API、アラート定義、侵害のインジケーターを構成する
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3e2772fd458c60e48f78c0d4b816cdac8ca25940
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66530321"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>Microsoft 365 Defender と SIEM ツールの統合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>セキュリティ情報とイベント管理 (SIEM) ツールを使用して、Microsoft 365 Defenderインシデントとストリーミング イベント データをプルする

> [!NOTE]
>
> - [Microsoft 365 Defenderインシデントは、](incident-queue.md)関連付けられたアラートとその証拠のコレクションで構成されます。
> - [ストリーミング API Microsoft 365 Defender](streaming-api.md)、イベント データをMicrosoft 365 Defenderからイベント ハブまたは Azure ストレージ アカウントにストリーミングします。

Microsoft 365 Defenderでは、環境にインストールされている特定の SIEM ソリューションまたはコネクタを表す登録済み AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから情報を取り込むセキュリティ情報とイベント管理 (SIEM) ツールがサポートされます。 

詳細については、以下を参照してください。

- [Microsoft 365 Defender API のライセンスと使用条件](api-terms.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [Hello World の例](api-hello-world.md)
- [アプリケーション コンテキストでアクセスする](api-create-app-web.md)

セキュリティ情報を取り込むには、次の 2 つの主要なモデルがあります。 

1.  Azure の REST API からMicrosoft 365 Defenderインシデントとその包含アラートを取り込む。 

2.  Azure Event Hubs または Azure Storage アカウントを介してストリーミング イベント データを取り込む。 

Microsoft 365 Defenderは現在、次の SIEM ソリューション統合をサポートしています。 

- [インシデント REST API からのインシデントの取り込み](#ingesting-incidents-from-the-incidents-rest-api)
- [Event Hub を使用したストリーミング イベント データの取り込み](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>インシデント REST API からのインシデントの取り込み

### <a name="incident-schema"></a>インシデント スキーマ
包含アラートエンティティと証拠エンティティメタデータを含むMicrosoft 365 Defenderインシデント プロパティの詳細については、「[スキーマ マッピング」を](../defender/api-list-incidents.md#schema-mapping)参照してください。

### <a name="splunk"></a>Splunk

完全にサポートされている新しい Microsoft Security 用 Splunk アドオンを使用して、次の機能をサポートします。

- Splunk の Common Information Model (CIM) にマップされる、次の製品からのアラートを含むインシデントの取り込み:

  - Microsoft 365 Defender
  - Microsoft Defender for Endpoint
  - Microsoft Defender for Identityと Azure Active Directory Identity Protection
  - Microsoft Defender for Cloud Apps

- Defender for Endpoint アラート (Defender for Endpoint の Azure エンドポイントから) を取り込み、これらのアラートを更新する

- Microsoft 365 DefenderインシデントやMicrosoft Defender for Endpointアラートの更新のサポートと、それぞれのダッシュボードは、Microsoft 365 App for Splunk に移行されました。 

関連情報:

- Microsoft Security 用 Splunk アドオンについては、[Splunkbase の Microsoft Security アドオンを](https://splunkbase.splunk.com/app/6207/#/overview)参照してください。

- Splunk 用 Microsoft 365 アプリは、[Splunkbase 上の Microsoft 365 アプリを](https://splunkbase.splunk.com/app/3786/)参照してください

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

Microsoft 365 Defender用の新しい SmartConnector は、ArcSight にインシデントを取り込み、これらを Common Event Framework (CEF) にマップします。

新しい ArcSight SmartConnector for Microsoft 365 Defenderの詳細については、[ArcSight 製品ドキュメントを参照してください](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)。

SmartConnector は、非推奨になった以前の FlexConnector をMicrosoft Defender for Endpointに置き換えます。
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>Event Hubs を使用したストリーミング イベント データの取り込み

まず、AAD テナントから Event Hubs または Azure Storage アカウントにイベントをストリーミングする必要があります。 詳細については、「 [ストリーミング API](../defender/streaming-api.md)」を参照してください。

Streaming API でサポートされているイベントの種類の詳細については、「 [サポートされているストリーミング イベントの種類](../defender/supported-event-types.md)」を参照してください。

### <a name="splunk"></a>Splunk

Microsoft Cloud Services 用 Splunk アドオンを使用して、Azure Event Hubsからイベントを取り込みます。  

Microsoft Cloud Services 用 Splunk アドオンの詳細については、[Microsoft Cloud Services アドオン on Splunkbase を](https://splunkbase.splunk.com/app/3110/)参照してください。
  

### <a name="ibm-qradar"></a>IBM QRadar
>Event Hubs または Azure Storage アカウントを介してMicrosoft 365 Defender製品からストリーミング イベント データを取り込む[Microsoft 365 Defender ストリーミング API](streaming-api.md) を呼び出す新しい IBM QRadar Microsoft 365 Defender デバイス サポート モジュール (DSM) を使用します。 サポートされているイベントの種類の詳細については、「 [サポートされているイベントの種類](supported-event-types.md)」を参照してください。
