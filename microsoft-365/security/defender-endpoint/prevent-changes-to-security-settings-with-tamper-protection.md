---
title: 改ざん防止機能を使用してセキュリティ設定を保護する
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: 改ざん防止を使用して、悪意のあるアプリが重要なセキュリティ設定を変更できないようにします。
keywords: マルウェア, Defender, ウイルス対策, 改ざん防止
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: dd0512f66adc012c222bded21bad6904bff884dd
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387157"
---
# <a name="protect-security-settings-with-tamper-protection"></a>改ざん防止機能を使用してセキュリティ設定を保護する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

改ざん防止は、次のいずれかのバージョンの Windows を実行しているデバイスで使用できます。

- Windows 11
- Windows 11 Enterprise multi-session 
- Windows 10
- Windows 10 Enterprise マルチセッション
- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> Windows Server 2012 R2 の改ざん保護は、最新の統合ソリューション パッケージを使用してオンボードされたデバイスで使用できます。 詳細については、「[Windows サーバーを Microsoft Defender for Endpoint サービスにオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints)」を参照してください。

## <a name="overview"></a>概要

サイバー攻撃の種類によっては、悪いアクターがマシンでウイルス対策保護などのセキュリティ機能を無効にしようとします。 悪意のあるアクターは、データへのアクセスを容易にしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にすることを好みます。 改ざん防止は、このようなことが発生するのを防ぐのに役立ちます。 改ざん防止により、悪意のあるアプリは次のようなアクションを実行できなくなります。

- ウイルスおよび脅威の保護の無効化
- リアルタイム保護の無効化
- 動作の監視の無効化
- IOfficeAntivirus (IOAV) などのウイルス対策保護を無効にする
- クラウド配信の保護の無効化
- セキュリティ インテリジェンスの更新プログラムの削除
- 検出された脅威に対する自動アクションを無効にする
- Windows セキュリティ アプリでの通知の抑制
- アーカイブファイルとネットワーク ファイルのスキャンを無効にする

### <a name="how-it-works"></a>メカニズム

改ざん防止は、基本的に Microsoft Defender ウイルス対策をセキュリティで保護された既定値にロックし、次のようなアプリや方法を使用してセキュリティ設定が変更されないようにします。

- Windows デバイスのレジストリ エディターで設定を構成する
- PowerShell コマンドレットを使用した設定の変更
- グループ ポリシーを使用したセキュリティ設定の編集または削除

改ざん防止では、セキュリティ設定を表示できません。 また、改ざん防止は、Microsoft 以外のウイルス対策アプリがWindows セキュリティ アプリに登録する方法には影響しません。 組織で Windows 10 Enterprise E5 を使用している場合、個々のユーザーは改ざん防止設定を変更できません。そのような場合、改ざん保護はセキュリティ チームによって管理されます。

### <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

