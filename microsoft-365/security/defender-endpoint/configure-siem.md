---
title: Microsoft Defender for Endpoint から SIEM ツールに検出をプルする
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 23940fc05e08dec6074dbdc420d529425cec0027
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2021
ms.locfileid: "53595824"
---
# <a name="pull-detections-to-your-siem-tools"></a>SIEM ツールへの検出のプル

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>セキュリティ情報とイベント管理 (SIEM) ツールを使用したプル検出

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。
>- [Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。
>-Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

Defender for Endpoint は、検出をプルするためのセキュリティ情報とイベント管理 (SIEM) ツールをサポートします。 Defender for Endpoint は、Azure でホストされている HTTPS エンドポイントを通じてアラートを公開します。 エンドポイントは、環境にインストールされている特定の SIEM コネクタを表す AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから検出を取得するように構成できます。

Defender for Endpoint は現在、専用の SIEM 統合モデルを通じて、次の特定の SIEM ソリューション ツールをサポートしています。

- IBM QRadar
- Micro Focus ArcSight

他の SIEM ソリューション (Splunk、RSA NetWitness など) は、新しいアラート API に基づく別の統合モデルを介してサポートされます。 詳細については、[パートナー アプリケーション] [ページを表示](https://securitycenter.microsoft.com/interoperability/partners) し、[セキュリティ情報と分析] セクションを選択して詳細を確認します。

サポートされている SIEM ツールのいずれかを使用するには、次の手順を実行する必要があります。

- [Defender for Endpoint で SIEM 統合を有効にする](enable-siem-integration.md)
- サポートされている SIEM ツールを構成します。
     - [エンドポイント検出用の Defender をプルする Micro Focus ArcSight の構成](configure-arcsight.md)
     - エンドポイント検出用 Defender をプルする IBM QRadar を構成する 詳細については [、「IBM Knowledge Center」を参照してください](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。

検出 API で公開されているフィールドの一覧の詳細については、「Defender for Endpoint Detection [fields」を参照してください](api-portal-mapping.md)。
