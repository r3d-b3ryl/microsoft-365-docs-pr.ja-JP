---
title: Microsoft 365 Defender米国政府機関のお客様向けサービス
description: 利用可能な米国政府機関Microsoft 365 Defenderの要件と機能に関する詳細
keywords: government, gcc, high, requirements, capabilitis, defender, Microsoft 365 Defender, xdr, dod
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
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender米国政府機関のお客様向けサービス

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender米国政府機関環境に組み込む米国政府機関のお客様は、Azure Commercial と同じ基になるテクノロジMicrosoft 365 Defender使用します。

この製品は、GCC、GCC High、DoD のお客様に提供され、商用バージョンと同じ予防、検出、調査、修復に基づいて提供されます。 ただし、このサービスの機能の可用性にはいくつかの違いがあります。

> [!NOTE]
> Defender for Cloud Apps、Defender for Endpoint、または Defender for Identity in Commercial を使用している GCC のお客様は、これらのサービスを GCC バージョンに移行して、Microsoft 365 Defender GCC の対象となる必要があります。

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft 365 Defenderのお客様には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。

### <a name="desktop-licensing"></a>デスクトップ ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5 High GCCの場合|Microsoft 365 G5 for DOD|
|Microsoft 365 G5 セキュリティ GCC|Microsoft 365 G5 Security for GCC High|Microsoft 365 G5 Security for DOD|
|Enterprise Mobility + Security G5 GCC|Enterprise Mobility + Security E5 for GCC High|Enterprise Mobility + Security E5 for DOD|
|Office 365 G5 GCC|Office 365 E5 High のGCC|Office 365 E5 DOD の場合|
|Microsoft Defender for Cloud Apps GCC|Microsoft Defender for Cloud Apps for GCC High|Microsoft Defender for Cloud Apps for DOD|
|Microsoft Defender for Endpoint - GCC|Microsoft Defender for Endpoint for GCC High|Microsoft Defender for Endpoint for DOD|
|Microsoft Defender for Identity - GCC|Microsoft Defender for Identity for GCC High|Microsoft Defender for Identity for DOD|
|Microsoft Defender for Office 365 (プラン 2) GCC|Microsoft Defender for Office 365 (プラン 2) for GCC High|Microsoft Defender for Office 365 (プラン 2) for DOD|
|Windows 10 Enterprise E5 GCC|Windows 10 Enterprise E5 for GCC High|Windows 10 Enterprise E5 for DOD|
|

### <a name="server-licensing"></a>サーバー ライセンス

<br />

****

|GCC|GCC High|DoD|
|---|---|---|
|Microsoft Defender for Endpoint Server GCC|Microsoft Defender for Endpoint Server for GCC High|Microsoft Defender for Endpoint Server for DOD|
|サーバー用 Microsoft Defender|Microsoft Defender for servers - Government|Microsoft Defender for servers - Government|
|

## <a name="portal-urls"></a>ポータル URL

米国政府機関のお客様向Microsoft 365 Defenderポータル URL を次に示します。

<br />

****

|お客様の種類|ポータル URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC High|ロール アウト|
|DoD|ロール アウト|
|
> [!NOTE]
> Microsoft Defender for Endpoint GCC商用から GCC への移行中の顧客である場合は、Microsoft Defender for Endpoint 商用データに https://transition.security.microsoft.com アクセスするために使用します。

## <a name="api"></a>API

API ドキュメントに記載されているパブリック URI の代わりに、次の [URI](api-overview.md)を使用する必要があります。

<br />

****

|エンドポイントの種類|GCC|GCC高& DoD|
|---|---|---|
|ログイン|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Microsoft 365 Defender API|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>商用機能と機能のパリティ

Microsoft 365 Defenderのお客様向け製品は、商用サービスと完全に同一性を持つ必要があります。 すべての商用機能と機能を米国政府機関のお客様に提供しますが、まだ利用できない機能がいくつか用意されています。

既知のギャップは次のとおりです。

<br />

****

|フィーチャー名|GCC|GCC High|DoD|
|---|:---:|:---:|:---:|
|統合: Microsoft Sentinel (インシデント&生データ)|![はい](../defender-endpoint/images/svg/check-yes.svg)|![はい](../defender-endpoint/images/svg/check-yes.svg) プライベート プレビューで|![はい](../defender-endpoint/images/svg/check-yes.svg) プライベート プレビューで|
|Microsoft 脅威エキスパート|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|![不要](../defender-endpoint/images/svg/check-no.svg) エンジニアリング バックログについて|

## <a name="more-details"></a>詳細情報

詳細については、「US Gov ページの個々のワークロード」を参照してください。
- [Microsoft Defender for Cloud Apps .](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description)
- [Microsoft Defender for Identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description).
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/gov).
