---
title: Android 機能用に Microsoft Defender for Endpoint を構成する
description: Android のエンドポイント用 Microsoft Defender を構成する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: afff05ac0e18ac41b1e2ba70b59ed4dfd0c6a22a
ms.sourcegitcommit: e685fafd6dde4901c378685b423883faed7b4fe7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2021
ms.locfileid: "59460318"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Android の機能でエンドポイント用 Defender を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Android 上のエンドポイント用 Defender を使用した条件付きアクセス

Android 上のエンドポイント用 Microsoft Defender と Microsoft Intune および Azure Active Directory を使用すると、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。

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

## <a name="configure-privacy-for-malware-threat-report"></a>マルウェア脅威レポートのプライバシーを構成する

> [!NOTE]
> Android 上の Defender for Endpoint のプライバシーコントロールは現在プレビュー中であり、商用リリース前に大幅に変更される可能性があります。

マルウェア脅威レポートのプライバシー制御を使用すると、マルウェア脅威レポートからアプリの詳細 (名前とパッケージ情報) のコレクションを無効にできます。 これにより、悪意のあるアプリが検出された場合に、組織がアプリ名を収集するかどうかを柔軟に選択できます。 *この機能は現在、Android デバイス管理者モードに登録されている **デバイスでのみ使用** できます。*

対象ユーザーに対して有効にするには、次の手順を使用します。

1. 管理[Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)デバイス構成プロファイルプロファイルの作成] に移動し  >    >  、次の設定を入力します。

   - **プラットフォーム**: Android デバイス管理者の選択
   - **プロファイル**: [カスタム] を選択し、[作成] をクリックします。

2. [基本] セクションで、プロファイルの名前と説明を指定します。
3. [構成設定] で **、[OMA-URI の追加] 設定を選択** します。

   - **名前**: この OMA-URI 設定の一意の名前と説明を入力して、後で簡単に見つけ出すことができるようにします。
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - データ型: ドロップダウン リストで [整数] を選択します。
   - 値: プライバシー設定を有効にするには 1 を入力します (既定では、値は 0 です)

4. [次 **へ] を** クリックし、このプロファイルを対象のデバイス/ユーザーに割り当てる。

上記のプライバシー制御を有効にすると、デバイスコンプライアンスチェックや条件付きアクセスには影響を与えず、たとえば悪意のあるアプリを持つデバイスは常にリスク レベルが "中" になります。

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
