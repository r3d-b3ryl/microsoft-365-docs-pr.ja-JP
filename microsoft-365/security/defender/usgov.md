---
title: Microsoft 365 Defender for US Government のお客様
description: 利用可能な米国政府機関のお客様の要件と機能に関するMicrosoft 365 Defenderについて説明します
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft 365 Defender, xdr, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: d1fa56bc797a3f651d79ab87f9ade0a9d753849d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482144"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender for US Government のお客様

**適用対象:**
- Microsoft 365 Defender

Azure US Government 環境に組み込まれている米国政府機関のお客様向けのMicrosoft 365 Defenderは、Azure Commercial のMicrosoft 365 Defenderと同じ基盤となるテクノロジを使用します。

このオファリングは GCC、GCC High、DoD のお客様が利用でき、商用バージョンと同じ防止、検出、調査、修復に基づいています。 ただし、このオファリングの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> Defender for Cloud Apps、Defender for Endpoint、または Defender for Identity を商用で使用している GCC のお客様は、GCC の対象となる GCC バージョンにこれらのサービスを移行する必要Microsoft 365 Defender。

## <a name="licensing-requirements"></a>ライセンスの要件

米国政府機関のお客様向けのMicrosoft 365 Defenderには、次のいずれかの Microsoft ボリューム ライセンス オファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|GCC High のMicrosoft 365 E5|DOD 用 Microsoft 365 G5|
|Microsoft 365 G5 セキュリティ GCC|Microsoft 365 G5 Security for GCC High|Microsoft 365 G5 Security for DOD|
|Enterprise Mobility + Security G5 GCC|GCC High の E5 Enterprise Mobility + Security|DOD の E5 Enterprise Mobility + Security|
|Office 365 G5 GCC|GCC High のOffice 365 E5|DOD のOffice 365 E5|
|gcc のMicrosoft Defender for Cloud Apps|GCC High のMicrosoft Defender for Cloud Apps|DOD のMicrosoft Defender for Cloud Apps|
|Microsoft Defender for Endpoint - GCC|GCC High のMicrosoft Defender for Endpoint|DOD のMicrosoft Defender for Endpoint|
|Microsoft Defender for Identity - GCC|GCC High のMicrosoft Defender for Identity|DOD のMicrosoft Defender for Identity|
|Microsoft Defender for Office 365 (プラン 2) GCC|GCC High のMicrosoft Defender for Office 365 (プラン 2)|DOD のMicrosoft Defender for Office 365 (プラン 2)|
|Windows 10 Enterprise E5 GCC|WINDOWS 10 ENTERPRISE E5 for GCC High|DOD の E5 のWindows 10 Enterprise|
|

### <a name="server-licensing"></a>サーバー ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender for Endpoint サーバー GCC|Microsoft Defender for Endpoint サーバー for GCC High|MICROSOFT DEFENDER FOR ENDPOINT サーバー for DOD|
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
> GCC の顧客であり、Microsoft Defender for Endpointコマーシャルから GCC に移行する過程にある場合は、Microsoft Defender for Endpoint商用データにアクセスするために使用https://transition.security.microsoft.comします。

## <a name="api"></a>API

[API ドキュメント](api-overview.md)に記載されているパブリック URI の代わりに、次の URI を使用する必要があります。

<br />

****

|エンドポイントの種類|GCC|GCC High & DoD|
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
|統合: Microsoft Sentinel (インシデント&未加工データ)|![はい](../defender-endpoint/images/svg/check-yes.svg) パブリック プレビュー段階|![はい](../defender-endpoint/images/svg/check-yes.svg) パブリック プレビュー段階|![はい](../defender-endpoint/images/svg/check-yes.svg) パブリック プレビュー段階|
|Microsoft 脅威エキスパート|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|

Event Streaming API テーブルの詳細な一覧については、Event Streaming API [でサポートされているストリーミング イベントの種類Microsoft 365 Defenderを](supported-event-types.md)参照してください。

## <a name="more-details"></a>詳細情報

詳細については、個々のワークロードの US Gov ページを参照してください。

- [Microsoft Defender for Cloud Apps](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description)。
- [Microsoft Defender for Identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description)。
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/gov)。
