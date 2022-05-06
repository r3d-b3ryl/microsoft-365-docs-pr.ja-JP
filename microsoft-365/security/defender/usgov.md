---
title: Microsoft 365 Defender for US Government のお客様
description: 利用可能な米国政府機関のお客様の要件と機能に関するMicrosoft 365 Defenderについて説明します
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft 365 Defender, xdr, dod
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3e8f6e523a5483de99beb0af7d01ab96951b7a3e
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375336"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender for US Government のお客様

**適用対象:**
- Microsoft 365 Defender

Azure US Government 環境に組み込まれている米国政府機関のお客様向けのMicrosoft 365 Defenderは、Azure Commercial のMicrosoft 365 Defenderと同じ基盤となるテクノロジを使用します。

このオファリングは、GCC、GCC High、DoD のお客様が利用でき、商用バージョンと同じ防止、検出、調査、修復に基づいています。 ただし、このオファリングの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> Defender for Cloud Apps、Defender for Endpoint、または Defender for Identity in Commercial を使用しているGCCのお客様は、Microsoft 365 Defender GCCの対象となるサービスをGCCバージョンに移行する必要があります。

## <a name="licensing-requirements"></a>ライセンスの要件

米国政府機関のお客様向けのMicrosoft 365 Defenderには、次のいずれかの Microsoft ボリューム ライセンス オファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|GCC High のMicrosoft 365 E5|MICROSOFT 365 G5 for DOD|
|Microsoft 365 G5 セキュリティ GCC|Microsoft 365 G5 Security for GCC High|MICROSOFT 365 G5 Security for DOD|
|Enterprise Mobility + Security G5 GCC|GCC High のEnterprise Mobility + Security E5|DOD の E5 Enterprise Mobility + Security|
|Office 365 G5 GCC|GCC High のOffice 365 E5|DOD のOffice 365 E5|
|Microsoft Defender for Cloud Apps GCC|GCC High のMicrosoft Defender for Cloud Apps|DOD のMicrosoft Defender for Cloud Apps|
|Microsoft Defender for Endpoint - GCC|GCC High のMicrosoft Defender for Endpoint|DOD のMicrosoft Defender for Endpoint|
|Microsoft Defender for Identity - GCC|GCC High のMicrosoft Defender for Identity|DOD のMicrosoft Defender for Identity|
|Microsoft Defender for Office 365 (プラン 2) GCC|GCC High のMicrosoft Defender for Office 365 (プラン 2)|DOD のMicrosoft Defender for Office 365 (プラン 2)|
|E5 GCCをWindows 10 Enterpriseする|Windows 10 Enterprise E5 for GCC High|DOD の E5 のWindows 10 Enterprise|
|

### <a name="server-licensing"></a>サーバー ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender for Endpoint サーバー GCC|GCC High 用Microsoft Defender for Endpoint サーバー|MICROSOFT DEFENDER FOR ENDPOINT サーバー for DOD|
|Microsoft Defender for servers|Microsoft Defender for servers - Government|Microsoft Defender for servers - Government|
|

## <a name="portal-urls"></a>ポータル URL

米国政府機関のお客様向けのMicrosoft 365 Defender ポータル URL を次に示します。

<br />

****

|お客様の種類|ポータル URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|ロール アウト|
|DoD|ロール アウト|
|
> [!NOTE]
> GCC顧客であり、Microsoft Defender for EndpointコマーシャルからGCCに移行する過程にある場合は、Microsoft Defender for Endpoint商用データにアクセスするために使用https://transition.security.microsoft.comします。

## <a name="api"></a>API

[API ドキュメント](api-overview.md)に記載されているパブリック URI の代わりに、次の URI を使用する必要があります。

<br />

****

|エンドポイントの種類|GCC|GCC 高& DoD|
|---|---|---|
|ログイン|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Microsoft 365 Defender API|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>商用の機能パリティ

米国政府機関のお客様向けのMicrosoft 365 Defenderは、商用サービスと完全な同等性を持っていません。 私たちの目標は、すべての商用機能と機能を米国政府機関のお客様に提供することですが、まだ利用できない機能がいくつかあります。

既知のギャップは次のとおりです。

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|統合: Microsoft Sentinel (インシデント&未加工データ)|![はい](../defender-endpoint/images/svg/check-yes.svg)|![はい](../defender-endpoint/images/svg/check-yes.svg) プライベート プレビュー|![はい](../defender-endpoint/images/svg/check-yes.svg) プライベート プレビュー|
|Microsoft 脅威エキスパート|![いいえ](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![いいえ](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![いいえ](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|

## <a name="more-details"></a>詳細情報

詳細については、個々のワークロードの US Gov ページを参照してください。
- [Microsoft Defender for Cloud Apps](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description)。
- [Microsoft Defender for Identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description)。
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/gov)。
