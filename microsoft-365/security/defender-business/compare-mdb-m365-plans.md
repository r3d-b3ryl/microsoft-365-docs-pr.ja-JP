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
ms.openlocfilehash: be57910a1f6b2387a1b826e6cff17e418ec3da2b
ms.sourcegitcommit: 5463d4518c269d9c125bb66836a780df292b4854
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66795380"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>中小企業向けの Microsoft 365 プランのセキュリティ機能を比較する

Microsoft では、中小企業向けの計画など、さまざまなクラウド ソリューションとサービスを提供しています。 たとえば、[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)には、Office アプリなどの生産性機能と共に、セキュリティとデバイス管理機能が含まれます。 この記事では、Microsoft 365 Business Premium、Microsoft Defender for Business、[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)のセキュリティ機能について説明します。


**この記事を使用して、次の操作を行います**。

- [Defender for Business (スタンドアロン) をMicrosoft 365 Business Premiumと比較します](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)。
- [Defender for Business (スタンドアロン) と Defender for Endpoint エンタープライズ オファリングを比較します](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)。

> [!TIP]
> Defender for Business は、中小企業向けのスタンドアロン セキュリティ ソリューションとして利用できます。 Microsoft 365 Business Premiumにも含まれています。 Microsoft 365 Business Basicまたは Standard が既にある場合は、Microsoft 365 Business Premiumにアップグレードするか、サブスクリプションに Defender for Business を追加して、デバイスの脅威保護機能を強化することを検討してください。

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Microsoft Defender for Businessのセキュリティ機能をMicrosoft 365 Business Premiumと比較する

> [!NOTE]
> この記事では、Microsoft Defender for Business (スタンドアロン プラン) とMicrosoft 365 Business Premium (Defender for Business を含む) に含まれる脅威保護機能の概要について説明します。 サービスの説明やライセンス契約のドキュメントを意図したものではありません。 詳細については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

Defender for Business はスタンドアロン サブスクリプションとしても利用でき、Microsoft 365 Business Premiumにも含まれています。 次の表では、Defender for Business (スタンドアロン) のセキュリティ機能とMicrosoft 365 Business Premiumを比較します。

|機能/機能|[Microsoft Defender for Business](mdb-overview.md)<br/>(スタンドアロン)|[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)<br/>(Defender for Business を含む)|
|---|---|---|
|Email保護|はい <br/>[Microsoft Defender ウイルス対策を使用したEmailスキャン](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|はい <ul><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)</li><li>[Microsoft Defender ウイルス対策を使用したEmailスキャン](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)</li></ul>|
|スパム対策保護|はい<br/>デバイスの場合|はい <ul><li>デバイスの場合</li><li>Microsoft 365 メール コンテンツ (メッセージや添付ファイルなど) の場合</li></ul>|
|マルウェア対策保護|はい<br/>デバイスの場合|はい<ul><li>デバイスの場合</li><li>Microsoft 365 メール コンテンツ (メッセージや添付ファイルなど) の場合</li></ul>|
|[次世代の保護](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (オンボードデバイスのウイルス対策とマルウェア対策の保護)|はい |はい |
|[攻撃面の減少](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(Windows 10 以降の ASR 規則とファイアウォール保護)|はい|はい|
|[エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md) <br/>(動作ベースの検出アクションと手動応答アクション)|はい|はい|
|[自動調査および対応](../defender-endpoint/automated-investigations.md)|はい|はい|
|[脅威と脆弱性の管理](../defender-endpoint/tvm-dashboard-insights.md)|はい|はい|
|一元管理とレポート|はい|はい|
|[API](../defender-endpoint/apis-intro.md) <br/>(カスタム アプリまたはレポート ソリューションとの統合用)|はい|はい|

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Microsoft Defender for Businessを Microsoft Defender for Endpoint プラン 1 および 2 と比較する

Defender for Business は、Defender for Endpoint のエンタープライズ レベルの機能を中小企業に提供します。 次の表では、Defender for Business のセキュリティ機能と、企業向けサービス (Microsoft Defender for Endpoint プラン 1 および 2) を比較します。

|機能/機能|[Defender for Business](mdb-overview.md)<br/>(スタンドアロン)|[Defender for Endpoint プラン 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(エンタープライズのお客様向け) |[Defender for Endpoint プラン 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(エンタープライズのお客様向け) |
|---|---|---|---|
|[集中管理](../defender-endpoint/manage-atp-post-migration.md) |はい <sup>[[1](#fn1)]</sup>|はい|はい|
|[クライアント構成の簡略化](mdb-simplified-configuration.md)|はい|いいえ|いいえ|
|[脅威と脆弱性の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|はい|いいえ|はい|
|[攻撃面の減少機能](../defender-endpoint/overview-attack-surface-reduction.md)|はい|はい|はい|
|[次世代の保護](../defender-endpoint/next-generation-protection.md)|はい|はい|はい|
|[エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md)|はい <sup>[[2](#fn2)]</sup>|いいえ|はい|
|[自動調査および対応](../defender-endpoint/automated-investigations.md)|はい <sup>[[3](#fn3)]</sup>|いいえ|はい|
|[脅威の捜索](../defender-endpoint/advanced-hunting-overview.md) と 6 か月間のデータ保持 |いいえ <sup>[[4](#fn4)]</sup>|いいえ|はい|
|[脅威の分析](../defender-endpoint/threat-analytics.md)|はい <sup>[[5](#fn5)]</sup>|いいえ|はい|
|[クロスプラットフォームサポート](../defender-endpoint/minimum-requirements.md) <br/>(Windows、Mac、iOS、Android OS)|はい <sup>[[6](#fn6)]</sup>|はい|はい|
|[Microsoft 脅威エキスパート](../defender-endpoint/microsoft-threat-experts.md)|いいえ|いいえ|はい|
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

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの要件を確認する](mdb-requirements.md)
- [Microsoft Defender for Businessを取得する](get-defender-business.md)
- [Microsoft Defender for Businessを設定して構成する方法について説明します](mdb-setup-configuration.md)
