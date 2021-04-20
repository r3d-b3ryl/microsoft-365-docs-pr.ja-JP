---
title: Microsoft Defender ウイルス対策と他のセキュリティ製品との互換性
description: 他のセキュリティ製品と使用しているオペレーティング システムを含む Microsoft Defender ウイルス対策に期待する機能。
keywords: Windows Defender, 次世代, ウイルス対策, 互換性, パッシブ モード
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8e179135f12ad6f4ea765eaf975a40534446b51f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893391"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender ウイルス対策の互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>概要

Microsoft Defender ウイルス対策は、Windows 10 を実行しているエンドポイントとデバイスに自動的に有効にされ、インストールされます。 しかし、別のウイルス対策/マルウェア対策ソリューションが使用されている場合は、何が起こりますか? Microsoft [Defender for Endpoint](microsoft-defender-endpoint.md) とウイルス対策保護を組み合わせて使用するかどうかによって異なります。
- 組織のエンドポイントとデバイスが Microsoft 以外のウイルス対策/マルウェア対策ソリューションで保護され、Microsoft Defender for Endpoint が使用されない場合、Microsoft Defender Antivirus は自動的に無効モードになります。
- 組織で Microsoft Defender for Endpoint を Microsoft 以外のウイルス対策/マルウェア対策ソリューションと組み合わせて使用している場合、Microsoft Defender Antivirus は自動的にパッシブ モードになります。 (リアルタイムの保護と脅威は、Microsoft Defender ウイルス対策によって修復されるのではありません。
- 組織が Microsoft 以外のウイルス対策/マルウェア対策ソリューションと共に Microsoft Defender for Endpoint を使用し、ブロック モードで [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) が有効になっている場合、悪意のあるアーティファクトが検出されるたびに、Microsoft Defender for Endpoint はアーティファクトをブロックおよび修復するアクションを実行します。

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>ウイルス対策と Microsoft Defender for Endpoint

次の表は、サード パーティ製のウイルス対策製品が Microsoft Defender for Endpoint で使用されている場合、または Microsoft Defender for Endpoint を使用しない場合の Microsoft Defender ウイルス対策の概要を示しています。 


| Windows バージョン   | マルウェア対策保護  | エンドポイント登録用 Microsoft Defender | Microsoft Defender ウイルス対策の状態     |
|------|------|-------|-------|
| Windows 10  | Microsoft が提供または開発していないサードパーティ製品 | はい  | パッシブ モード  |
| Windows 10  | Microsoft が提供または開発していないサードパーティ製品 | いいえ   | 自動無効化モード     |
| Windows 10  | Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10  | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows Server、バージョン 1803 以降、または Windows Server 2019 | Microsoft が提供または開発していないサードパーティ製品 | はい  | パッシブ モードに設定する必要があります (手動) <sup> [[1](#fn1)]<sup>  | 
| Windows Server、バージョン 1803 以降、または Windows Server 2019 | Microsoft が提供または開発していないサードパーティ製品 | いいえ  | 無効にする必要があります (手動) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server、バージョン 1803 以降、または Windows Server 2019 | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windows Server、バージョン 1803 以降、または Windows Server 2019 | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
| Windows Server 2016 | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 | Microsoft が提供または開発していないサードパーティ製品 | はい | 無効にする必要があります (手動) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft が提供または開発していないサードパーティ製品 | いいえ | 無効にする必要があります (手動) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Windows Server、バージョン 1803 以降、または Windows Server 2019 では、Microsoft 以外のウイルス対策製品をインストールしても、Microsoft Defender ウイルス対策は自動的にパッシブ モードに入らない。 このような場合は [、Microsoft Defender Antivirus を](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) パッシブ モードに設定して、サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防止します。

Windows Server、バージョン 1803 以降、または Windows Server 2019 を使用している場合は、次のレジストリ キーを設定して、Microsoft Defender Antivirus をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- タイプ: `REG_DWORD`
- 値: `1`

> [!NOTE]
> レジストリ `ForcePassiveMode` キーは、Windows Server 2016 ではサポートされていません。

(<a id="fn2">2</a>) Windows Server 2016 では、Microsoft 以外のウイルス対策製品をインストールしても、Microsoft Defender ウイルス対策は自動的にパッシブ モードに入らない。 さらに、Microsoft Defender ウイルス対策はパッシブ モードではサポートされていません。 このような場合は [、Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) を手動で無効またはアンインストールして、サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐ必要があります。

Windows Server インストールの主な違いおよび管理オプションについては [、「Microsoft Defender Antivirus on Windows Server」](microsoft-defender-antivirus-on-windows-server.md) を参照してください。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10、Windows Server 2016、Windows Server、バージョン 1803 以降、および Windows Server 2019 を実行しているデバイスでのみ使用できます。
>
> Windows 8.1 および Windows Server 2012 では、エンタープライズ レベルのエンドポイントウイルス対策保護が [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))として提供され、Microsoft Endpoint Configuration Manager を通じて管理されます。
>
> Windows Defender [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)および Windows Server 2012 のコンシューマー デバイスにも提供されます 。ただし、エンタープライズ レベルの管理 (または Windows Server 2012 Server Core インストール上のインターフェイス) は提供されません。

## <a name="functionality-and-features-available-in-each-state"></a>各状態で使用可能な機能と機能

このセクションの表では、各状態で使用できる機能と機能の概要を示します。 このテーブルは、情報のみを提供するように設計されています。 これは、Microsoft Defender Antivirus がアクティブ モードかパッシブ モードか、または無効/アンインストールされるかに応じて、アクティブに動作している機能& 機能を説明することを目的とします。 

> [!IMPORTANT]
> パッシブ モードで Microsoft Defender Antivirus を使用しているか、ブロック モードで EDR を使用している場合は、リアルタイム保護、クラウド配信保護、制限付き定期的スキャンなどの機能をオフにしません。 

|Protection |アクティブ モード |パッシブ モード |ブロック モードの EDR |無効またはアンインストール |
|:---|:---|:---|:---|:---|
| [リアルタイム保護と](./configure-real-time-protection-microsoft-defender-antivirus.md)[クラウドによる保護](./enable-cloud-protection-microsoft-defender-antivirus.md) | はい | いいえ <sup> [[3](#fn3)]<sup> | いいえ | いいえ |
| [定期的なスキャンの可用性が制限されている](./limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | いいえ | はい |
| [ファイルのスキャンおよび検出情報](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |
|  [脅威の修復](./configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup> [ 4 ][を参照してください](#fn4)。<sup> | はい | いいえ |
| [セキュリティ インテリジェンスの更新プログラム](./manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | はい | いいえ |

(<a id="fn3">3</a>) 一般に、Microsoft Defender Antivirus がパッシブ モードの場合、リアルタイム保護は、有効でパッシブ モードの場合でも、ブロックや強制を提供しません。 

(<a id="fn4">4</a>) Microsoft Defender Antivirus がパッシブ モードの場合、脅威修復機能はスケジュールされたスキャンまたはオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365 Endpoint データ](/microsoft-365/compliance/endpoint-dlp-learn-about) 損失防止保護は、Microsoft Defender Antivirus がアクティブモードまたはパッシブ モードの場合、引き続き正常に動作します。

## <a name="keep-the-following-points-in-mind"></a>以下の点に気を付ける

- アクティブ モードでは、コンピューター上のウイルス対策アプリとして Microsoft Defender ウイルス対策が使用されます。 Configuration Manager、グループ ポリシー、Intune、または他の管理製品で行われたすべての構成が適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (Configuration Manager やコンピューター自体の Microsoft Defender ウイルス対策アプリなど) で報告されます。

- パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されません。脅威は Microsoft Defender ウイルス対策によって修復されません。 ファイルがスキャンされ、Microsoft Defender for Endpoint サービスと共有される脅威検出のレポートが提供されます。 したがって、Microsoft Defender ウイルス対策がパッシブ モードの場合でも、Microsoft Defender ウイルス対策をソースとしてセキュリティ センター コンソールでアラートが発生する可能性があります。

- ブロック [モードの EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) がオンになっていて、Microsoft Defender Antivirus がプライマリ ウイルス対策ソリューションではない場合でも、悪意のあるアイテムを検出して修復できます。

- 無効にすると、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されません。 ファイルはスキャンされません。脅威は修復されません。 Microsoft Defender ウイルス対策の無効化およびアンインストールは、一般的にはお勧めしません。可能であれば、Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、Microsoft Defender ウイルス対策をパッシブ モードに保つ必要があります。

- Microsoft Defender for Endpoint に登録し、サードパーティのマルウェア対策製品を使用している場合は、パッシブ モードが有効になります。 [このサービスでは、デバイス](/microsoft-365/security/defender-endpoint/defender-compatibility) とネットワークで侵入の試みと攻撃を適切に監視するために、Microsoft Defender Antivirus サービスからの一般的な情報共有が必要です。

- Microsoft Defender ウイルス対策を自動的に無効にすると、Microsoft 以外のウイルス対策製品によって提供される保護が期限切れになったり、ウイルス、マルウェア、その他の脅威からのリアルタイム保護を停止したりすると、自動的に再び有効にできます。 自動再有効化は、デバイスでウイルス対策保護が確実に維持されるのに役立ちます。 また、Microsoft Defender[](limited-periodic-scanning-microsoft-defender-antivirus.md)ウイルス対策エンジンを使用して、メインのウイルス対策アプリに加えて、定期的に脅威をチェックする限られた定期的なスキャンを有効にすることもできます。

- Microsoft Defender ウイルス対策がパッシブ モードの場合でも [、Microsoft Defender ウイルス対策の更新プログラムを管理できます](manage-updates-baselines-microsoft-defender-antivirus.md)。ただし、デバイスにマルウェアからのリアルタイム保護を提供する最新の Microsoft 以外のウイルス対策製品がある場合は、Microsoft Defender ウイルス対策をアクティブ モードに移行できません。 セキュリティ層別の防御と検出の有効性を最適化するために、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも [、Microsoft Defender](./manage-updates-baselines-microsoft-defender-antivirus.md) ウイルス対策保護 (セキュリティ インテリジェンス更新プログラム、エンジン、プラットフォーム) を更新してください。

   Microsoft 以外のウイルス対策製品をアンインストールし、Microsoft Defender ウイルス対策を使用してデバイスに保護を提供すると、Microsoft Defender ウイルス対策は自動的に通常のアクティブ モードに戻ります。

> [!WARNING]
> Microsoft Defender Antivirus、Microsoft Defender for Endpoint、または Windows セキュリティ アプリで使用される関連サービスを無効、停止、または変更しない。 この推奨事項には、wscsvc、SecurityHealthService、MsSense、Sense、WinDefend、または *MsMpEng* サービスとプロセスが含まれます。     これらのサービスを手動で変更すると、デバイスに重大な不安定性が生じ、ネットワークが脆弱になる可能性があります。 これらのサービスを無効にしたり、停止したり、変更したりすると、Microsoft 以外のウイルス対策ソリューションを使用する場合や [、Windows セキュリティ](microsoft-defender-security-center-antivirus.md)アプリでの情報の表示方法に問題が発生する場合もあります。


## <a name="see-also"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [エンドポイント保護の構成](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
