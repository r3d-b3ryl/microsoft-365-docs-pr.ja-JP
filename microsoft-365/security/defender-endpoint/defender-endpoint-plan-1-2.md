---
title: Defender for Endpoint プランの比較
description: Defender for Endpoint プラン 1 とプラン 2 を比較します。 プランの違いについて理解し、組織のニーズに合ったプランを選択します。
keywords: Defender for Endpoint, Advanced Threat Protection, Endpoint Protection
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 06/17/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: shlomi, efratka
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: f55cfa3a9c32c6392f1c7d263f8e866ff4084e1e
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490015"
---
# <a name="compare-microsoft-defender-for-endpoint-plans"></a>Defender for Endpoint プランの比較

EndPoint 向け Microsoft Defender は、エンタープライズネットワークによる高度な脅威の防止、検出、調査、および応答を支援するために設計されたエンタープライズエンドポイントセキュリティプラットフォームです。 Defender for Endpoint は、ウイルス対策、マルウェア対策、ランサムウェアの軽減などの高度な脅威に対する保護と、集中管理およびレポート機能を提供します。 Microsoft Defender for Endpoint では、次のオプションから選択できます。

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事を使用すると、Defender for Endpoint Plan 1、Defender for Endpoint Plan 2、新しい Defender Vulnerability Management アドオン、およびMicrosoft 365 Defenderのさまざまな機能によってどのような保護が提供されているかを明確にすることができます。

## <a name="compare-defender-for-endpoint-plans"></a>Defender for Endpoint プランの比較

次の表は、各 Defender for Endpoint プランに含まれる内容をまとめたものです。

| 計画 | 取り上げる内容 |
|:---|:---|
| [Defender for Endpoint プラン 1](defender-endpoint-plan-1.md) | <ul><li>[次世代保護](defender-endpoint-plan-1.md#next-generation-protection) (マルウェア対策とウイルス対策を含む)</li><li>[攻撃面の減少](defender-endpoint-plan-1.md#attack-surface-reduction)</li><li> [手動応答アクション](defender-endpoint-plan-1.md#manual-response-actions)</li><li>[集中管理](defender-endpoint-plan-1.md#centralized-management)</li><li>[セキュリティ レポート](defender-endpoint-plan-1.md#reporting)</li><li>[API](defender-endpoint-plan-1.md#apis)</li><li>[Windows 10、iOS、Android OS、macOS デバイスのサポート](defender-endpoint-plan-1.md#cross-platform-support)</li></ul>|
| [Defender for Endpoint プラン 2](microsoft-defender-endpoint.md) | Defender for Endpoint Plan 1 のすべての機能に加えて、次の機能も含まれます。<ul><li>[デバイス検出](device-discovery.md)</li><li>[デバイス一覧](machines-view-overview.md)</li><li>[コア Defender の脆弱性管理機能](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md)</li><li>[脅威の分析](threat-analytics.md)</li><li>[自動調査および対応](automated-investigations.md)</li><li>[高度な追求](advanced-hunting-overview.md)</li><li>[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)</li><li>[Microsoft 脅威エキスパート](microsoft-threat-experts.md)</li><li>[Windows](configure-endpoints.md) (クライアントとサーバー) および [Windows 以外のプラットフォーム](configure-endpoints-non-windows.md) (macOS、iOS、Android、Linux) のサポート</li></ul> |
| [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md) | Defender for Endpoint プラン 2 の Defender 脆弱性管理機能の追加:<ul><li>[セキュリティ ベースラインの評価](../defender-vulnerability-management/tvm-security-baselines.md)</li><li>[脆弱なアプリケーションをブロックする](../defender-vulnerability-management/tvm-block-vuln-apps.md)</li><li>[ブラウザー拡張機能](../defender-vulnerability-management/tvm-browser-extensions.md)</li><li>[デジタル証明書の評価](../defender-vulnerability-management/tvm-certificate-inventory.md)</li><li>[ネットワーク共有分析](../defender-vulnerability-management/tvm-network-share-assessment.md)</li><li>[Windows](configure-endpoints.md) (クライアントとサーバー) および [Windows 以外のプラットフォーム](configure-endpoints-non-windows.md) (macOS、iOS、Android、Linux) のサポート</li></ul> |
| [Microsoft 365 Defender](../defender/microsoft-365-defender.md) | サービスには次のものが含まれます。 <ul><li>[Defender for Endpoint プラン 2](microsoft-defender-endpoint.md)</li><li>[Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/defender-vulnerability-management.md)</li><li>[Microsoft Defender for Office 365](../office-365-security/overview.md)</li><li>[Microsoft Defender for Identity](/defender-for-identity/)</li><li>[Microsoft Defender for Cloud Apps](/cloud-app-security/)</li></ul>|

> [!IMPORTANT]
> Defender for Endpoint プラン 1 とプラン 2 のスタンドアロン バージョンには、サーバー ライセンスは含まれません。 Windows Server や Linux を実行しているエンドポイントなどのサーバーをオンボードするには、 [Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction) オファリングの一部として Defender for Servers プラン 1 またはプラン 2 が必要です。 詳細については、こちらを参照してください。 [Microsoft Defender for Servers の概要に関するページを参照してください](/azure/defender-for-cloud/defender-for-servers-introduction)。

## <a name="mixed-licensing-scenarios"></a>混合ライセンスのシナリオ

組織が、Defender for Endpoint Plan 1 や Defender for Endpoint Plan 2 など、Microsoft エンドポイント セキュリティ サブスクリプションを組み合わせて使用しているとします。 **現在、最も機能の高い Microsoft エンドポイント セキュリティ サブスクリプションは、テナントのエクスペリエンスを設定します**。 この例では、テナント エクスペリエンスは、すべてのユーザーに対する Defender for Endpoint Plan 2 です。

ただし、 **サポートに問い合わせて、テナント エクスペリエンスのオーバーライドを要求することができます**。 つまり、すべてのユーザーに対して Defender for Endpoint Plan 1 エクスペリエンスを維持するためのオーバーライドを要求できます。 

- ライセンスと製品条項の詳細については、「 [Microsoft 365 サブスクリプションのライセンスと製品条項」を](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA)参照してください。
- サポートに問い合わせる方法については、「[Microsoft Defender for Endpoint サポートにお問い合わせください](contact-support.md)。

> [!TIP]
> 組織が小規模または中規模のビジネスの場合は、次の記事を参照してください。
> - [Microsoft Defender for Businessとは](../defender-business/mdb-overview.md)
> - [中小企業向けの Microsoft 365 プランのセキュリティ機能を比較します](../defender-business/compare-mdb-m365-plans.md)。

## <a name="start-a-trial"></a>試用版を開始する

- Defender for Endpoint プラン 1 を試す場合は、[https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) にアクセスしてください。
- Defender for Endpoint Plan 2 を試す場合は、[https://aka.ms/MDEp2OpenTrial](https://aka.ms/MDEp2OpenTrial) にアクセスしてください。
- Microsoft Defender 脆弱性の管理 アドオンを試すには、 [https://aka.ms/AddonPreviewTrial](https://aka.ms/AddonPreviewTrial). 

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Business](../defender-business/mdb-overview.md) (中小企業向けのエンドポイント保護)