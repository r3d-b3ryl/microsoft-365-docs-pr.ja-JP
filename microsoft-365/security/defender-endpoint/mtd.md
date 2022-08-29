---
title: Microsoft Defender for Endpoint - Mobile Threat Defense
ms.reviewer: ''
description: Microsoft Defender for Endpointでの Mobile Threat Defense の概要
keywords: mobile, defender, Microsoft Defender for Endpoint, ios, mtd, android, security
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
ms.openlocfilehash: f02dc28eb3204922386d0fae26bc1191779641e6
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327203"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender for Endpoint - Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android と iOS のMicrosoft Defender for Endpointは、**モバイル脅威防御ソリューション (MTD) です**。 通常、会社は PC を脆弱性や攻撃から保護することには積極的ですが、一方で、モバイル デバイスは多くの場合、監視や保護のない状態が続きます。 モバイル プラットフォームにアプリの分離や消費者向けアプリ ストアの審査などの保護が組み込まれている場合、これらのプラットフォームは Web ベースやその他の高度な攻撃に対して脆弱なままです。 より多くの従業員が仕事のためにデバイスを使用し、機密情報にアクセスするにつれて、企業は、モバイルに対するますます高度な攻撃からデバイスとリソースを保護するための MTD ソリューションを展開することが不可欠です。

## <a name="key-capabilities"></a>主な機能

