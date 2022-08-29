---
title: 中小企業向けの Microsoft 365 プランのセキュリティ機能を比較する
description: Defender for Business と Defender for Endpoint と Microsoft 365 Business Premiumの比較 会社の情報に基づいた意思決定を行うことができるように、各プランに含まれる内容を確認します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: 4cb0ca9f318041bb209fedf567baa5987e39b61a
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67343070"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>中小企業向けの Microsoft 365 プランのセキュリティ機能を比較する

Microsoft では、中小企業向けの計画など、さまざまなクラウド ソリューションとサービスを提供しています。 たとえば、[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)には、Office アプリなどの生産性機能と共に、セキュリティとデバイス管理機能が含まれます。 この記事では、Microsoft 365 Business Premium、Microsoft Defender for Business、[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)のセキュリティ機能について説明します。


**この記事を使用して、次の操作を行います**。

- [Microsoft Defender for BusinessをMicrosoft 365 Business Premiumと比較します](#compare-microsoft-defender-for-business-to-microsoft-365-business-premium)。
- [Defender for Business (スタンドアロン) と Defender for Endpoint エンタープライズ オファリングを比較します](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)。

> [!TIP]
> Defender for Business は、中小企業向けのスタンドアロン セキュリティ ソリューションとして利用できます。 Defender for Business がMicrosoft 365 Business Premiumに含まれるようになりました。 Microsoft 365 Business Basicまたは Standard が既にある場合は、Microsoft 365 Business Premiumにアップグレードするか、現在のサブスクリプションに Defender for Business を追加して、デバイスの脅威保護機能を強化することを検討してください。

## <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Microsoft Defender for BusinessをMicrosoft 365 Business Premiumと比較する

> [!NOTE]
> この記事では、Microsoft Defender for Business (スタンドアロン プラン) とMicrosoft 365 Business Premium (Defender for Business を含む) に含まれる機能の概要について説明します。 サービスの説明やライセンス契約のドキュメントを意図したものではありません。 詳細詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

| Microsoft Defender for Business (スタンドアロン) | Microsoft 365 Business Premium |
|:---|:---|
| デバイスのウイルス対策、マルウェア対策、ランサムウェア保護機能は次のとおりです。 <ul><li>[次世代保護](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) (クラウド保護と共にデバイス上のウイルス対策/マルウェア対策保護)</li><li>[攻撃面の縮小](../defender-endpoint/overview-attack-surface-reduction.md) (ネットワーク保護、ファイアウォール、および攻撃表面の縮小ルール) <sup>[[a](#fna)]</sup></li><li>[エンドポイントの検出と応答](../defender-endpoint/overview-endpoint-detection-response.md) (動作ベースの検出と手動の応答アクション)</li><li>[自動調査と対応](../defender/m365d-autoir.md) (検出された脅威に対する自己修復を使用)</li><li>[Microsoft Defender 脆弱性の管理](mdb-view-tvm-dashboard.md) (公開されているデバイスと推奨事項を表示する)</li><li>デバイス (Windows、Mac、iOS、Android) の[クロスプラットフォームサポート](mdb-onboard-devices.md) <sup>[[b](#fnb)]</sup></li><li>[一元管理とレポート (](mdb-get-started.md)Microsoft 365 Defender ポータル)</li><li>[統合用 API](../defender-endpoint/management-apis.md) (Microsoft パートナーまたはカスタム ツールとアプリ用)</li></ul><br/><br/><br/><br/><br/><br/><br/> | 生産性とセキュリティの機能は次のとおりです。<ul><li>[Microsoft 365 Business Standard](../../admin/admin-overview/what-is-microsoft-365-for-business.md) (Office アプリとサービス、Microsoft Teams)</li><li>[共有コンピューターのアクティブ化](/deployoffice/overview-shared-computer-activation) (Microsoft 365 Appsを展開する場合)</li><li>[Windows 10/11 Business](../../business-premium/m365bp-upgrade-windows-10-pro.md) (以前のバージョンの Windows Pro からアップグレード)</li><li>[Windows Autopilot](/mem/autopilot/windows-autopilot) (Windows デバイスのセットアップと構成用)</li><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) (電子メールの改ざん、スパム対策、マルウェア対策、スプーフィング インテリジェンス)</li><li>[Defender for Business](mdb-overview.md) ("Defender for Business (スタンドアロン)" 列に記載されているすべてのもの) </li><li>[Microsoft Defender for Office 365 計画 1](../office-365-security/overview.md) (高度な改ざん、リアルタイム検出、安全な添付ファイル、安全なリンク)</li><li>[自動拡張アーカイブ](../../compliance/autoexpanding-archiving.md) (電子メールの場合)</li><li>[Azure Active Directory Premium プラン 1](/azure/active-directory/fundamentals/active-directory-whatis) (ID 管理)</li><li>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (デバイスのオンボードと管理)</li><li>[Azure Information Protection Premium プラン 1](/azure/information-protection/what-is-information-protection) (機密情報の保護)</li><li>[Azure Virtual Desktop](/azure/virtual-desktop/overview) (クラウド内の一元管理されたセキュリティで保護された仮想マシン)</li></ul> |

(<a id="fna">a</a>) 攻撃面の縮小ルールを変更またはカスタマイズするには、Microsoft Intuneが必要です。 IntuneはMicrosoft 365 Business Premiumに含まれています。

(<a id="fnb">b</a>) iOS および Android デバイスのオンボードにはMicrosoft Intuneが必要です。 「[デバイスを Microsoft Defender for Business にオンボードするデバイスを Microsoft Defender for Business にオンボードする](mdb-onboard-devices.md)」を参照してください。

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Microsoft Defender for Businessを Microsoft Defender for Endpoint プラン 1 および 2 と比較する

Defender for Business は、Defender for Endpoint のエンタープライズ レベルの機能を中小企業に提供します。 次の表では、Defender for Business のセキュリティ機能と、企業向けサービス (Microsoft Defender for Endpoint プラン 1 および 2) を比較します。

|機能/機能|[Defender for Business](mdb-overview.md)<br/>(スタンドアロン)|[Defender for Endpoint プラン 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(エンタープライズのお客様向け) |[Defender for Endpoint プラン 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(エンタープライズのお客様向け) |
|---|---|---|---|
|[集中管理](../defender-endpoint/manage-atp-post-migration.md) |はい <sup>[[1](#fn1)]</sup>|はい|はい|
|[クライアント構成の簡略化](mdb-simplified-configuration.md)|はい|不要|不要|
|[Microsoft Defender 脆弱性の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|はい|不要|はい|
|[攻撃面の減少機能](../defender-endpoint/overview-attack-surface-reduction.md)|はい|はい|はい|
|[次世代の保護](../defender-endpoint/next-generation-protection.md)|はい|はい|はい|
|[エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md)|はい <sup>[[2](#fn2)]</sup>|不要|はい|
|[自動調査および対応](../defender-endpoint/automated-investigations.md)|はい <sup>[[3](#fn3)]</sup>|不要|はい|
|[脅威の捜索](../defender-endpoint/advanced-hunting-overview.md) と 6 か月間のデータ保持 |いいえ <sup>[[4](#fn4)]</sup>|不要|はい|
|[脅威分析](../defender-endpoint/threat-analytics.md)|はい <sup>[[5](#fn5)]</sup>|不要|はい|
|[クロスプラットフォームサポート](../defender-endpoint/minimum-requirements.md) <br/>(Windows、Mac、iOS、Android OS)|はい <sup>[[6](#fn6)]</sup>|はい|はい|
|[Microsoft 脅威エキスパート](../defender-endpoint/microsoft-threat-experts.md)|不要|不要|はい|
|パートナー API|はい|はい|はい|
|[Microsoft 365 Lighthouse統合](../../lighthouse/m365-lighthouse-overview.md) <br/>(顧客テナント間のセキュリティ インシデントを表示する場合)|はい |はい <sup>[[7](#fn7)]</sup>|はい <sup>[[7](#fn7)]</sup>|

(<a id="fn1">1</a>) Microsoft 365 Defender ポータル () または Microsoft エンドポイント マネージャー 管理センター ([https://security.microsoft.com](https://security.microsoft.com)[https://endpoint.microsoft.com](https://endpoint.microsoft.com)) で管理されるMicrosoft Intuneを使用して、デバイスのオンボードと管理を行います。

(<a id="fn2">2</a>) Defender for Business のエンドポイント検出と応答 (EDR) 機能には、動作ベースの検出と次の手動応答アクションが含まれます。 
- ウイルス対策スキャンの実行
- デバイスの分離
- ファイルを停止して検疫する
- ファイルをブロックまたは許可するインジケーターを追加する

(<a id="fn3">3</a>) Defender for Business では、テナント全体の自動調査と応答が既定で有効になります。 自動調査と対応を無効にすると、リアルタイムの保護に影響します。 [高度な機能の設定を確認するを](mdb-configure-security-settings.md#review-settings-for-advanced-features)参照してください。  

(<a id="fn4">4</a>) Defender for Business にはタイムライン ビューがありません。

(<a id="fn5">5</a>) Defender for Business では、脅威分析は中小企業向けに最適化されています。

(<a id="fn6">6</a>) デバイス[をMicrosoft Defender for Businessにオンボードする方法に関する](mdb-onboard-devices.md)Microsoft Defender for Businessを参照してください。

(<a id="fn7">7</a>) Defender for Endpoint を使用してテナント間でインシデントを表示する機能は新しい機能です。

Microsoft [エンドポイント セキュリティ プランの比較](../defender-endpoint/defender-endpoint-plan-1-2.md)も参照してください。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの要件を確認する](mdb-requirements.md)
- [Microsoft Defender for Businessを取得する](get-defender-business.md)
- [Microsoft Defender for Businessを設定して構成する方法について説明します](mdb-setup-configuration.md)
