---
title: Microsoft Defender for Business と他のプランをMicrosoft 365する
description: Defender for Business と Defender for Endpoint の違いを理解します。 各プランに含まれる情報を確認すると、組織に関する情報に基づいた意思決定を行う際に役立ちます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.date: 02/26/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: 3d8270b2c8424668200e4242cb65e491a2cc6991
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464982"
---
# <a name="compare-microsoft-defender-for-business-preview-to-microsoft-365-business-premium"></a>Microsoft Defender for Business (プレビュー) と Microsoft Defender Microsoft 365 Business Premium

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft は、中小企業向けのさまざまなプランを含む、さまざまなクラウド ソリューションとサービスを提供しています。 たとえば[、セキュリティMicrosoft 365 Business Premium](../../business/microsoft-365-business-overview.md)デバイス管理機能、および生産性機能 (アプリなど) が含Officeします。 

**この記事は、次の場合に使用します**。

- [Microsoft Defender for Business (プレビュー) と Microsoft Defender Microsoft 365 Business Premium](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)
- [Defender for Business と Microsoft Defender for Endpoint エンタープライズ オファリングの比較](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)


**Microsoft Defender for Business (プレビュー) をMicrosoft 365、サブスクリプションを使用する必要があります。** Microsoft Defender for Business (プレビュー) は、中小企業向けスタンドアロン のセキュリティ ソリューションです。 別のサブスクリプション (Microsoft 365 Business Basic や Standard など) を既に持っている場合は、Microsoft Defender for Business を追加して、より多くの脅威保護機能を取得してください。 

> [!TIP]
> 組織が小規模または中規模のビジネス (300 人以下のユーザー) で、Microsoft Defender for Business プレビュー プログラムにサインアップする場合は、 を参照してください [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview)。 詳細については、「 [Get Microsoft Defender for Business」を参照してください](get-defender-business.md)。

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Microsoft Defender for Business のセキュリティ機能とセキュリティ機能を比較Microsoft 365 Business Premium

