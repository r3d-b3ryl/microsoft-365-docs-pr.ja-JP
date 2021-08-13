---
title: Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性
description: 他のセキュリティ製品を使用した Microsoft Defender ウイルス対策とオペレーティング システムについて説明します。
keywords: Windows Defender、Defender for Endpoint、次世代、ウイルス対策、互換性、パッシブ モード
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: b7584a7e8165b11e334d004736df4b3868a1f172d2c5d1d0d7127cde311fee67
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800044"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender ウイルス対策互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>要約

Microsoft Defender ウイルス対策は自動的に有効になり、Windows 10を実行しているエンドポイントとデバイスにインストールされます。 しかし、別の (Microsoft 以外の) ウイルス対策/マルウェア対策ソリューションを使用するとどうなるでしょうか。 Microsoft Defender ウイルス対策を別のウイルス対策製品と共に実行できますか? 回答は、オペレーティング システムや、ウイルス対策保護と共に [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) 使用しているかどうかなど、いくつかの要因によって異なります。 

## <a name="important-points-to-keep-in-mind"></a>留意すべき重要な点

- アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 構成マネージャー、グループ ポリシー、Microsoft Intune、またはその他の管理製品を使って構成された設定が適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (エンドポイント自体の構成マネージャーやMicrosoft Defender ウイルス対策 アプリなど) で報告されます。

- パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、Microsoft Defender ウイルス対策によって脅威の修復を行われることは *ありません*。 ファイルのスキャン、Microsoft Defender for Endpoint サービスで共有された脅威検出へ報告が行われます。 Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[セキュリティ センター](microsoft-defender-security-center.md) で Microsoft Defender ウイルス対策がソースとして表示される警告を受け取る場合があります。

- [ブロック モードの EDR](edr-in-block-mode.md) がオンになっていて、Microsoft Defender ウイルス対策がプライマリ ウイルス対策ソリューションではない場合、ブロック モードの EDR によりデバイス上に見つかった悪意のあるアイテムが検出され、(侵害後に) 修復されます。 ブロック モードの EDR では、Microsoft Defender ウイルス対策をアクティブ モードまたはパッシブ モードで有効にする必要があります。

- 無効にすると、Microsoft Defender ウイルス対策がウイルス対策アプリとして使用されません。 ファイルのスキャン、脅威の修復は行われません。 Microsoft Defender ウイルス対策の無効化/アンインストールは一般的にお勧めしません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、できたら　Microsoft Defender ウイルス対策をパッシブにしてください。

- Microsoft Defender for Endpoint に登録していて、Microsoft 以外のウイルス対策/マルウェア対策製品を使用している場合、Microsoft Defender ウイルス対策はパッシブ モードで有効になります。 Defender for Endpoint では、侵入の試行や攻撃についてデバイスとネットワークを適切に監視するために、Microsoft Defender ウイルス対策からの一般的な情報共有が必要です。 詳細については、「[Microsoft Defender for Endpoint との Microsoft Defender ウイルス対策互換性](defender-compatibility.md)」を参照してください。 

- Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。 セキュリティの多層防御と検出の有効性を最適化するには、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、ウイルス対策とマルウェア対策の更新プログラムを取得してください。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。

- Microsoft Defender ウイルス対策が自動的に無効になっている場合は、Microsoft 以外のウイルス対策製品によって提供される保護の有効期限が切れるか、ウイルス、マルウェア、またはその他の脅威からのリアルタイム保護が停止した場合に、Microsoft Defender ウイルス対策を自動的に再有効化できます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。 また、Microsoft 以外のウイルス対策アプリを使用している場合に、Microsoft Defender ウイルス対策 エンジンを使用して、脅威を定期的にチェックする、[限られた定期的なスキャン](limited-periodic-scanning-microsoft-defender-antivirus.md)を有効にすることもできます。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender ウイルス対策および Microsoft 以外のウイルス対策/マルウェア対策ソリューション

オペレーティング システム、ウイルス対策製品、Defender for Endpoint は、Microsoft Defender ウイルス対策がアクティブ モードかパッシブ モードか無効かに影響します。 次の表は、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを一緒に使用した場合の Microsoft Defender ウイルス対策の動作と Microsoft Defender for Endpoint を使用しない Microsoft Defender ウイルス対策の動作をまとめたものです。 

