---
title: SIEM ツールを Microsoft Defender for Endpoint に統合する
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
ms.openlocfilehash: e241ae3b5250839d98d1692f38fb36333e9a69ca
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218672"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>SIEM ツールを Microsoft Defender for Endpoint に統合する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>セキュリティ情報とイベント管理 (SIEM) ツールを使用してアラートを取り込む

> [!NOTE]
>
> [Microsoft Defender for Endpoint Alert は](alerts.md) 、デバイスで発生した 1 つ以上の疑わしいイベントまたは悪意のあるイベントとその関連する詳細から構成されます。 Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

Microsoft Defender for Endpoint は、環境にインストールされている特定の SIEM ソリューションまたはコネクタを表す登録済み AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから情報を取り込むセキュリティ情報とイベント管理 (SIEM) ツールをサポートしています。 

詳細については、以下を参照してください。

- [Microsoft Defender for Endpoint API のライセンスと使用条件](api-terms-of-use.md) 
- [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
- [Hello World の例 (アプリケーションをアプリに登録するAzure Active Directory)](api-hello-world.md)
- [アプリケーション コンテキストでアクセスする](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpoint は現在、次の SIEM ソリューション統合をサポートしています。 

- [エンドポイント インシデントとアラート REST API のMicrosoft 365 Defender Microsoft Defender からインシデントとアラートを取り込む](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [Microsoft Defender for Endpoint イベントをイベント ストリーミング API Microsoft 365 Defender取り込む](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>エンドポイント インシデントとアラート REST API のMicrosoft 365 Defender Microsoft Defender からインシデントとアラートを取り込む

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>インシデント REST API からインシデントMicrosoft 365 Defender取り込む

インシデント API の詳細については、「Microsoft 365 Defenderメソッドとプロパティ」[を参照してください](../defender/api-incident.md)。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>Microsoft Defender for Endpoint アラート REST API からのアラートの取り込み

Microsoft Defender for Endpoint アラート API の詳細については [、「alerts メソッドとプロパティ」を参照してください](alerts.md)。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>エンドポイント向け Microsoft Defender との SIEM ツールの統合

### <a name="splunk"></a>Splunk

以下をMicrosoft 365 Defender Splunk 用のアドオンを使用します。 

- エンドポイント通知の Microsoft Defender の取り込み 
- Microsoft Defender for Endpoint のアラートを Splunk 内から更新する 

Splunk 用のMicrosoft 365 Defender詳細については[、「splunkbase」を参照してください](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

Microsoft 365 Defender 用の新しい SmartConnector は、Microsoft Defender for Endpoint を含むすべての Microsoft 365 Defender 製品からのアラートを含むインシデントを ArcSight に取り込み、これらを Common Event Framework (CEF) にマップします。 

新しい ArcSight SmartConnector for Microsoft 365 Defenderについては[、「ArcSight 製品」のドキュメントを参照してください](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)。

SmartConnector は、以前の FlexConnector のデータをMicrosoft 365 Defender。
  
### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>
>IBM QRadar と Microsoft Defender for Endpoint との統合は、Microsoft 365 Defender ストリーミング API を呼び出す新しい[Microsoft 365 Defender](../defender/streaming-api.md)デバイス サポート モジュール (DSM) でサポートされ、Microsoft 365 Defender からストリーミング イベント データを取り込Microsoft 365 Defender Microsoft Defender for Endpoint を含む製品。 サポートされているイベントの種類の詳細については、「サポートされている [イベントの種類」を参照してください](../defender/supported-event-types.md)。
新しい顧客は、以前の QRadar Microsoft Defender ATP デバイス サポート モジュール (DSM) を使用してオンボードされなくなりました。既存のお客様は、新しい Microsoft 365 Defender DSM をすべての Microsoft 365 Defender 製品との統合の単一ポイントとして採用してください。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>Microsoft Defender for Endpoint イベントをイベント ストリーミング API Microsoft 365 Defender取り込む

Microsoft 365 Defenderストリーミング イベント データには、Microsoft Defender for Endpoint および他の Microsoft Defender 製品からのアラートなどのイベントが含まれます。 これらのイベントは、アカウントまたは Azure イベント Azure Storageにストリーミングできます。 イベント ハブを介した統合モデルは、現在 Splunk と IBM QRadar でサポートされています。

詳細については、「SIEM 統合のMicrosoft 365 Defender[参照してください](../defender/configure-siem-defender.md)。
