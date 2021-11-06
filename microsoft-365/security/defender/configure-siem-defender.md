---
title: SIEM ツールをユーザー設定と統合Microsoft 365 Defender
description: REST API を使用し、サポートされているセキュリティ情報とイベント管理ツールを構成して検出を受信およびプルする方法について説明します。
keywords: siem、セキュリティ情報とイベント管理ツール、splunk、arcsight、カスタム インジケーター、rest API、アラート定義、侵害の指標を構成する
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
ms.openlocfilehash: e4f67bed002c1864403be9458aae230eac0e7340
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2021
ms.locfileid: "60805017"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>SIEM ツールをユーザー設定と統合Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>セキュリティMicrosoft 365 Defenderイベント管理 (SIEM) ツールを使用して、インシデントとストリーミング イベント データをプルする

> [!NOTE]
>
> - [Microsoft 365 Defenderインシデントは](incident-queue.md)、相関アラートとその証拠のコレクションで構成されます。
> - [Microsoft 365 Defender API は](streaming-api.md)、イベント データMicrosoft 365 Defenderハブまたは Azure ストレージ アカウントにストリーミングします。

Microsoft 365 Defenderは、Azure Active Directory (AAD) のエンタープライズ テナントから特定の SIEM ソリューションまたはコネクタを表す登録済み AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して情報を取り込むセキュリティ情報とイベント管理 (SIEM) ツールをサポートします。環境。 

詳細については、以下を参照してください。

- [Microsoft 365 DefenderAPI ライセンスと使用条件](api-terms.md)
- [API にMicrosoft 365 Defenderする](api-access.md)
- [Hello World の例](api-hello-world.md)
- [アプリケーション コンテキストでアクセスする](api-create-app-web.md)

セキュリティ情報を取り込む 2 つの主要なモデルがあります。 

1.  Azure Microsoft 365 Defenderの REST API から、インシデントとその含まれているアラートを取り込む。 

2.  Azure Event Hubs またはアカウントを介してストリーミング イベント データをAzure Storageします。 

Microsoft 365 Defenderは現在、次の SIEM ソリューション統合をサポートしています。 

- [インシデント REST API からのインシデントの取り込み](#ingesting-incidents-from-the-incidents-rest-api)
- [イベント ハブ経由でのストリーミング イベント データの取り込み](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>インシデント REST API からのインシデントの取り込み

### <a name="incident-schema"></a>インシデント スキーマ
含まれているアラートエンティティと証拠エンティティMicrosoft 365 Defender含むインシデント プロパティの詳細については、「スキーマ マッピング」[を参照してください](../defender/api-list-incidents.md#schema-mapping)。

### <a name="splunk"></a>Splunk

以下をMicrosoft 365 Defender Splunk 用のアドオンを使用します。 

- Splunk の共通情報モデル (CIM) にマップされている次の製品からのアラートを含むインシデントを取り込む。  
  - Microsoft 365 Defender 
  - Microsoft Defender for Endpoint 
  - Microsoft Defender for Identity & Azure Active Directory Id Protection 
  - Microsoft Cloud App Security 

- Splunk 内からMicrosoft 365 Defenderインシデントを更新する 

- エンドポイントの Defender アラート (エンドポイントの Azure エンドポイントの Defender から) を取り込み、これらのアラートを更新する 

Splunk 用のMicrosoft 365 Defender詳細については[、「splunkbase」を参照してください](https://splunkbase.splunk.com/app/4959/)。

  

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

新しい SmartConnector for Microsoft 365 Defenderインシデントを ArcSight に取り込み、これらを Common Event Framework (CEF) にマップします。 

新しい ArcSight SmartConnector for Microsoft 365 Defenderについては[、「ArcSight 製品ドキュメント」を参照してください](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)。

SmartConnector は、Microsoft Defender for Endpoint の以前の FlexConnector を置き換える。
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>イベント ハブ経由でのストリーミング イベント データの取り込み

まず、テナントからイベント ハブまたは AAD アカウントにイベントをストリームAzure Storageがあります。 詳細については、「ストリーミング [API」を参照してください](../defender/streaming-api.md)。

ストリーミング API でサポートされるイベントの種類の詳細については、「サポートされるストリーミング イベントの [種類」を参照してください](../defender/supported-event-types.md)。

### <a name="splunk"></a>Splunk
Azure Event Hubs からイベントを取り込むには、Microsoft Cloud Services 用 Splunk アドオンを使用します。  


Microsoft Cloud Services 用 Splunk アドオンの詳細については [、「splunkbase」を参照してください](https://splunkbase.splunk.com/app/3110/)。
  

### <a name="ibm-qradar"></a>IBM QRadar
>[Microsoft 365 Defender](streaming-api.md)ストリーミング API を呼び出す新しい IBM QRadar Microsoft 365 Defender デバイス サポート モジュール (DSM) を使用して、Microsoft 365 Defender 製品からストリーミング イベント データを取り込む。 サポートされているイベントの種類の詳細については、「サポートされている [イベントの種類」を参照してください](supported-event-types.md)。

