---
title: SIEM ツールとMicrosoft Defender for Endpointを統合する
description: インシデントとアラートを取り込み、SIEM ツールを統合する方法について説明します。
keywords: siem、セキュリティ情報とイベント管理ツール、splunk、arcsight、カスタム インジケーター、rest API、アラート定義、侵害のインジケーターを構成する
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
ms.openlocfilehash: 3bdb35b4251725dc4b2e69fc077d0edf29693cef
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020585"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>SIEM ツールとMicrosoft Defender for Endpointを統合する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートを取り込む

> [!NOTE]
>
> [Microsoft Defender for Endpoint アラート](alerts.md)は、デバイスで発生した 1 つ以上の疑わしいイベントまたは悪意のあるイベントとその関連する詳細から構成されます。 Microsoft Defender for Endpointアラート API は、アラートを使用するための最新の API であり、各アラートに関連する証拠の詳細な一覧が含まれています。 詳細については、「 [アラートのメソッドとプロパティ」と](alerts.md) 「 [アラートの一覧表示](get-alerts.md)」を参照してください。

Microsoft Defender for Endpointは、環境にインストールされている特定の SIEM ソリューションまたはコネクタを表す登録済み AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから情報を取り込むセキュリティ情報とイベント管理 (SIEM) ツールをサポートします。

詳細については、以下を参照してください。

- [Microsoft Defender for Endpoint API のライセンスと使用条件](api-terms-of-use.md) 
- [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
- [Hello World例 (Azure Active Directory にアプリケーションを登録する方法について説明します)](api-hello-world.md)
- [アプリケーション コンテキストでアクセスする](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpointは現在、次の SIEM ソリューション統合をサポートしています。 

- [Microsoft 365 Defenderからインシデントとアラートを取り込み、インシデントをMicrosoft Defender for Endpointし、REST API にアラートを送信する](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [Microsoft 365 Defender イベント ストリーミング API からのMicrosoft Defender for Endpoint イベントの取り込み](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>Microsoft 365 Defenderからインシデントとアラートを取り込み、インシデントをMicrosoft Defender for Endpointし、REST API にアラートを送信する

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>Microsoft 365 Defender インシデント REST API からのインシデントの取り込み

Microsoft 365 Defenderインシデント API の詳細については、「[インシデントのメソッドとプロパティ](../defender/api-incident.md)」を参照してください。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>Microsoft Defender for Endpoint アラート REST API からアラートを取り込む

Microsoft Defender for Endpoint アラート API の詳細については、「[アラートのメソッドとプロパティ](alerts.md)」を参照してください。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>SIEM ツールとMicrosoft Defender for Endpointの統合

### <a name="splunk"></a>Splunk

サポートする Splunk 用のMicrosoft 365 Defender アドオンの使用:

- Microsoft Defender for Endpointアラートの取り込み
- Splunk 内からMicrosoft Defender for Endpointのアラートを更新する

Splunk 用のMicrosoft 365 Defender アドオンの詳細については、「[splunkbase](https://splunkbase.splunk.com/app/4959/)」を参照してください。

### <a name="datadog"></a>Datadog

Endpoint と Datadog の統合のMicrosoft 365 Defenderは次をサポートします。

- Microsoft Defender for Endpointアラートとインシデントの取り込み
- エンドポイント、脅威と脆弱性、ソフトウェア全体の監視メトリックを有効にするダッシュボード

統合の詳細については、「 [Datadog Marketplace](https://app.datadoghq.com/marketplace/app/crest-data-systems-microsoft-defender/support)」を参照してください。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

Microsoft 365 Defender用の新しい SmartConnector は、Microsoft Defender for Endpointからのアラートを含むすべてのMicrosoft 365 Defender製品からのアラートを含むインシデントを ArcSight に取り込み、これらを Common Event Framework (CEF) にマップします。

新しい ArcSight SmartConnector for Microsoft 365 Defenderの詳細については、[ArcSight 製品のドキュメントを参照してください](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html)。

SmartConnector は、以前の FlexConnector をMicrosoft 365 Defenderに置き換えます。

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>IBM QRadar と Microsoft 365 Defender の統合(Microsoft Defender for Endpointを含む)は、次のように呼び出す新しいMicrosoft 365 Defenderデバイス サポート モジュール (DSM) によってサポートされるようになりました。[Microsoft Defender for Endpoint](../defender/streaming-api.md)を含むMicrosoft 365 Defender製品からストリーミング イベント データを取り込むストリーミング API をMicrosoft 365 Defenderします。 新しい QRadar Microsoft 365 Defender DSM の詳細については、「[IBM QRadar 製品ドキュメント」を参照](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender)し、Streaming API でサポートされるイベントの種類の詳細については、「[サポートされているイベントの種類](../defender/supported-event-types.md)」を参照してください。

新しい顧客は、以前の QRadar Microsoft Defender ATP デバイス サポート モジュール (DSM) を使用してオンボードされなくなり、既存のお客様は、すべてのMicrosoft 365 Defender製品との統合のシングル ポイントとして新しいMicrosoft 365 Defender DSM を採用することをお勧めします。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>Microsoft 365 Defender イベント ストリーミング API からのMicrosoft Defender for Endpoint イベントの取り込み

Microsoft 365 Defenderストリーミング イベント データには、Microsoft Defender for Endpointおよびその他の Microsoft Defender 製品からのアラートやその他のイベントが含まれます。 これらのイベントは、Azure Storage アカウントまたはAzure Event Hubsにストリーミングできます。 現在、イベント ハブを介した統合モデルは、Splunk と IBM QRadar によってサポートされています。

詳細については、「[MICROSOFT 365 DEFENDER SIEM 統合」を](../defender/configure-siem-defender.md)参照してください。
