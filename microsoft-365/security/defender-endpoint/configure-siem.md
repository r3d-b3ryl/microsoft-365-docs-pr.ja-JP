---
title: SIEM ツールをユーザー設定と統合Microsoft Defender for Endpoint
description: インシデントとアラートを取り込み、SIEM ツールを統合する方法について学習します。
keywords: siem、セキュリティ情報とイベント管理ツール、splunk、arcsight、カスタム インジケーター、rest API、アラート定義、侵害の指標を構成する
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
ms.openlocfilehash: ed88048b506ecfcddb8394667e7d800927fc1d83
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634913"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>SIEM ツールをユーザー設定と統合Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートを取り込む

> [!NOTE]
>
> [Microsoft Defender for Endpointアラートは](alerts.md)、デバイス上で発生した 1 つ以上の疑わしいイベントまたは悪意のあるイベントとその関連する詳細から構成されます。 アラート Microsoft Defender for Endpoint API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

Microsoft Defender for Endpointは、登録されたユーザーの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから情報を取り込むセキュリティ情報とイベント管理 (SIEM) ツールをサポートAAD 環境にインストールされている特定の SIEM ソリューションまたはコネクタを表すアプリケーション。

詳細については、以下を参照してください。

- [Microsoft Defender for Endpoint API ライセンスと使用条件](api-terms-of-use.md) 
- [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
- [Hello World例 (アプリケーションをアプリケーションに登録する方法Azure Active Directory)](api-hello-world.md)
- [アプリケーション コンテキストでアクセスする](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpointは、現在、次の SIEM ソリューション統合をサポートしています。 

- [ユーザーからのインシデントとアラートの取り込みMicrosoft 365 Defender、Microsoft Defender for Endpointおよびアラート REST API](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [イベント ストリーミング API Microsoft Defender for EndpointイベントMicrosoft 365 Defender取り込む](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>ユーザーからのインシデントとアラートの取り込みMicrosoft 365 Defender、Microsoft Defender for Endpointおよびアラート REST API

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>REST API からインシデントMicrosoft 365 Defender取り込む

インシデント API の詳細については、「Microsoft 365 Defenderメソッドとプロパティ[」を参照してください](../defender/api-incident.md)。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>REST API に対する通知Microsoft Defender for Endpoint取り込む

アラート API の詳細については、「Microsoft Defender for Endpointのメソッド[とプロパティ」を参照してください](alerts.md)。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>SIEM ツールとツールのMicrosoft Defender for Endpoint

### <a name="splunk"></a>Splunk

以下をMicrosoft 365 Defender Splunk 用のアドオンを使用します。

- アラートMicrosoft Defender for Endpoint取り込む
- Splunk 内からMicrosoft Defender for Endpointアラートを更新する

Splunk 用のMicrosoft 365 Defender詳細については、「[splunkbase」を参照してください](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

Microsoft 365 Defender 用の新しい SmartConnector は、Microsoft Defender for Endpoint を含むすべての Microsoft 365 Defender 製品からのアラートを含むインシデントを ArcSight に取り込み、これらを Common Event Framework (CEF) にマップします。

新しい ArcSight SmartConnector for Microsoft 365 Defender [ArcSight 製品のドキュメントを参照してください](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html)。

SmartConnector は、以前の FlexConnector のデータをMicrosoft 365 Defender。

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>IBM QRadar Microsoft 365 Defender との統合 (Microsoft Defender for Endpoint を含む) は、Microsoft 365 Defender デバイス サポート モジュール (DSM) でサポートされています。[Microsoft 365 Defenderを含](../defender/streaming-api.md)む、他の製品からストリーミング イベント データMicrosoft 365 Defender取り込Microsoft Defender for Endpoint。 新しい QRadar Microsoft 365 Defender DSM の詳細については、「[IBM QRadar](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender) 製品ドキュメント」、およびストリーミング API でサポートされるイベントの種類の詳細については、「サポートされるイベントの種類」[を参照](../defender/supported-event-types.md)してください。

新しい顧客は、以前の QRadar Microsoft Defender ATP デバイス サポート モジュール (DSM) を使用してオンボードされなくなりました。既存のお客様は、新しい Microsoft 365 Defender DSM をすべての Microsoft 365 Defender 製品との統合の単一ポイントとして採用してください。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>イベント ストリーミング API Microsoft Defender for EndpointイベントMicrosoft 365 Defender取り込む

Microsoft 365 Defenderストリーミング イベント データには、Microsoft Defender 製品や他の Microsoft Defender 製品からのMicrosoft Defender for Endpointその他のイベントが含まれます。 これらのイベントは、アカウントまたはアカウントにAzure StorageストリーミングAzure Event Hubs。 イベント ハブを介した統合モデルは、現在 Splunk と IBM QRadar でサポートされています。

詳細については、「SIEM 統合[のMicrosoft 365 Defender参照してください](../defender/configure-siem-defender.md)。