> [!NOTE]
> この記事は、Microsoft Defender for Business (プレビュー) およびセキュリティ 保護機能に含まれる脅威保護機能の概要を提供することを目的Microsoft 365 Business Premium。 この記事は、サービスの説明またはライセンス契約ドキュメントとして機能することを意図した記事ではありません。 詳細については、「セキュリティと[コンプライアンスMicrosoft 365ライセンス ガイダンス」を&してください。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

次の表は、Defender for Business のセキュリティ機能と機能を、Defender for Business がプレビュー中Microsoft 365 Business Premiumと比較します。 Defender for Business が一般に利用できる状態になると、その Defender はビジネス にMicrosoft 365 Business Premium。 <br/><br/>

| 機能/機能 | [Microsoft Defender for Business](mdb-overview.md) (プレビュー) | [Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md) |
|:---|:---|:---|
| 電子メールの保護 | はい ([電子メール スキャン](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md) (Microsoft Defender ウイルス対策) | はい ([Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)) |
| スパム対策の保護 | はい (デバイスの場合) | はい (メッセージMicrosoft 365添付ファイルなどの電子メール コンテンツの場合) |
| マルウェア対策保護 | はい (デバイスの場合) | はい (メッセージMicrosoft 365添付ファイルなどの電子メール コンテンツの場合) |
| [次世代の保護](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (ウイルス対策とマルウェア対策の保護) | はい (Microsoft Defender ウイルス対策は、Windows 10以降に含まれます)  | はい (Microsoft Defender ウイルス対策は、Windows 10以降に含まれます) |
| [攻撃面の減少](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(攻撃表面の縮小ルールと他の保護)  | はい (攻撃表面の縮小ルールは、Windows 10以降に組み込み、さらに集中管理された機能) | はい (攻撃表面の縮小ルールは、Windows 10以降に組み込む) |
| [エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md) | はい。 含まれる内容: <br/>- 動作ベースの検出 <br/>- 手動応答アクション <br/>- ライブ応答   | 不要 |
| [自動調査および対応](../defender-endpoint/automated-investigations.md) | はい | 不要 |
| [脅威と脆弱性の管理](../defender-endpoint/tvm-dashboard-insights.md) | はい | いいえ |
| 集中管理とレポート作成 | はい。 クライアント デバイスWindowsオンボーディングして管理するには、Microsoft 365 Defender ポータル () で管理するか、[https://security.microsoft.com](https://security.microsoft.com)Microsoft エンドポイント マネージャーを選択します[https://endpoint.microsoft.com](https://endpoint.microsoft.com)。 | はい。 クライアント デバイスのWindows管理するには、Microsoft 365 管理センターします[https://admin.microsoft.com](https://admin.microsoft.com)。 デバイスは、デバイス () でオンボードMicrosoft エンドポイント マネージャー必要があります[https://endpoint.microsoft.com](https://endpoint.microsoft.com)。 |
| [API](../defender-endpoint/apis-intro.md) <br/>(カスタム アプリやレポート ソリューションと統合できます)  | はい | はい |



## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Microsoft Defender for Business と Microsoft Defender for Endpoint Plans 1 および 2 を比較する

Defender for Business (プレビュー) は、Defender for Endpoint のエンタープライズ レベルの機能を中小企業にも提供します。 次の表は、Defender for Business (プレビュー) のセキュリティ機能と Microsoft Defender for Endpoint Plans 1 および 2 を比較しています。 <br/><br/>

| 機能/機能 | [Defender for Business](mdb-overview.md) (プレビュー) | [Defender for Endpoint プラン 1](../defender-endpoint/defender-endpoint-plan-1.md) | [Defender for Endpoint Plan 2](../defender-endpoint/microsoft-defender-endpoint.md) |
|:---|:---|:---|
| [集中管理](../defender-endpoint/manage-atp-post-migration.md) <sup>[[1](#fn1)]</sup> | はい | はい | はい |
| [簡略化されたクライアント構成](mdb-simplified-configuration.md) | はい | 不要 | 不要 |
| [脅威と脆弱性の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) | はい | 不要 | はい |
| [攻撃表面の縮小機能](../defender-endpoint/overview-attack-surface-reduction.md) | はい | はい | はい |
| [次世代の保護](../defender-endpoint/next-generation-protection.md) | はい | はい | はい |
| [エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md) | は <sup>い [[2](#fn2)]</sup> | 不要 | はい |
| [自動調査および対応](../defender-endpoint/automated-investigations.md) | は <sup>い [[2](#fn2)]</sup> | 不要 | はい |
| [脅威の検出](../defender-endpoint/advanced-hunting-overview.md) と 6 か月間のデータ保持 | 不要 | いいえ | はい |
| [脅威の分析](../defender-endpoint/threat-analytics.md) | は <sup>い [[2](#fn2)]</sup> | いいえ | はい |
| [クロスプラットフォームのサポート](../defender-endpoint/minimum-requirements.md) <br/>(Windows macOS、iOS、および Android OS) | は <sup>い [[3](#fn3)]</sup> | はい | はい |
| [Microsoft 脅威エキスパート](../defender-endpoint/microsoft-threat-experts.md) | いいえ | いいえ | はい |
| パートナー API | はい | はい | はい |
| [Microsoft 365 Lighthouse統合](../../lighthouse/m365-lighthouse-overview.md) <br/>(顧客テナント間でセキュリティ インシデントを表示する場合) | はい | 不要 | いいえ |

(<a id="fn1">1</a>) Microsoft 365 Defenderポータル () または別のツール ([https://security.microsoft.com](https://security.microsoft.com)など) でデバイスをオンボードMicrosoft エンドポイント マネージャー管理します[https://endpoint.microsoft.com](https://endpoint.microsoft.com)。

(<a id="fn2">2</a>) これらの機能は、中小企業向けに最適化されています。

(<a id="fn3">3</a>) プレビュー プログラム中に、Windowsクライアント デバイスがポータル () でMicrosoft 365 Defenderされます[https://security.microsoft.com](https://security.microsoft.com)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business の要件 (プレビュー) を参照してください。](mdb-requirements.md)

- [Microsoft Defender for Business (プレビュー) を設定および構成する方法について説明します。](mdb-setup-configuration.md) 