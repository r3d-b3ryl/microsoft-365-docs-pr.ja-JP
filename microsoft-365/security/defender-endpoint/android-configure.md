---
title: Android 機能用に Microsoft Defender for Endpoint を構成する
description: Android でMicrosoft Defender for Endpointを構成する方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, 構成
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
ms.openlocfilehash: 0e0a8a99444f09d58a43502edd1c94e4cce52301
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664680"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Android の機能で Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Android 上の Defender for Endpoint を使用した条件付きアクセス

Android でのMicrosoft Defender for EndpointとMicrosoft IntuneとAzure Active Directoryにより、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intuneを通じてこの機能を活用するためにデプロイできる Mobile Threat Defense (MTD) ソリューションです。

Android と条件付きアクセスで Defender for Endpoint を設定する方法の詳細については、「[Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection)」を参照してください。

## <a name="configure-custom-indicators"></a>カスタム インジケーターを構成する

> [!NOTE]
> Android 上の Defender for Endpoint では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみがサポートされます。

Android 上の Defender for Endpoint を使用すると、管理者は Android デバイスをサポートするようにカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「インジケーターの [管理](manage-indicators.md)」を参照してください。

## <a name="configure-web-protection"></a>Web 保護を構成する
Android 上の Defender for Endpoint を使用すると、IT 管理者は Web 保護機能を構成できます。 この機能は、Microsoft エンドポイント マネージャー管理センター内で使用できます。

> [!NOTE]
> Android 上の Defender for Endpoint は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。
> 詳細については、「 [Android を実行するデバイスで Web 保護を構成する」を](/mem/intune/protect/advanced-threat-protection-manage-android)参照してください。

## <a name="privacy-controls"></a>プライバシー コントロール

> [!IMPORTANT]
> Android のMicrosoft Defender for Endpointのプライバシー コントロールはプレビュー段階です。 次の情報は、市販される前に大幅に変更される可能性のあるプレリリース済み製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Android デバイスから Defender for Endpoint によって送信されるデータを構成するには、次のプライバシー制御を使用できます。

|脅威レポート     |詳細      |
|--------------------|-------------|
|マルウェア レポート |管理者はマルウェア レポートのプライバシー制御を設定できます。プライバシーが有効になっている場合、Defender for Endpoint はマルウェア アラート レポートの一部としてマルウェア アプリ名とその他のアプリの詳細を送信しません |
|フィッシング レポート |管理者はフィッシング レポートのプライバシー制御を設定できます。プライバシーが有効になっている場合、Defender for Endpoint はフィッシング アラート レポートの一部として安全でない Web サイトのドメイン名と詳細を送信しません |
|アプリの脆弱性評価 (Android のみ) |既定では、仕事用プロファイルにインストールされているアプリに関する情報のみが、脆弱性評価のために送信されます。 管理者はプライバシーを無効にして個人用アプリを含めることができます|

## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>BYOD デバイス用アプリの脆弱性評価を構成する

Android 上のバージョン 1.0.3425.0303 のMicrosoft Defender for Endpointから、オンボードされたモバイル デバイスにインストールされている OS とアプリの脆弱性評価を実行できます。

> [!NOTE]
> 脆弱性評価は、Microsoft Defender for Endpointの[脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)の一部です。 

**個人用デバイス (BYOD) からのアプリに関連するプライバシーに関する注意事項:**

- 仕事用プロファイルを持つ Android Enterpriseの場合は、仕事用プロファイルにインストールされているアプリのみがサポートされます。
- 他の BYOD モードの場合、既定では、アプリの脆弱性評価は有効 **になりません** 。 ただし、デバイスが管理者モードの場合、管理者はMicrosoft エンドポイント マネージャーを使用してこの機能を明示的に有効にして、デバイスにインストールされているアプリの一覧を取得できます。 詳細については、以下の詳細を参照してください。

### <a name="configure-privacy-for-device-administrator-mode"></a>デバイス管理者モードのプライバシーを構成する

ターゲット ユーザーの **デバイス管理者** モードでデバイスからの **アプリの脆弱性評価を有効にするには**、次の手順に従います。 

> [!NOTE]
> 既定では、デバイス管理モードで登録されているデバイスでは、この設定はオフになっています。

1. [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431) **DevicesConfiguration** >  **profilesCreate** >  プロファイルに移動し、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者を選択する
   - **プロファイル**: [カスタム] を選択し、[作成] をクリックします。

2. [ **基本]** セクションで、プロファイルの名前と説明を指定します。

3. **構成設定** で、[**OMA-URI 設定の** 追加] を選択します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に検索できるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - [データ型]: ドロップダウン リストから [整数] を選択します。
   - 値: 0 と入力してプライバシー設定を無効にします (既定では、値は 1 です)

4. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>Android Enterprise仕事用プロファイルのプライバシーを構成する

Defender for Endpoint は、仕事用プロファイル内のアプリの脆弱性評価をサポートします。 ただし、対象ユーザーに対してこの機能をオフにする場合は、次の手順を使用できます。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**AppsApp** >  **構成****ポリシーAddManaged** >  >  デバイスに移動 **します**。
2. ポリシーに名前を付けます。**プラットフォーム > Android Enterprise**; プロファイルの種類を選択します。
3. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。
4. 設定 ページで、[**構成デザイナーを使用** する] を選択し、キーとして **DefenderTVMPrivacyMode** を追加し、値の型を **Integer** として追加します。
   - 仕事用プロファイルでアプリの脆弱性を無効にするには、値を `1` 入力し、このポリシーをユーザーに割り当てます。 既定では、この値は `0`.
   - キーが設定されている `0`ユーザーの場合、Defender for Endpoint は、脆弱性評価のために、仕事用プロファイルからバックエンド サービスにアプリの一覧を送信します。
5. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

上記のプライバシー制御をオンまたはオフにしても、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。

## <a name="configure-privacy-for-phishing-alert-report"></a>フィッシング アラート レポートのプライバシーを構成する

フィッシングレポートのプライバシー制御を使用すると、フィッシング脅威レポートのドメイン名または Web サイト情報の収集を無効にすることができます。 これにより、悪意のある Web サイトまたはフィッシング Web サイトが Defender for Endpoint によって検出され、ブロックされたときに、組織がドメイン名を収集するかどうかを柔軟に選択できます。

### <a name="configure-privacy-for-phishing-alert-report-on-android-device-administrator-enrolled-devices"></a>Android デバイス管理者が登録したデバイスでフィッシング アラート レポートのプライバシーを構成します。

ターゲット ユーザーに対して有効にするには、次の手順に従います。

1. [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431) **DevicesConfiguration** >  **profilesCreate** >  プロファイルに移動し、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者を選択します。
   - **プロファイル**: [カスタム] を選択し、[ **作成**] をクリックします。

2. [ **基本]** セクションで、プロファイルの名前と説明を指定します。

3. **構成設定** で、[**OMA-URI 設定の** 追加] を選択します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に検索できるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeURLInReport**
   - [データ型]: ドロップダウン リストから [整数] を選択します。
   - 値: 1 と入力してプライバシー設定を有効にします。 既定値は 0 です。

4. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

このプライバシー制御を使用すると、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。

### <a name="configure-privacy-for-phishing-alert-report-on-android-enterprise-work-profile"></a>Android Enterprise仕事用プロファイルでフィッシング アラート レポートのプライバシーを構成する

次の手順に従って、仕事用プロファイルで対象ユーザーのプライバシーを有効にします。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**AppsApp** >  **構成****ポリシーAddManaged** >  >  デバイスに移動 **します**。
2. ポリシーに名前を付けます **。Platform > Android Enterprise** は、プロファイルの種類を選択します。
3. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。
4. 設定 ページで、[**構成デザイナーの使用**] を選択し、キーとして **DefenderExcludeURLInReport** を追加し、値の型を Integer として追加 **します**。
   - **プライバシーを有効にするには、「1」と入力します**。 既定値は 0 です。
5. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

上記のプライバシー制御をオンまたはオフにしても、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。

## <a name="configure-privacy-for-malware-threat-report"></a>マルウェアの脅威レポートのプライバシーを構成する

マルウェア脅威レポートのプライバシー制御を使用すると、マルウェア脅威レポートからアプリの詳細 (名前とパッケージ情報) の収集を無効にすることができます。 これにより、組織は、悪意のあるアプリが検出されたときにアプリ名を収集するかどうかを柔軟に選択できます。

### <a name="configure-privacy-for-malware-alert-report-on-android-device-administrator-enrolled-devices"></a>Android デバイス管理者が登録したデバイスでマルウェア アラート レポートのプライバシーを構成します。

ターゲット ユーザーに対して有効にするには、次の手順に従います。

1. [管理センター Microsoft エンドポイント マネージャー](https://go.microsoft.com/fwlink/?linkid=2109431) **DevicesConfiguration** >  **profilesCreate** >  プロファイルに移動し、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者を選択します。
   - **プロファイル**: [カスタム] を選択し、[ **作成**] をクリックします。

2. [ **基本]** セクションで、プロファイルの名前と説明を指定します。

3. **構成設定** で、[**OMA-URI 設定の** 追加] を選択します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に検索できるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - [データ型]: ドロップダウン リストから [整数] を選択します。
   - 値: 1 と入力してプライバシー設定を有効にします。 既定値は 0 です。

4. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

このプライバシー制御を使用すると、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。 たとえば、悪意のあるアプリを持つデバイスでは、常にリスク レベルが "中" になります。

### <a name="configure-privacy-for-malware-alert-report-on-android-enterprise-work-profile"></a>Android Enterprise仕事用プロファイルでマルウェア アラート レポートのプライバシーを構成する

次の手順に従って、仕事用プロファイルで対象ユーザーのプライバシーを有効にします。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**AppsApp** >  **構成****ポリシーAddManaged** >  >  デバイスに移動 **します**。
2. ポリシーに名前を付けます **。Platform > Android Enterprise** は、プロファイルの種類を選択します。
3. ターゲット アプリとして **Microsoft Defender for Endpoint** を選択します。
4. 設定 ページで、**構成デザイナーを使用** を選択し、**キーとして DefenderExcludeAppInReport** を追加し、値の型を **Integer** として追加します。
   - **プライバシーを有効にするには、「1」と入力します**。 既定値は 0 です。
5. [ **次へ** ] をクリックし、このプロファイルを対象のデバイス/ユーザーに割り当てます。

このプライバシー制御を使用すると、デバイスコンプライアンスチェックや条件付きアクセスには影響しません。 たとえば、悪意のあるアプリを持つデバイスでは、常にリスク レベルが "中" になります。

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
