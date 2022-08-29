---
title: Microsoft Defender for Businessの次世代の保護構成設定を理解する
description: Defender for Business のウイルス対策と次世代の保護設定、中小企業のエンドポイント セキュリティについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 3fdd5f507b5f340d9de152a19a720269d96cd2a6
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320286"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessで次世代の構成設定を理解する

Defender for Business の次世代保護には、堅牢なウイルス対策とマルウェア対策の保護が含まれています。 既定のポリシーは、生産性を妨げることなく、デバイスとユーザーを保護するように設計されています。 また、ビジネス ニーズに合わせてポリシーをカスタマイズすることもできます。 また、Microsoft Intuneを使用している場合は、Microsoft エンドポイント マネージャー管理センターを使用してセキュリティ ポリシーを管理できます。

**この記事では、以下について説明します。**

- [次世代の保護の設定とオプション](#next-generation-protection-settings-and-options)
- [Defender for Business のその他の事前構成済み設定](#other-preconfigured-settings-in-defender-for-business) 
- [Defender for Business の既定の設定とMicrosoft Intune](#defender-for-business-default-settings-and-microsoft-intune)

## <a name="next-generation-protection-settings-and-options"></a>次世代の保護の設定とオプション

次の表に、設定とオプションを示します。

| Setting | 説明 |
|:---|:---|
| **リアルタイム保護**:  |  |
| **リアルタイム保護を有効にする** | 既定で有効にすると、リアルタイム保護によって、マルウェアがデバイスで実行されるのを見つけて停止します。 *リアルタイム保護を有効にしておくことをお勧めします。* リアルタイム保護を有効にすると、次の設定が構成されます。<ul><li>動作の監視がオンになっている ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring))。</li><li>ダウンロードしたすべてのファイルと添付ファイルがスキャンされます ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection))。</li><li>Microsoft ブラウザーで使用されるスクリプトはスキャンされます ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))。</li></ul>   |
| **事前ブロック** | 既定で有効にすると、一目でブロックすると、検出から数秒でマルウェアがブロックされ、分析のためにサンプル ファイルを送信できる時間 (秒単位) が長くなり、検出レベルが高に設定されます。 *一目でブロックを有効にしておくことをお勧めします。*<br/><br/>一目でブロックを有効にすると、Microsoft Defender ウイルス対策の次の設定が構成されます。<ul><li>疑わしいファイルのブロックとスキャンは、高ブロック レベル ([CloudBlockLevel) に設定されます](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)。</li><li>ファイルをブロックしてチェックする秒数は、50 秒 ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)) に設定されます。</li></ul> <br/>**大事な** ブロックが一目でオフになっている場合は、Microsoft Defender ウイルス対策に`CloudExtendedTimeout`影響`CloudBlockLevel`します。  |
| **ネットワーク保護を有効にする** | オンにすると、ネットワーク保護は、フィッシング詐欺、悪用ホスティング サイト、インターネット上の悪意のあるコンテンツから保護するのに役立ちます。 また、ユーザーがネットワーク保護をオフにすることを防ぎます。<br/><br/>ネットワーク保護は、次のモードに設定できます。<ul><li>**ブロック モード** は既定の設定です。 これにより、ユーザーが安全でないと見なされるサイトにアクセスできなくなります。 *ネットワーク保護をブロック モードに設定しておくことをお勧めします。*</li><li>**監査モード** を使用すると、ユーザーは安全でない可能性があるサイトにアクセスし、そのようなサイトとの間のネットワーク アクティビティを追跡できます。</li><li>**無効モードでは** 、ユーザーが安全でない可能性のあるサイトへのアクセスをブロックしたり、そのようなサイトとの間でネットワーク アクティビティを追跡したりすることはありません。</li></ul> |
| **修復**  |  |
| **望ましくない可能性があるアプリに対して実行するアクション (PUA)** | PUA には、広告ソフトウェアを含めることができます。署名されていない他のソフトウェアのインストールを提供するバンドル ソフトウェア。セキュリティ機能を回避しようとする回避ソフトウェア。 PUA は必ずしもウイルス、マルウェア、またはその他の種類の脅威ではありませんが、デバイスのパフォーマンスに影響を与える可能性があります。 PUA 保護は、PUA として検出されたアイテムをブロックします。 PUA 保護は次のように設定できます。<ul><li>**[有効]** は既定の設定です。 デバイス上で PUA として検出された項目がブロックされます。 *PUA 保護を有効にしておくことをお勧めします。*</li><li>**監査モード** では、PUA として検出された項目に対してアクションは実行されません。</li><li>**無効にしても** 、PUA である可能性のある項目は検出またはアクションを実行しません。</li></ul> |
| **スキャン**   |  |
| **スケジュールされたスキャンの種類** | デバイスで毎週のウイルス対策スキャンを実行することを検討してください。 次のスキャンの種類のオプションから選択できます。<ul><li>**クイックスキャンは** 、レジストリ キーやスタートアップ フォルダーなどの場所をチェックします。この場所では、マルウェアを登録してデバイスと共に起動できます。 *クイックスキャン オプションを使用することをお勧めします。*</li><li>**Fullscan は** 、デバイス上のすべてのファイルとフォルダーをチェックします。</li><li>**無効にすると** 、スケジュールされたスキャンは行われません。 ユーザーは自分のデバイスでスキャンを実行できます。 (一般に、スケジュールされたスキャンを無効にすることはお勧めしません)。</li></ul><br/> [スキャンの種類の詳細については、こちらを参照してください](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **スケジュールされたスキャンを実行する曜日** | 定期的な毎週のウイルス対策スキャンを実行する日を選択します。 |
| **スケジュールされたスキャンを実行する時刻** | 定期的にスケジュールされたウイルス対策スキャンを実行する時間を選択します。 |
| **低パフォーマンスを使用する** | この設定は既定でオフになっています。 *この設定はオフにしておくことをお勧めします。* ただし、この設定をオンにすると、スケジュールされたスキャン中に使用されるデバイスのメモリとリソースを制限できます。 **大事な****[低パフォーマンスの使用**] をオンにすると、Microsoft Defender ウイルス対策の次の設定が構成されます。<ul><li>アーカイブ ファイルはスキャンされません ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning))。</li><li>スキャンには低い CPU 優先度 ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)) が割り当てられます。</li><li>完全なウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan))。</li><li>クイックウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan))。</li><li>ウイルス対策スキャン中の平均 CPU 負荷率を 50% から 20% ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)) に減らします。</li></ul> |
| **ユーザーの操作性**   |  |
| **Windows セキュリティ アプリへのアクセスをユーザーに許可する** | この設定をオンにすると、ユーザーがデバイスでWindows セキュリティ アプリを開くことができるようになります。 ユーザーは Defender for Business で構成した設定をオーバーライドすることはできませんが、クイック スキャンを実行したり、検出された脅威を表示したりできます。 |
| **ウイルス対策の除外** | 除外は、Microsoft Defender ウイルス対策スキャンによってスキップされるプロセス、ファイル、またはフォルダーです。 *一般に、除外を定義する必要はありません。* Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作と一般的な管理ファイルに基づく多くの自動除外が含まれています。 [除外の詳細については、こちらを参照してください](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md)。 |
| **プロセスの除外** | プロセスの除外により、特定のプロセスによって開かれたファイルが Microsoft Defender ウイルス対策によってスキャンされなくなります。 [プロセスの除外の詳細について説明します](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。 |
| **ファイル拡張子の除外** | ファイル拡張子の除外により、特定の拡張子を持つファイルが Microsoft Defender ウイルス対策によってスキャンされなくなります。 [ファイル拡張子の除外の詳細について説明します](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 |
| **ファイルとフォルダーの除外** | ファイルとフォルダーの除外により、特定のフォルダー内のファイルが Microsoft Defender ウイルス対策によってスキャンされなくなります。 [ファイルとフォルダーの除外の詳細について説明します](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Defender for Business のその他の事前構成済み設定

Defender for Business では、次のセキュリティ設定が事前構成されています。

- リムーバブル ドライブのスキャンがオンになっている ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning))。
- 毎日のクイック スキャンには、事前設定された時刻 ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)) がありません。
- セキュリティ インテリジェンスの更新は、ウイルス対策スキャンが実行される前にチェックされます ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan))。
- セキュリティ インテリジェンスチェックは 4 時間ごとに行われます ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval))。

