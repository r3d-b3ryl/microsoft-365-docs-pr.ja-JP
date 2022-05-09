---
title: Microsoft Defender for Endpointを他の Microsoft ソリューションと統合する
description: Microsoft Defender for IdentityやMicrosoft Defender for Cloudなど、Microsoft Defender for Endpointが他の Microsoft ソリューションと統合する方法について説明します。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 Defender, 条件付きアクセス, office, Microsoft Defender for Endpoint, microsoft Defender for IDENTITY, Microsoft Defender for office, Azure Defender, Microsoft クラウド アプリ セキュリティ, azure Sentinel
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4f220b16b0402215aa1fad0681edf241b61062ed
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321233"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender for Endpointおよびその他の Microsoft ソリューション

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>他の Microsoft ソリューションと統合する

Microsoft Defender for Endpointさまざまな Microsoft ソリューションと直接統合されます。

### <a name="microsoft-defender-for-cloud"></a>Microsoft Defender for Cloud

Microsoft Defender for Endpointは、Windows サーバーのエンドポイントでの検出と対応 (EDR) 機能を含む包括的なサーバー保護ソリューションを提供します。

### <a name="microsoft-sentinel"></a>Microsoft Sentinel

Microsoft Defender for Endpoint コネクタを使用すると、Microsoft Defender for Endpointから Microsoft Sentinel にアラートをストリーミングできます。 これにより、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応のためにプレイブックを構築できます。

### <a name="azure-information-protection"></a>Azure Information Protection

エンドポイント DLP 機能には、エンドポイント デバイスに格納された機密データに対する検出と保護の強化されたソリューションが組み込まれており、ソリューション間の可視性と統合を容易にするため、Azure Information Protection統合は最近非推奨になりました。 これは、次の [ブログ](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)で発表されました。 エンドポイント DLP の使用に移行することをお勧めします。

### <a name="conditional-access"></a>条件付きアクセス

Microsoft Defender for Endpointの動的なデバイス リスク スコアは条件付きアクセス評価に統合され、セキュリティで保護されたデバイスのみがリソースにアクセスできるようにします。

### <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Appsは、Microsoft Defender for Endpoint信号を利用して、サポートされていないクラウド サービス (シャドウ IT) をすべてのユーザーから使用するなど、クラウド アプリケーションの使用状況を直接可視化できるようにします監視対象のデバイスをMicrosoft Defender for Endpointします。

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

疑わしいアクティビティは、ユーザー コンテキストで実行されているプロセスです。 Microsoft Defender for EndpointとMicrosoft Defender for Identityの統合により、アクティビティや ID 全体でサイバー セキュリティ調査を柔軟に行うことができます。

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office

[Defender for Office 365は、](/office365/securitycompliance/office-365-atp)セーフ リンク、セーフ添付ファイル、高度なフィッシング対策、スプーフィング インテリジェンス機能を通じて、電子メール メッセージまたはファイル内のマルウェアから組織を保護するのに役立ちます。 Microsoft Defender for Office 365とMicrosoft Defender for Endpointの統合により、セキュリティ アナリストはアップストリームに移動して攻撃のエントリ ポイントを調査できます。 脅威インテリジェンス共有を通じて、攻撃を封じ込め、ブロックすることができます。

> [!NOTE]
> Defender for Office 365過去 30 日以内のイベントのデータが表示されます。 アラートの場合、Defender for Office 365データは最初のアクティビティ時間に基づいて表示されます。 その後、データはDefender for Office 365で使用できなくなります。

### <a name="skype-for-business"></a>Skype for Business

Skype for Business統合により、アナリストは、侵害された可能性のあるユーザーまたはデバイス所有者とポータルの簡単なボタンを使用して通信できます。

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

Microsoft 365 Defender、Microsoft Defender for Endpoint、およびさまざまな Microsoft セキュリティ ソリューションを使用すると、エンドポイント、ID、電子メール、およびアプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応する、侵害前および侵害後の統合エンタープライズ防御スイートが形成されます。

[Microsoft 365 Defenderの詳細を確認する](/microsoft-365/security/defender/microsoft-365-defender)

## <a name="related-topics"></a>関連項目

- [統合とその他の高度な機能を構成する](advanced-features.md)
- [Microsoft 365 Defenderの概要](/microsoft-365/security/defender/microsoft-365-defender)
- [Microsoft 365 Defender を有効にする](/microsoft-365/security/defender/m365d-enable)
- [条件付きアクセスを使用してユーザー、データ、デバイスを保護する](conditional-access.md)