| Windows バージョン   | ウイルス対策/マルウェア対策ソリューション  | Defender for Endpoint に <br/> オンボードしますか? | Microsoft Defender ウイルス対策     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10  | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows 10  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | パッシブ モード (自動) |
| Windows 10  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ   | 無効モード (自動)    |
| Windows Server バージョン 1803 以降 <p> Windows Server 2019 | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windows Server バージョン 1803 以降 <p> Windows Server 2019 | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windows Server バージョン 1803 以降 <p> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | Microsoft Defender ウイルス対策 をパッシブ モードに設定する必要があります (手動) <sup>[[1](#fn1)]<sup>  | 
| Windows Server バージョン 1803 以降 <p> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ  | Microsoft Defender ウイルス対策 を無効にする必要があります (手動) <sup>[[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい | Microsoft Defender ウイルス対策 を無効にする必要があります (手動) <sup>[[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ | Microsoft Defender ウイルス対策 を無効にする必要があります (手動) <sup>[[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Windows Server バージョン 1803 以降、または Windows Server 2019 では、Microsoft 以外のウイルス対策製品をインストールしている場合、Microsoft Defender ウイルス対策は自動的にパッシブ モードになりません。 このような場合、[Microsoft Defender ウイルス対策をパッシブ モードに設定](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。

バージョン 1803 以降の Windows Server、または Windows Server 2019 では、次のレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

> [!NOTE]
> パッシブ モードは、Windows Server 2016 ではサポートされていません。 `ForceDefenderPassiveMode` レジストリ キーは、Windows Server バージョン 1803 以降、または Windows Server 2019 で使用できますが、Windows Server 2016 では使用できません。 

(<a id="fn2">2</a>) Windows Server 2016 では、Microsoft 以外のウイルス対策製品を使用している場合、パッシブ モードまたはアクティブ モードで Microsoft Defender ウイルス対策を実行することはできません。 このような場合、[Microsoft Defender ウイルス対策を手動で無効/アンインストール](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。

Windows Server インストールの主な相違点と管理オプションについては、「[Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」 を参照します。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10、Windows Server 2016、Windows Server、バージョン 1803 以降、Windows Server 2019 を実行しているデバイスでのみ使用できます。
>
> Windows 8.1 および Windows Server 2012 では、エンタープライズ レベルのエンドポイント ウイルス対策保護が [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))として提供されます。これは、Microsoft Endpoint Configuration Manager によって管理されます。
>
> Windows Defender は、[Windows 8.1 上コンシューマー デバイスと Windows Server 2012 上コンシューマー デバイス](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender) へも提供されておりますが、エンタープライズ レベル管理 (または Windows Server 2012 Server Core インストール) はありません。

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

このセクションの表は、各状態で使用できる機能をまとめたものです。 表は情報提供だけを目的としています。 Windows Defender ウイルス対策がアクティブ モードか、パッシブ モードか、無効状態か、アンインストール済み状態かによって機能の作動状態を説明します。 

> [!IMPORTANT]
> パッシブ モードで Microsoft Defender ウイルス対策を使用している場合、またはブロック モードで EDR を使用している場合は、リアルタイム保護、クラウドによる保護、制限のある定期的なスキャンなどの機能をオフにしないでください。 

|保護 |アクティブ モード |パッシブ モード |ブロック モードの EDR |無効またはアンインストール済み |
|:---|:---|:---|:---|:---|
| [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md) と [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | いいえ <sup>[[3](#fn3)]<sup> | いいえ | いいえ |
| [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | いいえ | はい |
| [スキャン中ファイルと検出情報](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |
|  [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup>[[4](#fn4)]<sup> を参照します | 必要 | いいえ |
| [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |

(<a id="fn3">3</a>) 一般に、Microsoft Defender ウイルス対策がパッシブ モードの場合、リアルタイム保護でブロックや強制が有効になっておりパッシブ モードでもブロックや強制ができません。 

(<a id="fn4">4</a>) Microsoft Defender ウイルス対策がパッシブ モードの場合、脅威修復機能は、スケジュールされたスキャン中とオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365 Endpoint データ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about) 保護は、Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードの場合、正常に動作し続けます。

## <a name="why-defender-for-endpoint-matters"></a>Defender for Endpoint が重要な理由

Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合でも、エンドポイントを Defender for Endpoint にオンボードすることを検討してみましょう。 ほとんどの場合、デバイスを Defender for Endpoint にオンボードすると、Microsoft 以外のウイルス対策ソリューションと一緒に Microsoft Defender ウイルス対策を併用して保護を強化することができます。 たとえば、[ブロック モードでEDR](edr-in-block-mode.md) を使用すると、プライマリ ウイルス対策ソリューションで見逃されることがある悪意のある成果物をブロックして修復することができます。 

次に、動作のしくみを示します。

- 組織のクライアント デバイスが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護され、それらのデバイスが Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策は自動的にパッシブ モードになります。 この場合、脅威の検出は行われますが、リアルタイム保護と脅威はMicrosoft Defender ウイルス対策によって修復されることはありません。
   
   > [!NOTE]
   > この特定のシナリオは、Windows Server を実行しているエンドポイントには適用されません。

- 組織のクライアント デバイスが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護され、それらのデバイスが Microsoft Defender for Endpoint にオンボードされていない場合、Microsoft Defender ウイルス対策は自動的に無効モードになります。この場合、脅威は Microsoft Defender ウイルス対策によって検出または修復されません。
   
   > [!NOTE]
   > この特定のシナリオは、Windows Server を実行しているエンドポイントには適用されません。

- 組織のエンドポイントが Windows Server を実行していて、それらのエンドポイントが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護されている場合、それらのエンドポイントが Defender for Endpoint にオンボードされても、Microsoft Defender ウイルス対策が自動的にパッシブ モードになったり無効になったりすることはありません。この特定のシナリオでは、Windows Server エンドポイントを適切に構成する必要があります。 

   - バージョン 1803 以降の Windows Server、Windows Server 2019 では、Microsoft Defender ウイルス対策をパッシブ モードで実行するように設定できます。 
   - Windows Server 2016 では、Microsoft Defender ウイルス対策を無効にする必要があります (Windows Server 2016 ではパッシブ モードはサポートされていません)。

- 組織のエンドポイントが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護されている場合、それらのデバイスを [ブロック モードで EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) を有効にして Defender for Endpoint にさせると、Defender for Endpoint で悪意のある成果物をブロックして修復することができます。
   
   > [!NOTE]
   > この特定のシナリオは、Windows Server 2016 には適用されません。 ブロック モードの EDR では、Microsoft Defender ウイルス対策をアクティブ モードまたはパッシブ モードで有効にする必要があります。


> [!WARNING]
> Microsoft Defender ウイルス対策、Microsoft Defender for Endpoint、Windows セキュリティ アプリで使用される関連サービスを無効化、停止、変更しないでください。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。


## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [Endpoint Protection を構成する](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