## <a name="defender-for-business-default-settings-and-microsoft-intune"></a>Defender for Business の既定の設定とMicrosoft Intune

次の表では、Defender for Business 用に事前構成された設定と、それらの設定が Intune (Microsoft エンドポイント マネージャー 管理センターで管理されている) に表示される内容にどのように対応するかを示します。 [Defender for Business で簡略化された構成プロセス](mdb-simplified-configuration.md)を使用している場合は、これらの設定を編集する必要はありません。

| Setting  | 説明  |
|---------|---------|
| [クラウド保護](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | クラウド配信保護または Microsoft Advanced Protection Service (MAPS) とも呼ばれることもあります。クラウド保護は、Microsoft Defender ウイルス対策と Microsoft クラウドと連携して、新しい脅威を特定します。場合によっては、1 台のデバイスが影響を受ける前であってもです。 既定では、 [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) がオンになっています。 [クラウド保護の詳細については、こちらを参照してください](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md)。         |
| [受信ファイルと送信ファイルの監視](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | 受信ファイルと送信ファイルを監視するために、 [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) はすべてのファイルを監視するように設定されています。         |
| [ネットワーク ファイルをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | 既定では、 [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) は有効ではなく、ネットワーク ファイルはスキャンされません。 |
| [電子メール メッセージをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | 既定では、 [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) は有効ではなく、電子メール メッセージはスキャンされません。 |
| [検疫されたマルウェアを保持する日数 (0 ~ 90)](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | 既定では、 [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) 設定はゼロ (0) 日に設定されます。 検疫中のアーティファクトは自動的に削除されません。  |
| [サンプルの同意を送信する](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | 既定では、 [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) は安全なサンプルを自動的に送信するように設定されています。 安全なサンプルの例には`.bat`、`.dll``.scr`個人を特定できる情報 (PII) が含まれていないファイル、`.exe`ファイルなどがあります。 ファイルに PII が含まれている場合、ユーザーは、サンプルの送信の続行を許可する要求を受け取ります。 [クラウド保護とサンプル送信の詳細について説明します](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md)。 |
| [リムーバブル ドライブをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | 既定では、 [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) は、デバイス上の USB サム ドライブなどのリムーバブル ドライブをスキャンするように構成されています。 [マルウェア対策ポリシーの設定の詳細について説明します](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)。   |
| [毎日のクイック スキャン時間を実行する](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | 既定では、 [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) は午前 2 時に設定されます。 [スキャン設定の詳細については、こちらを参照してください](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。   |
| [スキャンを実行する前に署名の更新を確認する](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | 既定では、 [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) は、ウイルス対策/マルウェア対策スキャンを実行する前にセキュリティ インテリジェンス更新プログラムをチェックするように構成されています。 スキャン設定と[セキュリティ インテリジェンスの更新の](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)[詳細について説明](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)します。   |
| [セキュリティ インテリジェンスの更新プログラムを確認する頻度 (0 ~ 24 時間)](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | 既定では、 [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) は、セキュリティ インテリジェンスの更新プログラムを 4 時間ごとにチェックするように構成されています。 スキャン設定と[セキュリティ インテリジェンスの更新の](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)[詳細について説明](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)します。 |


## <a name="next-steps"></a>次の手順

- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)


## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender ポータルにアクセスする](mdb-get-started.md)
- [Defender for Business でファイアウォール設定を管理する](mdb-custom-rules-firewall.md)
- [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender)