Android と iOS のMicrosoft Defender for Endpointには、次の主な機能が用意されています。最新の機能と利点については、お[知らせをお読みください](https://aka.ms/mdeblog)。

<br>

|機能|説明|
|---|---|
|Web Protection|フィッシング対策、安全でないネットワーク接続のブロック、カスタム インジケーターのサポート。|
|Malware Protection (Android のみ)|悪意のあるアプリのスキャン。|
|脱獄検出 (iOS のみ)|脱獄されたデバイスの検出。|
|Microsoft Defender 脆弱性の管理 (MDVM) |オンボードされたモバイル デバイスの脆弱性評価。 Microsoft Defender for EndpointのMicrosoft Defender 脆弱性の管理の詳細については、この[ページ](next-gen-threat-and-vuln-mgt.md)を参照してください。 *iOS では、このプレビューでは OS の脆弱性のみがサポートされることに注意してください。*|
|Network Protection *(パブリック プレビュー)*| 悪意のあるWi-Fi関連する脅威と不正な証明書に対する保護。Intuneのルート CA 証明書とプライベート ルート CA 証明書の一覧を許可する機能。エンドポイントとの信頼を確立できます。|
|統合アラート|統合された M365 セキュリティ コンソール内のすべてのプラットフォームからのアラート|
|条件付きアクセス、条件付き起動|リスクの高いデバイスが企業リソースにアクセスするのをブロックする。 Defender for Endpoint リスクシグナルをアプリ保護ポリシー (MAM) に追加することもできます|
|プライバシーコントロール。 プレビュー段階 (以下の注を参照)|Microsoft Defender for Endpointから送信されたデータを制御して、脅威レポートのプライバシーを構成します。 *プライバシー制御は現在、登録済みデバイスでのみ使用できます。登録されていないデバイスのコントロールは後で追加されます*|
|Microsoft Tunnel との統合|1 つのアプリでセキュリティと接続を有効にする VPN ゲートウェイ ソリューションである Microsoft Tunnel と統合できます。 Android で使用できるようになり、iOS でも一般公開されるようになりました。|

これらの機能はすべて、Microsoft Defender for Endpointライセンス所有者が利用できます。 詳細については、「 [ライセンス要件」を](minimum-requirements.md#licensing-requirements)参照してください。


## <a name="overview-and-deploy"></a>概要とデプロイ

モバイルでのMicrosoft Defender for Endpointの展開は、Microsoft エンドポイント マネージャー (MEM) を使用して行うことができます。 MTD の機能とデプロイの概要については、次のビデオをご覧ください。

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>展開

次の表は、Android と iOS にMicrosoft Defender for Endpointをデプロイする方法をまとめたものです。 詳細なドキュメントについては、次を参照してください。 
- [Android でのMicrosoft Defender for Endpointの概要](microsoft-defender-endpoint-android.md)、および
- [iOS 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-ios.md)

**Android**

|登録の種類     |詳細      |
|--------------------|-------------|
|Intune統合エンドポイント マネージャーを使用した Android Enterprise (Microsoft エンドポイント マネージャー)|[Android Enterprise 登録済みデバイスにデプロイする](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|Intune統合エンドポイント マネージャーを持つデバイス管理者 (Microsoft エンドポイント マネージャー)|[デバイス管理者が登録したデバイスに展開する](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|管理されていない BYOD または他の統合エンドポイント マネージャーによって管理されているデバイス / アプリ保護ポリシー (MAM) のセットアップ|[アプリ保護ポリシー (MAM) で Defender リスクシグナルを構成する](android-configure-mam.md)|

**iOS**

|登録の種類     |詳細      |
|--------------------|-------------|
|Intune統合エンドポイント マネージャーを使用した監視対象デバイス (Microsoft エンドポイント マネージャー)|1. [iOS ストア アプリとしてデプロイ](ios-install.md)する<br/>2. [監視対象の iOS デバイス用に VPN を使用せずに Web Protection を設定](ios-install.md#complete-deployment-for-supervised-devices)する|
|Intune UEM (Microsoft エンドポイント マネージャー) に登録されている教師なし (BYOD) デバイス|[iOS ストア アプリとしてデプロイする](ios-install.md)|
|他の UEM によって管理されているアンマネージド BYOD またはデバイス / アプリ保護ポリシー (MAM) のセットアップ|[アプリ保護ポリシー (MAM) で Defender リスクシグナルを構成する](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>エンド ユーザーオンボーディング

- [iOS 登録済みデバイスのゼロタッチ オンボードを構成](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint)する: 管理者は、ユーザーがアプリを開く必要なく、登録済みの iOS デバイスでMicrosoft Defender for Endpointをサイレント オンボードするようにゼロタッチ インストールを構成できます。 

- [条件付きアクセスを構成してユーザーのオンボードを強制](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)する: これは、展開後にエンド ユーザーがMicrosoft Defender for Endpoint アプリにオンボードされるように適用できます。 Defender for Endpoint リスクシグナルを使用した条件付きアクセスの構成に関する簡単なデモについては、このビデオをご覧ください。 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>オンボードを簡略化する

- [iOS - オンボードZero-Touch](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint)
- [Android Enterprise - Always-on VPN をセットアップ](android-intune.md#auto-setup-of-always-on-vpn)します。
- [iOS - VPN プロファイルの自動セットアップ](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>パイロット評価

Microsoft Defender for Endpointを使用してモバイル脅威の防御を評価するときに、サービスを大規模なデバイスセットにデプロイする前に、特定の条件が満たされていることを確認できます。 広くデプロイする前に、終了条件を定義し、それらが満たされていることを確認できます。

これにより、サービスのロールアウト中に発生する可能性がある潜在的な問題を減らすことができます。 役立つ可能性のあるいくつかのテストと終了条件を次に示します。

- デバイスインベントリの一覧にデバイスが表示されます。モバイル デバイスで Defender for Endpoint のオンボードに成功した後、 [デバイスがセキュリティ コンソール](https://security.microsoft.com)のデバイス インベントリに一覧表示されていることを確認します。

- Android デバイスでマルウェア検出テストを実行する:Google Play ストアからテスト ウイルス アプリをインストールし、Microsoft Defender for Endpointによって検出されることを確認します。 このテストに使用できるアプリの例を次に示します。 [ウイルスのテスト](https://play.google.com/store/apps/details?id=com.antivirus&hl=en_US&gl=US)です。 仕事用プロファイルを持つ Android Enterprise では、仕事用プロファイルのみがサポートされることに注意してください。

- フィッシング テストを実行する:Microsoft Defender for Endpointによってブロックされることを参照https://smartscreentestratings2.netして確認します。 仕事用プロファイルを持つ Android Enterprise では、仕事用プロファイルのみがサポートされることに注意してください。

- ダッシュボードにアラートが表示されます:上記の検出テストのアラートが [セキュリティ コンソール](https://security.microsoft.com)に表示されることを確認します。

## <a name="configure"></a>Configure

- [Android 機能を構成する](android-configure.md)
- [iOS 機能の構成](ios-configure-features.md)
- [監視対象の iOS デバイス用に VPN を使用せずに Web Protection を構成する](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>リソース

- [Android 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md)
- [iOS 用 Microsoft Defender for Endpoint API](microsoft-defender-endpoint-ios.md)
- 今後のリリースについては、お [知らせ](https://aka.ms/mdeblog)をご覧ください。

