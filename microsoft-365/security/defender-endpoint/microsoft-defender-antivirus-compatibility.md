---
title: Microsoft Defender ウイルス対策他のセキュリティ製品との互換性
description: 他のセキュリティMicrosoft Defender ウイルス対策オペレーティング システムとの関連付けについて説明します。
keywords: windows Defender、 Defender for endpoint, 次世代, ウイルス対策, 互換性, パッシブ モード
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
ms.topic: article
manager: dansimp
ms.technology: mde
ms.date: 05/06/2021
ms.openlocfilehash: 866a36828c5c83d833d66bd7ed7d32b3499cbbdf
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275158"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender ウイルス対策互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>概要

Microsoft Defender ウイルス対策を実行しているエンドポイントとデバイスに自動的に有効にされ、インストールWindows 10。 しかし、別の (Microsoft 以外の) ウイルス対策/マルウェア対策ソリューションを使用するとどうなるでしょうか。 Microsoft [Defender for Endpoint](microsoft-defender-endpoint.md) とウイルス対策保護を組み合わせて使用するかどうかによって異なります。 この記事では、エンドポイントが Microsoft Defender for Endpoint にオンボードされている場合に、ウイルス対策/マルウェア対策ソリューションで何が起こるかを説明します。

## <a name="why-defender-for-endpoint-matters"></a>Defender for Endpoint が重要な理由

Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合でも、エンドポイントを Defender for Endpoint にオンボーディングする方法を検討してください。 ほとんどの場合、デバイスを Defender for Endpoint にオンボードする場合、Microsoft 以外のウイルス対策ソリューションとMicrosoft Defender ウイルス対策を使用して保護を強化できます。 たとえば、ブロック モードで EDR[を使用すると](edr-in-block-mode.md)、プライマリ ウイルス対策ソリューションが見逃している可能性のある悪意のあるアーティファクトをブロックおよび修復できます。 

次に、動作のしくみを示します。

- 組織のクライアント デバイスが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護されている場合、それらのデバイスが Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策 は自動的にパッシブ モードになります。 この場合、脅威の検出は発生しますが、リアルタイムの保護と脅威は、ユーザーがMicrosoft Defender ウイルス対策。 **注**: この特定のシナリオは、サーバーで実行されているエンドポイントにはWindowsされません。

- 組織のクライアント デバイスが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護され、それらのデバイスが Microsoft Defender for Endpoint にオンボードされない場合、Microsoft Defender ウイルス対策 は自動的に無効モードになります。 この場合、脅威は、ユーザーが検出または修復Microsoft Defender ウイルス対策。 **注**: この特定のシナリオは、サーバーで実行されているエンドポイントにはWindowsされません。

- 組織のエンドポイントが Windows Server を実行し、それらのエンドポイントが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護されている場合、それらのエンドポイントが Defender for Endpoint にオンボードされている場合、Microsoft Defender ウイルス対策 はパッシブ モードまたは無効モードに自動的には入りません。 この特定のシナリオでは、サーバー エンドポイントを適切にWindowsする必要があります。 

   - Windows サーバー、バージョン 1803 以降、および Windows Server 2019 では、パッシブ モードでMicrosoft Defender ウイルス対策を実行するように設定できます。 
   - このWindows Server 2016、Microsoft Defender ウイルス対策を無効にする必要があります (パッシブ モードは、Windows Server 2016)。

- 組織のエンドポイントが Microsoft 以外のウイルス対策/マルウェア対策ソリューションによって保護されている場合、これらのデバイスがブロック モードで[EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)で Defender for Endpoint にオンボーディングされている場合、Defender for Endpoint は悪意のあるアーティファクトをブロックして修復します。 **注**: この特定のシナリオは、このシナリオにはWindows Server 2016。 EDRモードでは、アクティブ モードMicrosoft Defender ウイルス対策パッシブ モードで有効にする必要があります。

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>ウイルス対策と Microsoft Defender for Endpoint

次の表は、Microsoft 以外のウイルスMicrosoft Defender ウイルス対策マルウェア対策ソリューションを使用する場合、または Microsoft Defender for Endpoint を使用しない場合に発生する問題の概要を示しています。 