|このタスクを実行するには...|このセクションを参照してください。..|
|---|---|
|テナント全体の改ざん保護を管理する <p> Microsoft 365 Defender ポータルを使用して改ざん防止を有効または無効にする|[Microsoft 365 Defenderを使用して組織の改ざん防止を管理する](manage-tamper-protection-microsoft-365-defender.md)|
|組織内の改ざん防止設定を微調整する <p> 改ざん防止を有効または無効にするには、Intune (Microsoft エンドポイント マネージャー) を使用します。 この方法を使用して、一部またはすべてのユーザーの改ざん防止を構成できます。|[Microsoft エンドポイント マネージャーを使用して組織の改ざん防止を管理する](manage-tamper-protection-microsoft-endpoint-manager.md)|
|Configuration Managerを使用して組織の改ざん防止をオン (またはオフ) にする|[Configuration Managerバージョン 2006 でテナントアタッチを使用して組織の改ざん保護を管理する](manage-tamper-protection-configuration-manager.md)|
|個々のデバイスの改ざん防止をオン (またはオフ) にする|[個々のデバイスで改ざん防止を管理する](manage-tamper-protection-individual-device.md)|
|デバイスでの改ざんの試行に関する詳細を表示する|[改ざんの試行に関する情報を表示する](#view-information-about-tampering-attempts)|
|セキュリティに関する推奨事項を確認する|[セキュリティに関する推奨事項を確認する](#review-your-security-recommendations)|
|よく寄せられる質問の一覧 (FAQ) を確認する|[FAQ を参照する](faqs-tamper-protection.md)|

## <a name="potential-dependency-on-cloud-protection"></a>クラウド保護に対する潜在的な依存関係  
  
改ざん防止を有効にするために使用する方法または管理ツールによっては、 [クラウド配信](cloud-protection-microsoft-defender-antivirus.md)保護に依存している可能性があります。 クラウド配信保護は、クラウド保護または Microsoft Advanced Protection Service (MAPS) とも呼ばれます。

次の表に、メソッド、ツール、依存関係の詳細を示します。

| 改ざん防止を有効にする方法 | クラウド保護への依存 |
|---|---|
|Microsoft Intune|不要|
|テナントアタッチを使用した Microsoft Endpoint Configuration Manager|不要|
|Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com))|はい|

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>R2、2016、または Windows バージョン 1709、1803、または 1809 Windows Server 2012使用していますか?

最新の統合ソリューション、Windows Server 2016、Windows 10 バージョン 1709、1803、または [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) を使用して Windows Server 2012 R2 を使用している場合、Windows セキュリティ アプリに **改ざん防止** は表示されません。 代わりに、PowerShell を使用して、改ざん保護が有効になっているかどうかを判断できます。

Windows Server 2016では、改ざん防止が有効になっている場合、設定アプリはリアルタイム保護の状態を正確に反映しません。

### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>PowerShell を使用して、改ざん防止とリアルタイム保護が有効になっているかどうかを判断する

1. Windows PowerShell アプリを開きます。

2. [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell コマンドレットを使用します。

3. 結果の一覧で、 `IsTamperProtected` 検索または検索します `RealTimeProtectionEnabled`。 ( *true* の値は、改ざん保護が有効になっていることを意味します)。

## <a name="view-information-about-tampering-attempts"></a>改ざんの試行に関する情報を表示する

改ざんの試行は、通常、より大きなサイバー攻撃を示しています。 不適切なアクターは、セキュリティ設定を永続化して検出され続ける方法として変更しようとします。 組織のセキュリティ チームの一員である場合は、そのような試行に関する情報を表示し、脅威を軽減するための適切なアクションを実行できます。

改ざんの試行が検出されると、[Microsoft 365 Defender ポータル](/microsoft-365/security/defender-endpoint/portal-overview) ([https://security.microsoft.com](https://security.microsoft.com)) でアラートが発生します。

[Microsoft Defender for Endpointでエンドポイントの検出と応答](overview-endpoint-detection-response.md)、[高度な捜索](advanced-hunting-overview.md)機能を使用して、セキュリティ運用チームはそのような試みを調査して対処できます。

## <a name="review-your-security-recommendations"></a>セキュリティに関する推奨事項を確認する

改ざん防止は[、Microsoft Defender 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)機能と統合されます。 [セキュリティに関する推奨事項には、](tvm-security-recommendation.md) 改ざん防止が有効になっていることを確認することが含まれます。 たとえば、 *改ざん* を検索できます。 結果で、[ **改ざん防止を有効にする]** を選択して詳細を確認し、有効にすることができます。

Microsoft Defender 脆弱性の管理の詳細については、「[ダッシュボードの分析情報 - Defender の脆弱性管理」を](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management)参照してください。


> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Endpoint Protection for Microsoft Intune を使用して Windows PC をセキュリティで保護する](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Defender for Endpoint の概要を確認する](/microsoft-365/security/defender-endpoint)
- [ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
- [トラブルシューティング モードを有効にする](enable-troubleshooting-mode.md)
- [トラブルシューティング モードがオンです](troubleshooting-mode-scenarios.md)
