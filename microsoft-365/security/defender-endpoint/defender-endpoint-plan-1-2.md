---
title: Microsoft エンドポイント セキュリティ計画の比較
description: Defender for Endpoint プラン 1 などの Microsoft エンドポイント セキュリティ プランと Defender for Endpoint プラン 2 を比較します。 プランの違いについて理解し、組織のニーズに合ったプランを選択します。
keywords: Defender for Endpoint, 高度な脅威に対する保護, エンドポイント保護, エンドポイント セキュリティ, デバイス セキュリティ, サイバーセキュリティ
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 07/25/2022
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.reviewer: shlomi, efratka
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 3340ec1b97cde08ed0aa7b3e74df3d0157d65474
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481330"
---
# <a name="compare-microsoft-endpoint-security-plans"></a>Microsoft エンドポイント セキュリティ計画の比較

Microsoft Defender for Endpoint や Microsoft 365 Defender などの Microsoft エンドポイント セキュリティ プランは、エンタープライズ組織が高度な脅威を防止、検出、調査、および対応できるように設計されています。 Microsoft Defender for Business と Microsoft 365 Business Premium は、中小企業向けに最適化された同様の機能を提供します。 これらのプランでは、ウイルス対策とマルウェア対策の保護、ランサムウェアの軽減などの高度な脅威保護と、一元的な管理とレポートが提供されます。 

この記事は、次のプランに含まれる内容を明確にするのに役立ちます。 

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender 脆弱性管理アドオン](../defender-vulnerability-management/index.yml)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md) および [Microsoft 365 Business Premium](../../business-premium/index.md)

> [!IMPORTANT]
> この記事では、Microsoft エンドポイント セキュリティ プランの脅威に対する保護機能の概要について説明します。ただし、サービスの説明やライセンス契約のドキュメントを意図したものではありません。 詳細詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

## <a name="compare-microsoft-endpoint-security-plans"></a>Microsoft エンドポイント セキュリティ計画の比較

次の表は、Microsoft エンドポイント セキュリティ プランに含まれる内容をまとめたものです。

