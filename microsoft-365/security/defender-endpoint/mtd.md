---
title: Microsoft Defender for Endpoint - Mobile Threat Defense
ms.reviewer: ''
description: Microsoft Defender for Endpoint でのモバイル脅威防御の概要
keywords: モバイル, Defender, Microsoft Defender for Endpoint, ios, mtd, android, security
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce5d8fcf693b6586c134b8fe2381d3881e68d9d3
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767608"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender for Endpoint - Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint on Android and iOS は、モバイル **脅威防御ソリューション (MTD) です**。 通常、会社は PC を脆弱性や攻撃から保護することには積極的ですが、一方で、モバイル デバイスは多くの場合、監視や保護のない状態が続きます。 モバイル プラットフォームにアプリの分離や消費者向けアプリ ストアなどの組み込みの保護が組み込みされている場合、これらのプラットフォームは Web ベースまたは他の高度な攻撃に対して脆弱なままです。 従業員が仕事用にデバイスを使用し、機密情報にアクセスする場合、企業は MTD ソリューションを展開して、デバイスとリソースをモバイルでのますます高度な攻撃から保護する必要があります。

## <a name="key-capabilities"></a>主な機能

Android および iOS のエンドポイント向け Microsoft Defender には、以下の主要な機能が提供されています。最新の機能と利点については、お知らせをご [覧ください](https://aka.ms/mdeblog)。

<br>

|機能|説明|
|---|---|
|Web 保護|フィッシング対策、安全でないネットワーク接続のブロック、カスタム インジケーターのサポート。|
|マルウェア保護 (Android のみ)|悪意のあるアプリのスキャン。|
|脱獄検出 (iOS 専用)|脱獄されたデバイスの検出。|
|脅威と脆弱性の管理 (TVM) |オンボードモバイル デバイスの脆弱性評価。 Microsoft Defender for [Endpoint 脅威と脆弱性の管理詳細](next-gen-threat-and-vuln-mgt.md)については、このページをご覧ください。 *iOS では、このプレビューでは OS の脆弱性だけがサポートされています。*|
|統合アラート|統合 M365 セキュリティ コンソールのすべてのプラットフォームからのアラート|
|条件付きアクセス、条件付き起動|リスクの高いデバイスによる企業リソースへのアクセスをブロックする。 エンドポイントリスク信号の Defender をアプリ保護ポリシー (MAM) に追加することもできます。|
|プライバシーコントロール。 プレビューで (以下のメモを参照)|Microsoft Defender for Endpoint から送信されるデータを制御して、脅威レポートのプライバシーを構成します。 *プライバシーコントロールは現在、登録済みデバイスでのみ使用できます。登録されていないデバイスのコントロールは後で追加されます*|
|アプリケーションとのMicrosoft Tunnel|VPN ゲートウェイ Microsoft Tunnelと統合して、1 つのアプリでセキュリティと接続を有効にできます。 現在 Android でのみ利用可能|

これらすべての機能は、Microsoft Defender for Endpoint ライセンスホルダーで使用できます。 詳細については、「ライセンス要件 [」を参照してください](minimum-requirements.md#licensing-requirements)。


## <a name="overview-and-deploy"></a>概要と展開

モバイルでの Microsoft Defender for Endpoint の展開は、MEM (Microsoft エンドポイント マネージャーを介して実行できます。 MTD の機能と展開の概要については、次のビデオをご覧ください。

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>展開

次の表に、Android と iOS に Microsoft Defender for Endpoint を展開する方法を示します。 詳細なドキュメントについては、次を参照してください。 
- [Android 上のエンドポイント用 Microsoft Defender の概要](microsoft-defender-endpoint-android.md)、および
- [iOS 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-ios.md)

**Android**

|登録の種類     |詳細      |
|--------------------|-------------|
|Android Enterprise Intune Unified エンドポイント マネージャー (Microsoft エンドポイント マネージャー)|[登録済みデバイスEnterprise Android に展開する](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|Intune Unified エンドポイント マネージャー (Microsoft エンドポイント マネージャー) のデバイス管理者|[デバイス管理者が登録したデバイスに展開する](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|他の統合エンドポイント マネージャーによって管理される管理されていない BYOD またはデバイス / セットアップ アプリ保護ポリシー (MAM)|[アプリ保護ポリシー (MAM) で Defender リスクシグナルを構成する](android-configure-mam.md)|

**iOS**

|登録の種類     |詳細      |
|--------------------|-------------|
|Intune Unified エンドポイント マネージャー の監視Microsoft エンドポイント マネージャー)|1. [iOS ストア アプリとして展開する](ios-install.md)<br/>2. [監視対象の iOS デバイス用に VPN を使用せずに Web 保護をセットアップする](ios-install.md#complete-deployment-for-supervised-devices)|
|Intune UEM に登録されている未発行 (BYOD) デバイス (Microsoft エンドポイント マネージャー)|[iOS ストア アプリとして展開する](ios-install.md)|
|他の UEM によって管理される管理されていない BYOD またはデバイス / セットアップ アプリ保護ポリシー (MAM)|[アプリ保護ポリシー (MAM) で Defender リスクシグナルを構成する](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>エンド ユーザーのオンボーディング

- [iOS](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) 登録済みデバイス用にゼロタッチオンボードを構成する: 管理者は、ユーザーにアプリを開かなくても、登録された iOS デバイスで Microsoft Defender for Endpoint をサイレント オンボードするゼロタッチ インストールを構成できます。 

- [条件付きアクセスを](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)構成してユーザーオンボーディングを強制する: これは、展開後にエンド ユーザーが Microsoft Defender for Endpoint アプリにオンボードされるのを確認するために適用できます。 Defender for Endpoint リスクシグナルを使用した条件付きアクセスの構成に関する簡単なデモについては、このビデオをご覧ください。 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>オンボードを簡略化する

- [iOS - Zero-Touchオンボード](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview)
- [Android Enterprise - セットアップ Always-on VPN](android-intune.md#auto-setup-of-always-on-vpn)。
- [iOS - VPN プロファイルの自動セットアップ](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>パイロット評価

Microsoft Defender for Endpoint を使用してモバイル脅威防御を評価する場合は、サービスを大規模なデバイスセットに展開する前に、特定の条件が満たされたと確認できます。 広く展開する前に、終了条件を定義し、満たされた条件を確認できます。

これにより、サービスの展開中に発生する可能性のある潜在的な問題を減らすのに役立ちます。 役立つ可能性があるテストと終了条件を次に示します。

- デバイスがデバイス インベントリ リストに表示されます。モバイル デバイス上の Defender for Endpoint のオンボーディングが正常に完了したら、セキュリティ コンソールのデバイス インベントリにデバイスが一覧表示されたことを [確認します](https://security.microsoft.com)。

- Android デバイスでマルウェア検出テストを実行する: Google play ストアからテスト ウイルス アプリをインストールし、Microsoft Defender for Endpoint によって検出されるのを確認します。 このテストで使用できるアプリの例を次に示します。ウイルス [のテスト](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus)です。 Android の場合、Enterpriseプロファイルだけがサポートされます。

- フィッシング テストを実行する: Microsoft https://smartscreentestratings2.net Defender for Endpoint によってブロックされるのを参照して確認します。 Android の場合、Enterpriseプロファイルだけがサポートされます。

- ダッシュボードにアラートが表示される: 上記の検出テストのアラートがセキュリティ コンソールに [表示されるのを確認します](https://security.microsoft.com)。

## <a name="configure"></a>Configure

- [Android の機能を構成する](android-configure.md)
- [iOS 機能の構成](ios-configure-features.md)
- [監視対象の iOS デバイス用に VPN なしで Web 保護を構成する](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>リソース

- [Android 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md)
- [iOS 用 Microsoft Defender for Endpoint API](microsoft-defender-endpoint-ios.md)
- 今後のリリースについては、お知らせをご [覧ください](https://aka.ms/mdeblog)。

