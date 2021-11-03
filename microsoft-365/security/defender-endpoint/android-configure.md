---
title: Android 機能用に Microsoft Defender for Endpoint を構成する
description: Android のエンドポイント用 Microsoft Defender を構成する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, configuration
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 53eed34cfff6d2318b87e781b32a9963c372b279
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667388"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Android の機能でエンドポイント用 Defender を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Android 上のエンドポイント用 Defender を使用した条件付きアクセス

Android 上のエンドポイント用 Microsoft Defender と Microsoft Intune および Azure Active Directory を使用すると、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intune を通じてこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。

Android および条件付きアクセスで Defender for Endpoint をセットアップする方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](/mem/intune/protect/advanced-threat-protection)。

## <a name="configure-custom-indicators"></a>カスタム インジケーターの構成

> [!NOTE]
> Defender for Endpoint on Android では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。

Defender for Endpoint on Android を使用すると、管理者は Android デバイスをサポートするカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](manage-indicators.md)。

## <a name="configure-web-protection"></a>Web 保護の構成
Defender for Endpoint on Android では、IT 管理者は Web 保護機能を構成できます。 この機能は、管理センター Microsoft エンドポイント マネージャー使用できます。

> [!NOTE]
> Android 上のエンドポイントの Defender は、Web Protection 機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。
> 詳細については、「Android を実行 [するデバイスで Web 保護を構成する」を参照してください](/mem/intune/protect/advanced-threat-protection-manage-android)。


## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>BYOD デバイス用アプリの脆弱性評価を構成する

Android 上の Microsoft Defender for Endpoint のバージョン 1.0.3425.0303 から、オンボードモバイル デバイスにインストールされている OS とアプリの脆弱性評価を実行できます。

> [!NOTE]
> 脆弱性評価は、Microsoft [](next-gen-threat-and-vuln-mgt.md) Defender for Endpoint の脅威と脆弱性の管理の一部です。 Android では、この機能は現在プレビュー中であり、商用リリース前に大幅に変更される可能性があります。

**個人用デバイス (BYOD) からのアプリに関連するプライバシーに関する注意事項:**

- 仕事用プロファイルEnterprise Android の場合、作業プロファイルにインストールされているアプリだけがサポートされます。
- 他の BYOD モードでは、既定では、アプリの脆弱性評価 **は** 有効になりません。 ただし、デバイスが管理者モードの場合、管理者はデバイスにインストールされているアプリの一覧を取得するために、Microsoft エンドポイント マネージャーを使用してこの機能を明示的に有効にできます。 詳細については、ドキュメントを参照してください。

### <a name="configure-privacy-for-device-administrator-mode"></a>デバイス管理者モードのプライバシーを構成する

対象ユーザーのデバイス管理者 **モードで** デバイスからのアプリの脆弱性評価を有効にするには、次の手順を使用します。 

> [!NOTE]
> 既定では、デバイス管理モードに登録されているデバイスでは無効になっています。

1. 管理[Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス構成プロファイルプロファイルの作成] に移動し  >    >  、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者の選択
   - **プロファイル**: [カスタム] を選択し、[作成] をクリックします。

2. [基本 **] セクション** で、プロファイルの名前と説明を指定します。

3. [構成設定 **] で****、[OMA-URI の追加] 設定を選択** します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に見つけ出すことができるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - データ型: ドロップダウン リストで [整数] を選択します。
   - 値: プライバシー設定を無効にするには 0 を入力します (既定では、値は 1 です)

4. [次 **へ] を** クリックし、このプロファイルを対象のデバイス/ユーザーに割り当てる。

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>仕事用プロファイルで Android Enterpriseを構成する

Defender for Endpoint は、作業プロファイル内のアプリの脆弱性評価をサポートします。 ただし、対象ユーザーに対してこの機能をオフにする場合は、次の手順を使用できます。

1. [[Microsoft エンドポイント マネージャー管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)**アプリ** アプリの構成ポリシー] [管理対象  >    >  **デバイス**  >  **の追加] に移動します**。
2. ポリシーに名前を付け、**プラットフォーム > Android Enterprise;** プロファイルの種類を選択します。
3. ターゲット **アプリとして [Microsoft Defender for Endpoint]** を選択します。
4. [設定] ページで、[構成デザイナーを使用する] を選択し、キーと値の種類として **DefenderTVMPrivacyMode** を整数として追加 **します。**
   - 作業プロファイル内のアプリの脆弱性を無効にするには、値を 1 と入力し、このポリシーをユーザーに割り当てる必要があります。 既定では、この値は 0 に設定されます。
   - キーが '0' に設定されているユーザーの場合、Defender はアプリの一覧を作業プロファイルからバックエンド サービスに送信して、脆弱性評価を行います。
5. [次 **へ] を** クリックし、このプロファイルを対象のデバイス/ユーザーに割り当てる。

上記のプライバシーコントロールをオンまたはオフにした場合、デバイスコンプライアンスチェックや条件付きアクセスには影響はありません。


## <a name="configure-privacy-for-malware-threat-report"></a>マルウェア脅威レポートのプライバシーを構成する

> [!NOTE]
> Android 上の Defender for Endpoint のプライバシーコントロールは現在プレビュー中であり、商用リリース前に大幅に変更される可能性があります。

マルウェア脅威レポートのプライバシー制御を使用すると、マルウェア脅威レポートからアプリの詳細 (名前とパッケージ情報) のコレクションを無効にできます。 これにより、悪意のあるアプリが検出された場合に、組織がアプリ名を収集するかどうかを柔軟に選択できます。 *この機能は現在、Android デバイス管理者モードに登録されている **デバイスでのみ使用** できます。*

対象ユーザーに対して有効にするには、次の手順を使用します。

1. 管理[Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス構成プロファイルプロファイルの作成] に移動し  >    >  、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者の選択
   - **プロファイル**: [カスタム] を選択し、[作成] をクリックします。

2. [基本 **] セクション** で、プロファイルの名前と説明を指定します。

3. [構成設定 **] で****、[OMA-URI の追加] 設定を選択** します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に見つけ出すことができるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - データ型: ドロップダウン リストで [整数] を選択します。
   - 値: プライバシー設定を有効にするには 1 を入力します (既定では、値は 0 です)

4. [次 **へ] を** クリックし、このプロファイルを対象のデバイス/ユーザーに割り当てる。

このプライバシー制御を使用すると、デバイスコンプライアンスチェックや条件付きアクセスには影響を与えかねない。 たとえば、悪意のあるアプリを持つデバイスのリスク レベルは常に "中" になります。

## <a name="related-topics"></a>関連トピック

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
