---
title: 中小企業向けのMicrosoft 365プランのセキュリティ機能を比較する
description: Defender for Business と Defender for Endpoint の違いを理解する。 各プランに含まれる内容を把握すると、会社の情報に基づいた決定を下すのに役立ちます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.date: 04/18/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: e32018f52f3a45624fcf07ae03e44c662a594297
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64916317"
---
# <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Microsoft Defender for BusinessをMicrosoft 365 Business Premiumと比較する

> [!IMPORTANT]
> Microsoft Defender for Businessは、2022 年 3 月 1 日以降、[Microsoft 365 Business Premium](../../business-premium/index.md)のお客様に展開されます。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー段階にあり、 [ここでサインアップ](https://aka.ms/mdb-preview) して要求する顧客と IT パートナーに段階的にロールアウトされます。 プレビューには [シナリオの初期セット](mdb-tutorials.md#try-these-preview-scenarios)が含まれており、定期的に機能を追加します。
>
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。

Microsoft では、中小企業向けのさまざまなプランを含め、さまざまなクラウド ソリューションとサービスを提供しています。 たとえば、[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)には、セキュリティとデバイス管理機能と、Office アプリなどの生産性機能が含まれます。 この記事は、デバイス保護などのセキュリティ機能がMicrosoft 365 Business Premium、Microsoft Defender for Business、Microsoft Defender for Endpointに含まれているセキュリティ機能を明確にするために設計されています。

Microsoft Defender for Businessは、スタンドアロン オファリングとして、またはMicrosoft 365 Business Premiumの一部として使用できます (2022 年 3 月 1 日以降)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

**この記事を使用して、次の操作を行います**。

- [Microsoft Defender for Business (スタンドアロン) と Microsoft 365 Business Premiumの比較](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)
- [Defender for Business (スタンドアロン) をMicrosoft Defender for Endpointエンタープライズ オファリングと比較する](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)

**Microsoft Defender for Businessを購入して使用するために、Microsoft 365 サブスクリプションを持っている必要はありません。** Microsoft Defender for BusinessはMicrosoft 365 Business Premiumに含まれており、中小企業向けのスタンドアロン セキュリティ ソリューションとして利用できます。 Microsoft 365 Business Basicまたは Standard が既にある場合は、Microsoft 365 Business Premiumにアップグレードするか、Microsoft Defender for Businessを追加して脅威保護機能を強化することを検討してください。

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Microsoft Defender for Businessのセキュリティ機能をMicrosoft 365 Business Premiumと比較する

> [!NOTE]
> この記事は、Microsoft Defender for Business (スタンドアロン プラン) およびMicrosoft 365 Business Premium (Defender for Business を含む) に含まれる脅威保護機能の概要を提供することを目的としています。 この記事は、サービスの説明またはライセンス契約ドキュメントとして機能することを意図していません。 詳細については、[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンスに関するページを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください

**2022 年 3 月 1 日以降、Defender for Business はMicrosoft 365 Business Premiumの一部としてロールアウトを開始します。スタンドアロン オファリングとしての Defender for Business はまだプレビュー段階です。**

次の表では、Defender for Business (スタンドアロン) のセキュリティ機能とMicrosoft 365 Business Premiumを比較します。

|機能/機能|[Microsoft Defender for Business](mdb-overview.md)<br/>(スタンドアロン、現在プレビュー段階)|[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)<br/>(Defender for Business を含む)|
|---|---|---|
|電子メール保護|はい <br/>- [Microsoft Defender ウイルス対策を使用した電子メール スキャン](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|はい <br/>- [Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) <br/>- [Microsoft Defender ウイルス対策を使用した電子メール スキャン](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スパム対策の保護|はい <br/>- デバイスの場合|はい <br/>- デバイスの場合<br/>- Microsoft 365メール コンテンツ (メッセージや添付ファイルなど) の場合|
|マルウェア対策保護|はい<br/>- デバイスの場合|はい <br/>- デバイスの場合<br/>- Microsoft 365メール コンテンツ (メッセージや添付ファイルなど) の場合|
|[次世代の保護](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (ウイルス対策とマルウェア対策の保護)|はい<br/>- Microsoft Defender ウイルス対策はWindows 10以降に含まれます|はい <br/>- Microsoft Defender ウイルス対策はWindows 10以降に含まれます<br/>- オンボードされたデバイスの次世代保護ポリシー|
|[攻撃面の減少](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(Windows 10 以降の ASR 規則とファイアウォール保護)|はい|はい|
|[エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md) <br/>(動作ベースの検出アクションと手動応答アクション)|はい|はい|
|[自動調査および対応](../defender-endpoint/automated-investigations.md)|はい|はい|
|[脅威と脆弱性の管理](../defender-endpoint/tvm-dashboard-insights.md)|はい|はい|
|一元管理とレポート|はい|はい|
|[API](../defender-endpoint/apis-intro.md) <br/>(カスタム アプリまたはレポート ソリューションとの統合用)|はい|はい|

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Microsoft Defender for Businessを Microsoft Defender for Endpoint プラン 1 および 2 と比較する

Defender for Business は、Defender for Endpoint のエンタープライズ レベルの機能を中小企業に提供します。

次の表では、Defender for Business のセキュリティ機能と、企業向けサービス (Microsoft Defender for Endpoint プラン 1 および 2) を比較します。

|機能/機能|[Defender for Business](mdb-overview.md)<br/>(スタンドアロン、現在プレビュー段階)|[Defender for Endpoint プラン 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(エンタープライズのお客様向け) |[Defender for Endpoint プラン 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(エンタープライズのお客様向け) |
|---|---|---|---|
|[集中管理](../defender-endpoint/manage-atp-post-migration.md) |はい <sup>[[1](#fn1)]</sup>|はい|はい|
|[クライアント構成の簡略化](mdb-simplified-configuration.md)|はい|いいえ|いいえ|
|[脅威と脆弱性の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|はい|いいえ|はい|
|[攻撃面の縮小機能](../defender-endpoint/overview-attack-surface-reduction.md)|はい|はい|はい|
|[次世代の保護](../defender-endpoint/next-generation-protection.md)|はい|はい|はい|
|[エンドポイントでの検出と対応](../defender-endpoint/overview-endpoint-detection-response.md)|はい <sup>[[2](#fn2)]</sup>|いいえ|はい|
|[自動調査および対応](../defender-endpoint/automated-investigations.md)|はい <sup>[[3](#fn3)]</sup>|いいえ|はい|
|[脅威の捜索](../defender-endpoint/advanced-hunting-overview.md) と 6 か月間のデータ保持 |いいえ <sup>[[4](#fn4)]</sup>|いいえ|はい|
|[脅威分析](../defender-endpoint/threat-analytics.md)|はい <sup>[[5](#fn5)]</sup>|いいえ|はい|
|[クロスプラットフォームサポート](../defender-endpoint/minimum-requirements.md) <br/>(Windows、macOS、iOS、Android OS)|はい <sup>[[6](#fn6)]</sup>|はい|はい|
|[Microsoft 脅威エキスパート](../defender-endpoint/microsoft-threat-experts.md)|いいえ|いいえ|はい|
|パートナー API|はい|はい|はい|
|[Microsoft 365 Lighthouse統合](../../lighthouse/m365-lighthouse-overview.md) <br/>(顧客テナント間のセキュリティ インシデントを表示する場合)|はい|いいえ|いいえ|

(<a id="fn1">1</a>) Microsoft 365 Defender ポータル () または Microsoft エンドポイント マネージャー ([https://security.microsoft.com](https://security.microsoft.com)[https://endpoint.microsoft.com](https://endpoint.microsoft.com)) でデバイスをオンボードおよび管理します。

(<a id="fn2">2</a>) Defender for Business のエンドポイント検出と応答 (EDR) 機能には、動作ベースの検出と次の 4 種類の手動応答アクションが含まれます。 
- ウイルス対策スキャンの実行
- デバイスの分離
- ファイルを停止して検疫する
- ファイルをブロックまたは許可するインジケーターを追加する

(<a id="fn3">3</a>) Defender for Business では、テナント全体の自動調査と応答が既定で有効になります。 自動調査と対応を無効にすると、リアルタイムの保護に影響します。 [高度な機能の設定を確認するを](mdb-configure-security-settings.md#review-settings-for-advanced-features)参照してください。  

(<a id="fn4">4</a>) Defender for Business にはタイムライン ビューがありません。

(<a id="fn5">5</a>) Defender for Business では、脅威分析は中小企業向けに最適化されています。

(<a id="fn6">6</a>) プレビュー プログラム中は、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) でWindowsクライアント デバイスのオンボードがサポートされます。 ローカル スクリプト メソッドを使用できます。 [「Microsoft Defender for Businessにデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの要件を確認する](mdb-requirements.md)
- [Microsoft Defender for Businessを取得する](get-defender-business.md)
- [Microsoft Defender for Businessを設定して構成する方法について説明します](mdb-setup-configuration.md)