| 計画 | 取り上げる内容 |
|:---|:---|
| [Defender for Endpoint プラン 1](defender-endpoint-plan-1.md) <sup>[[1](#fn1)]</sup> | <ul><li>[次世代保護](defender-endpoint-plan-1.md#next-generation-protection) (マルウェア対策とウイルス対策を含む)</li><li>[攻撃面の減少](defender-endpoint-plan-1.md#attack-surface-reduction)</li><li> [手動応答アクション](defender-endpoint-plan-1.md#manual-response-actions)</li><li>[集中管理](defender-endpoint-plan-1.md#centralized-management)</li><li>[セキュリティ レポート](defender-endpoint-plan-1.md#reporting)</li><li>[API](defender-endpoint-plan-1.md#apis)</li><li>[Windows 10、iOS、Android OS、macOS デバイスのサポート](defender-endpoint-plan-1.md#cross-platform-support)</li></ul>|
| [Defender for Endpoint プラン 2](microsoft-defender-endpoint.md) <sup>[[2](#fn2)]</sup> | Defender for Endpoint プラン 1 のすべての機能に加えて、次の機能も含まれます:<ul><li>[デバイス検出](device-discovery.md)</li><li>[デバイス一覧](machines-view-overview.md)</li><li>[コア Defender の脆弱性管理機能](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md)</li><li>[脅威の分析](threat-analytics.md)</li><li>[自動調査および対応](automated-investigations.md)</li><li>[高度な追求](advanced-hunting-overview.md)</li><li>[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)</li><li>[Microsoft 脅威エキスパート](microsoft-threat-experts.md)</li><li>[Windows](configure-endpoints.md) (クライアントとサーバー) および [Windows 以外のプラットフォーム](configure-endpoints-non-windows.md) (macOS、iOS、Android、Linux) のサポート</li></ul> |
| [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md) | その他の Defender for Endpoint プラン 2 の Defender 脅威と脆弱性の管理機能:<ul><li>[セキュリティ ベースラインの評価](../defender-vulnerability-management/tvm-security-baselines.md)</li><li>[脆弱なアプリケーションをブロックする](../defender-vulnerability-management/tvm-block-vuln-apps.md)</li><li>[ブラウザー拡張機能](../defender-vulnerability-management/tvm-browser-extensions.md)</li><li>[デジタル証明書の評価](../defender-vulnerability-management/tvm-certificate-inventory.md)</li><li>[ネットワーク共有分析](../defender-vulnerability-management/tvm-network-share-assessment.md)</li><li>[Windows](configure-endpoints.md) (クライアントとサーバー) および [Windows 以外のプラットフォーム](configure-endpoints-non-windows.md) (macOS、iOS、Android、Linux) のサポート</li></ul> |
| [Defender for Business](../defender-business/mdb-overview.md) <sup>[[3](#fn3)]</sup>  | [中小企業向けに最適化されたサービス](../defender-business/compare-mdb-m365-plans.md) は次のとおりです: <ul><li>メールの保護</li><li>スパム対策保護</li><li>マルウェア対策保護</li><li>次世代の保護</li><li>攻撃面の縮小</li><li>エンドポイントの検出および応答</li><li>自動調査および対応 </li><li>脆弱性管理</li><li>一元的なレポート</li><li>API (カスタム アプリまたはレポート ソリューションとの統合用)</li><li>[Microsoft 365 Lighthouse との統合](../defender-business/mdb-lighthouse-integration.md)</li></ul> |

(<a id="fn1">1</a>) Microsoft Defender for Endpoint プラン 1 は、商用および教育機関のお客様向けのスタンドアロン サブスクリプションとして利用できます。 また、Microsoft 365 E3/A3 の一部としても含まれています。

(<a id="fn2">2</a>) Microsoft Defender for Endpoint プラン 2 は、以前は Microsoft Defender for Endpoint と呼ばれ、スタンドアロン サブスクリプションとして利用できます。 また、次のプランの一部として含まれています:

- Windows 11 Enterprise E5/A5
- Windows 10 Enterprise E5/A5
- Microsoft 365 E5/A5/G5 (Windows 10 または Windows 11 Enterprise E5 を含む)
- Microsoft 365 E5/A5/G5/F5 Security
- Microsoft 365 F5 セキュリティ/コンプライアンス

(<a id="fn3">3</a>) Microsoft Defender for Business は、中小企業向けのスタンドアロン サブスクリプションとして使用できます。 Microsoft 365 Business Premium[の一](/microsoft-365/business-premium)部としても含まれています。 これらのプランには、簡単なセットアップと構成エクスペリエンスを備えた高度なセキュリティ機能が備わっています。 [「Microsoft Defender for BusinessとMicrosoft 365 Business Premiumを比較する」を参照](/microsoft-365/security/defender-business/compare-mdb-m365-plans#compare-microsoft-defender-for-business-to-microsoft-365-business-premium)してください。

## <a name="options-for-onboarding-servers"></a>サーバーをオンボードするためのオプション

Defender for Endpoint プラン 1 および 2 (スタンドアロン)、Defender for Business (スタンドアロン)、および Microsoft 365 Business Premium には、サーバー ライセンスは含まれていません。 サーバーをオンボードするには、次のオプションから選択します:

- [Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction) オファリングの一部としての **Microsoft Defender for Servers プラン 1 またはプラン 2**。 詳細情報。 「[Microsoft Defender for Servers の概要](/azure/defender-for-cloud/defender-for-servers-introduction)」を参照してください。
- 中小企業向けの **Microsoft Defender for Business サーバー (プレビュー)** です。 「[Microsoft Defender for Business サーバーの取得方法 (プレビュー)](../defender-business/get-defender-business-servers.md)」を参照してください。

## <a name="mixed-licensing-scenarios"></a>混合ライセンスのシナリオ

組織が、Defender for Endpoint プラン 1 や Defender for Endpoint プラン 2 など、Microsoft エンドポイント セキュリティ サブスクリプションを組み合わせて使用しているとします。 **現在もっとも機能の高い Microsoft エンドポイント セキュリティ サブスクリプションにより、テナントのエクスペリエンスが設定されます**。 この例では、テナント エクスペリエンスは、すべてのユーザーに対する Defender for Endpoint プラン 2 になります。

ただし、**サポートに問い合わせて、テナント エクスペリエンスのオーバーライドを要求することができます**。 つまり、すべてのユーザーに対して Defender for Endpoint プラン 1 エクスペリエンスを維持するためのオーバーライドを要求できます。 

- ライセンスと製品条項の詳細については、「[Microsoft 365 サブスクリプションのライセンスと製品条項](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA)」を参照してください。
- サポートに問い合わせる方法については、[Microsoft Defender for Endpoint サポートにお問い合わせ](contact-support.md)ください。

> [!TIP]
> 組織が中小企業の場合は、次の記事を参照してください:
> - [Defender for Business とは?](../defender-business/mdb-overview.md)
> - [中小企業向けの Microsoft 365 プランのセキュリティ機能を比較します](../defender-business/compare-mdb-m365-plans.md)。

## <a name="start-a-trial"></a>試用版の使用を開始する

- Defender for Endpoint を試すには、[Defender for Endpoint 試用版サインアップ ページ](https://go.microsoft.com/fwlink/p/?LinkID=2168109)に移動します。
- Defender for Endpoint プラン 2 の Microsoft Defender 脅威と脆弱性の管理アドオンを試すには、[https://aka.ms/AddonPreviewTrial](https://aka.ms/AddonPreviewTrial) にアクセスしてください。 

## <a name="see-also"></a>関連項目

- [Microsoft Security の使用を開始する (試用版プラン)](https://www.microsoft.com/security/business/get-started/start-free-trial)
- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md) (中小企業向けのエンドポイント保護)