| Windows バージョン   | ウイルス対策/マルウェア対策ソリューション  | オンボード <br/> Defender for Endpoint? | Microsoft Defender ウイルス対策状態     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10  | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows 10  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | パッシブ モード (自動) |
| Windows 10  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ   | 無効モード (自動的に)    |
| Windowsサーバー、バージョン 1803 以降 <p> Windows Server 2019 | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windowsサーバー、バージョン 1803 以降 <p> Windows Server 2019 | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windowsサーバー、バージョン 1803 以降 <p> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | Microsoft Defender ウイルス対策パッシブ モードに設定する必要があります (手動) <sup> [[1](#fn1)]<sup>  | 
| Windowsサーバー、バージョン 1803 以降 <p> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ  | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Windows Server、バージョン 1803 以降、または Windows Server 2019 では、microsoft 以外のウイルス対策製品をインストールしても、Microsoft Defender ウイルス対策 はパッシブ モードに自動的に入らない。 このような場合は、サーバーに複数[Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode)ウイルス対策製品がインストールされている場合に発生する問題を防ぐために、パッシブ モードに設定します。 PowerShell、グループ Microsoft Defender ウイルス対策レジストリ キーを使用して、パッシブ モードに設定できます。

Windows Server、バージョン 1803 以降、または Windows Server 2019 を使用している場合は、次のレジストリ キーを設定して、Microsoft Defender ウイルス対策 をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- タイプ: `REG_DWORD`
- 値: `1`

> [!NOTE]
> パッシブ モードは、デバイスでWindows Server 2016。 レジストリ `ForcePassiveMode` キーは、レジストリ キーにはWindows Server 2016。 

(<a id="fn2">2</a>) Windows Server 2016 Microsoft 以外のウイルス対策製品を使用している場合は、パッシブ モードまたはアクティブ モードMicrosoft Defender ウイルス対策を実行できません。 このような場合は、サーバー[に](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016)複数Microsoft Defender ウイルス対策ウイルス対策製品がインストールされている場合に発生する問題を防ぐために、手動でインストールを無効またはアンインストールします。

サーバー [Microsoft Defender ウイルス対策のWindowsの](microsoft-defender-antivirus-on-windows-server.md)主な違いおよび管理オプションについては、「Windows」を参照してください。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10、Windows Server 2016、Windows Server、バージョン 1803 以降、および Windows Server 2019 を実行しているデバイスでのみ使用できます。
>
> このWindows 8.1およびWindows Server 2012、エンタープライズ レベルのエンドポイントウイルス対策保護は、System Center Endpoint Protection によって管理Microsoft Endpoint Configuration Manager。 [](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))
>
> Windows Defender Windows 8.1 および Windows Server 2012 のコンシューマー デバイスにも提供されます 。ただし、エンタープライズ レベルの管理 (または[Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)Server Core インストール上のインターフェイス) は提供されません。

## <a name="functionality-and-features-available-in-each-state"></a>各状態で使用可能な機能と機能

このセクションの表では、各状態で使用できる機能と機能の概要を示します。 このテーブルは、情報のみを提供するように設計されています。 Microsoft Defender ウイルス対策 がアクティブ モード、パッシブ モード、または無効/アンインストールされたかどうかに応じて、アクティブに動作している機能& 機能を記述することを目的とします。 

> [!IMPORTANT]
> パッシブ モードで Microsoft Defender ウイルス対策 を使用しているか、ブロック モードで EDR を使用している場合は、リアルタイム保護、クラウド配信保護、制限付き定期的スキャンなどの機能をオフにしません。 

|Protection |アクティブ モード |パッシブ モード |ブロック モードの EDR |無効またはアンインストール |
|:---|:---|:---|:---|:---|
| [リアルタイム保護と](configure-real-time-protection-microsoft-defender-antivirus.md)[クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | いいえ <sup> [[3](#fn3)]<sup> | いいえ | いいえ |
| [定期的なスキャンの可用性が制限されている](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | いいえ | はい |
| [ファイルのスキャンおよび検出情報](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |
|  [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup> [ 4 ][を参照してください](#fn4)。<sup> | はい | いいえ |
| [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |

(<a id="fn3">3</a>) 一般に、Microsoft Defender ウイルス対策 がパッシブ モードの場合、リアルタイム保護は、有効でパッシブ モードの場合でも、ブロックや強制を提供しません。 

(<a id="fn4">4</a>) Microsoft Defender ウイルス対策モードの場合、脅威修復機能はスケジュールされたスキャンまたはオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365エンドポイント のデータ](/microsoft-365/compliance/endpoint-dlp-learn-about)損失防止保護は、アクティブモードまたはパッシブ モードの場合Microsoft Defender ウイルス対策正常に動作し続ける。

## <a name="keep-the-following-points-in-mind"></a>以下の点に気を付ける

- アクティブ モードでは、Microsoft Defender ウイルス対策ウイルス対策アプリとして使用されます。 Configuration Manager、グループ ポリシー、Intune、または他の管理製品で行われたすべての構成が適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (Configuration Manager やコンピューター上の Microsoft Defender ウイルス対策 アプリなど) で報告されます。

- パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用され、脅威はウイルス対策アプリによって修復Microsoft Defender ウイルス対策。 ファイルがスキャンされ、Microsoft Defender for Endpoint サービスと共有される脅威検出のレポートが提供されます。 セキュリティ センターには、パッシブ[](microsoft-defender-security-center.md)モードの場合Microsoft Defender ウイルス対策ソースとして通知Microsoft Defender ウイルス対策表示される場合があります。

- ブロック[EDRが有効](edr-in-block-mode.md)になっていて、Microsoft Defender ウイルス対策ウイルス対策ソリューションではない場合、悪意のあるアイテムを検出して修復します。 EDRモードでは、アクティブ モードMicrosoft Defender ウイルス対策パッシブ モードで有効にする必要があります。

- 無効にすると、Microsoft Defender ウイルス対策ウイルス対策アプリとして使用されません。 ファイルはスキャンされません。脅威は修復されません。 一般に、Microsoft Defender ウイルス対策の無効化/アンインストールは推奨されません。可能であれば、Microsoft Microsoft Defender ウイルス対策ウイルス対策ソリューションを使用している場合は、パッシブ モードに維持してください。

- Microsoft Defender for Endpoint に登録し、サードパーティのマルウェア対策製品を使用している場合は、パッシブ モードが有効になります。 このサービスでは、侵入の試みと攻撃Microsoft Defender ウイルス対策デバイスとネットワークを適切に監視するために、Microsoft Defender ウイルス対策 サービスからの一般的な情報共有が必要です。 詳細については、「Microsoft [Defender for Endpoint Microsoft Defender ウイルス対策互換性に関するページ」を参照してください](defender-compatibility.md)。 

- パッシブ Microsoft Defender ウイルス対策モードの場合でも、ユーザーの更新プログラム[を管理Microsoft Defender ウイルス対策。](manage-updates-baselines-microsoft-defender-antivirus.md)ただし、マルウェアからのリアルタイム保護を提供する最新の Microsoft 以外のウイルス対策製品がデバイスに存在する場合は、Microsoft Defender ウイルス対策をアクティブ モードに移行できません。 セキュリティ層による防御と検出の有効性を最適に保つには、Microsoft Defender ウイルス対策 がパッシブ モードで実行されている場合でも[、Microsoft Defender ウイルス対策](manage-updates-baselines-microsoft-defender-antivirus.md)保護 (セキュリティ インテリジェンス更新プログラム、エンジン、およびプラットフォーム) を更新してください。

- Microsoft Defender ウイルス対策が自動的に無効になっている場合、Microsoft 以外のウイルス対策製品によって提供される保護が期限切れになったり、ウイルス、マルウェア、その他の脅威からのリアルタイム保護を停止したりすると、自動的に再び有効にできます。 自動再有効化は、デバイスでウイルス対策保護が確実に維持されるのに役立ちます。 また、メインのウイルス対策[](limited-periodic-scanning-microsoft-defender-antivirus.md)アプリに加えて、Microsoft Defender ウイルス対策エンジンを使用して定期的に脅威をチェックする限られた定期的なスキャンを有効にすることもできます。

> [!WARNING]
> Microsoft Defender ウイルス対策、Microsoft Defender for Endpoint、またはアプリで使用される関連サービスを無効、停止、またはWindows セキュリティしない。 この推奨事項には、wscsvc、SecurityHealthService、MsSense、Sense、WinDefend、または *MsMpEng* サービスとプロセスが含まれます。     これらのサービスを手動で変更すると、デバイスに重大な不安定性が生じ、ネットワークが脆弱になる可能性があります。 これらのサービスを無効にしたり、停止したり、変更したりすると、Microsoft 以外のウイルス対策ソリューションを使用する場合や、それらの情報が Windows セキュリティ アプリに表示される場合にも問題が[発生する可能性があります](microsoft-defender-security-center-antivirus.md)。


## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策のWindows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [構成Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
