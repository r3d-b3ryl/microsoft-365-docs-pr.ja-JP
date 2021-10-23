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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8de50b9f06f05c012cc2b4c789838612d98abe62
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557307"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Microsoft Defender for Endpoint - Mobile Threat Defense

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android および iOS のエンドポイント向け Microsoft Defender は、モバイル **脅威防御ソリューション (MTD) です**。 通常、企業は PC を脆弱性や攻撃から保護するために積極的に取り組み、モバイル デバイスは多くの場合、保護されていない状態で保護されます。 モバイル プラットフォームにアプリの分離や消費者向けアプリ ストアなどの組み込みの保護が組み込みされている場合、これらのプラットフォームは Web ベースまたは他の高度な攻撃に対して脆弱なままです。 従業員が仕事用にデバイスを使用し、機密情報にアクセスする場合、企業は MTD ソリューションを展開して、デバイスとリソースをモバイルでのますます高度な攻撃から保護する必要があります。

## <a name="key-capabilities"></a>主な機能

Microsoft Defender for Endpoint on Android and iOS では、以下の主要な機能を提供しています。 最新の機能と利点については、お知らせをお [読みください](https://aka.ms/mdeblog)。

<br>

|機能|説明|
|---|---|
|Web 保護|フィッシング対策、安全でないネットワーク接続のブロック、カスタム インジケーターのサポート。|
|マルウェア保護 (Android のみ)|悪意のあるアプリのスキャン。|
|脱獄検出 (iOS 専用)|脱獄されたデバイスの検出。|
|統合アラート|統合 M365 セキュリティ コンソールのすべてのプラットフォームからのアラート|
|条件付きアクセス、条件付き起動|リスクの高いデバイスによる企業リソースへのアクセスをブロックする。 エンドポイントリスク信号の Defender をアプリ保護ポリシー (MAM) に追加することもできます。|
|アプリケーションとのMicrosoft Tunnel|VPN ゲートウェイ Microsoft Tunnelと統合して、1 つのアプリでセキュリティと接続を有効にできます。 現在 Android でのみ利用可能|

これらすべての機能は、Microsoft Defender for Endpoint ライセンスホルダーで使用できます。 詳細については、「ライセンス要件 [」を参照してください](minimum-requirements.md#licensing-requirements)。

## <a name="overview-and-deploy"></a>概要と展開

モバイルでの Microsoft Defender for Endpoint の展開は、MEM (Microsoft エンドポイント マネージャーを介して実行できます。 MTD の機能と展開の概要については、次のビデオをご覧ください。

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

詳細については、以下のリンクを参照してください。

**Android:** [Android 上のエンドポイント用 Microsoft Defender](microsoft-defender-endpoint-android.md)

**iOS:** [iOS 上のエンドポイント用 Microsoft Defender](microsoft-defender-endpoint-ios.md)

### <a name="pilot-evaluation"></a>パイロット評価

Microsoft Defender for Endpoint を使用したモバイル脅威防御の評価中に、サービスを大規模なデバイス セットに展開する前に、特定の条件が満たされているのを確認できます。 広く展開する前に、終了条件を定義し、満たされた条件を確認できます。

これにより、サービスの展開中に発生する可能性のある潜在的な問題を減らすのに役立ちます。 以下に、役立つ可能性があるいくつかのテストと終了条件を示します。

- デバイスがデバイス インベントリ リストに表示されます。モバイル デバイス上の Defender for Endpoint のオンボーディングが正常に完了したら、セキュリティ コンソールの [デバイス インベントリ] にデバイスが一覧表示されたことを [確認します](https://security.microsoft.com)。

- Android デバイスでマルウェア検出テストを実行する: Google play ストアからテスト ウイルス アプリをインストールし、Microsoft Defender for Endpoint によって検出されるのを確認します。 このテストで使用できるアプリの例を次に示します。ウイルス [のテスト](https://play.google.com/store/apps/details?id=com.androidantivirus.testvirus)です。 Android の場合、Enterpriseプロファイルだけがサポートされます。

- フィッシング テストを実行する: Microsoft Defender for Endpoint によってブロックされるのを参照して https://smartscreentestratings2.net 確認します。 Android の場合、Enterpriseプロファイルだけがサポートされます。

- ダッシュボードにアラートが表示される: 上記の検出テストのアラートがセキュリティ コンソールに表示される [のを確認します](https://security.microsoft.com)。

## <a name="deployment-best-practices"></a>展開のベスト プラクティス

### <a name="end-user-onboarding"></a>エンド ユーザーのオンボーディング

- [条件付きアクセスを構成して](android-configure.md#conditional-access-with-defender-for-endpoint-on-android)ユーザーオンボーディングを強制する : これは、展開後にエンド ユーザーが Microsoft Defender for Endpoint アプリにオンボードされるのを確認するために適用できます。 Defender for Endpoint リスクシグナルを使用した条件付きアクセスの構成に関する簡単なデモについては、このビデオをご覧ください。 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>オンボードを簡略化する

- [Android Enterprise - セットアップ Always-on VPN](android-intune.md#auto-setup-of-always-on-vpn)。
- [iOS - VPN プロファイルの自動セットアップ](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="configure"></a>Configure

- [Android の機能を構成する](android-configure.md)
- [iOS 機能の構成](ios-configure-features.md)
- [監視対象の iOS デバイスの監視モードを構成する](ios-install.md#configure-microsoft-defender-for-endpoint-for-supervised-mode)

## <a name="resources"></a>リソース

- [Android 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md)
- [iOS 用 Microsoft Defender for Endpoint API](microsoft-defender-endpoint-ios.md)
- 今後のリリースについては、お知らせをご [覧ください](https://aka.ms/mdeblog)。

