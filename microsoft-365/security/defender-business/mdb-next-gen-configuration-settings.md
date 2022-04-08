---
title: Microsoft Defender for Businessの次世代の保護構成設定を理解する
description: Microsoft Defender for Businessでの次世代保護の構成設定について理解する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: a39a0a55592ba8f76403f9e8d9aaf7416cb35228
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714243"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessで次世代の構成設定を理解する

> [!IMPORTANT]
> Microsoft Defender for Businessは、2022 年 3 月 1 日以降、[Microsoft 365 Business Premium](../../business-premium/index.md)のお客様に展開されます。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー段階にあり、 [ここにサインアップ](https://aka.ms/mdb-preview) して要求する顧客と IT パートナーに段階的にロールアウトされます。 プレビューには [シナリオの初期セット](mdb-tutorials.md#try-these-preview-scenarios)が含まれており、定期的に機能を追加します。
> 
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。 

Defender for Business の次世代保護には、堅牢なウイルス対策とマルウェア対策の保護が含まれています。 既定のポリシーは、生産性を妨げることなくデバイスとユーザーを保護するように設計されています。ただし、ビジネス ニーズに合わせてポリシーをカスタマイズすることもできます。 また、Microsoft エンドポイント マネージャーを使用している場合は、これを使用してセキュリティ ポリシーを管理できます。

**この記事では、次について説明します**。

- [次世代の保護の設定とオプション](#next-generation-protection-settings-and-options)

- [Defender for Business のその他の事前構成済み設定](#other-preconfigured-settings-in-defender-for-business) 

- [Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー](#defender-for-business-default-settings-and-microsoft-endpoint-manager)

## <a name="next-generation-protection-settings-and-options"></a>次世代の保護の設定とオプション

次の表に、設定とオプションの一覧を示します。<br/><br/>

| 設定 | 説明 |
|:---|:---|
| **リアルタイム保護**:  |  |
| **リアルタイム保護を有効にする** | 既定で有効にすると、リアルタイム保護によって、マルウェアがデバイスで実行されるのを見つけて停止します。 *リアルタイム保護を有効にしておくことをお勧めします。*<br/><br/>リアルタイム保護を有効にすると、次の設定が構成されます。<br/>- 動作の監視が有効になっている ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring))<br/>- ダウンロードしたすべてのファイルと添付ファイルがスキャンされます ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection))<br/>- Microsoft ブラウザーで使用されるスクリプトがスキャンされます ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))   |
| **事前ブロック** | 既定で有効にすると、一目でブロックすると、検出から数秒でマルウェアがブロックされ、分析のためにサンプル ファイルを送信できる時間 (秒単位) が長くなり、検出レベルが高に設定されます。 *一目でブロックを有効にしておくことをお勧めします。*<br/><br/>一目でブロックを有効にすると、Microsoft Defender ウイルス対策に対して次の設定が構成されます。 <br/>- 疑わしいファイルのブロックとスキャンが高ブロック レベル ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)) に設定されている<br/>- ファイルをブロックしてチェックする秒数を 50 秒に設定します ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)) <br/><br/>**重要**: 一目でブロックがオフになっている場合は、Microsoft Defender ウイルス対策に影響`CloudBlockLevel``CloudExtendedTimeout`します。  |
| **ネットワーク保護を有効にする** | オンにすると、ネットワーク保護は、フィッシング詐欺、悪用ホスティング サイト、インターネット上の悪意のあるコンテンツから保護するのに役立ちます。 また、ユーザーがネットワーク保護をオフにすることを防ぎます。<br/><br/>ネットワーク保護は、次のいずれかのモードに設定できます。<br/>- **ブロック モード** (この設定は既定)、ユーザーが安全でないと見なされるサイトにアクセスできないようにします。 *ネットワーク保護をブロック モードに設定しておくことをお勧めします。*<br/>- ユーザーが安全でない可能性があるサイトにアクセスし、そのようなサイトとの間でネットワーク アクティビティを追跡できる **監査モード** <br/>- **無効モード**。ユーザーが安全でない可能性のあるサイトへのアクセスをブロックしたり、そのようなサイトとの間でネットワーク アクティビティを追跡したりする |
| **修復**  |  |
| **望ましくない可能性があるアプリに対して実行するアクション (PUA)** | PUA には、広告ソフトウェア、他の署名されていないソフトウェアのインストールを提供するバンドル ソフトウェア、セキュリティ機能を回避しようとする回避ソフトウェアを含めることができます。 PUA は必ずしもウイルス、マルウェア、またはその他の種類の脅威ではありませんが、PUA はデバイスのパフォーマンスに影響を与える可能性があります。<br/><br/>PUA 保護は、PUA として検出されたアイテムをブロックします。 PUA 保護は、次のいずれかの設定に設定できます。 <br/>- **デバイス** で PUA として検出された項目をブロックする有効 (この設定が既定です)。 *PUA 保護を有効にしておくことをお勧めします。*<br/>- **PUA** として検出された項目に対してアクションを実行しない監査モード <br/>- **無効になっています**。PUA である可能性のある項目に対して検出またはアクションを実行しません。 |
| **スキャン**   |  |
| **スケジュールされたスキャンの種類** | デバイスで毎週のウイルス対策スキャンを実行することを検討してください。 次のスキャンの種類のオプションから選択できます。 <br/>- **クイックスキャンは** 、レジストリ キーやスタートアップ フォルダーなどの場所をチェックします。デバイスから起動するためにマルウェアを登録できます。 *クイックスキャン オプションを使用することをお勧めします。* <br/>- **Fullscan は** 、デバイス上のすべてのファイルとフォルダーをチェックします <br/>- **無効にすると** 、スケジュールされたスキャンは行われません。 ユーザーは自分のデバイスでスキャンを実行できます。 (一般に、スケジュールされたスキャンを無効にすることはお勧めしません)。) <br/><br/> [スキャンの種類の詳細については、こちらを参照してください](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **スケジュールされたスキャンを実行する曜日** | 定期的な毎週のウイルス対策スキャンを実行する日を選択します。 |
| **スケジュールされたスキャンを実行する時刻** | 定期的にスケジュールされたウイルス対策スキャンを実行する時間を選択します。 |
| **低パフォーマンスを使用する** | この設定は既定でオフになっています。 *この設定はオフにしておくことをお勧めします。* ただし、この設定をオンにすると、スケジュールされたスキャン中に使用されるデバイス のメモリとリソースを制限できます。 <br/><br/>**大事な****[低パフォーマンスの使用**] をオンにすると、Microsoft Defender ウイルス対策に対して次の設定が構成されます。 <br/>- アーカイブ ファイルがスキャンされない ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning))<br/>- スキャンには低い CPU 優先度が割り当てられます ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)) <br/>- 完全なウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan)) <br/>- クイックウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan)) <br/>- ウイルス対策スキャン中の平均 CPU 負荷率を 50% から 20% に減らす ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)) |
| **ユーザーの操作性**   |  |
| **Windows セキュリティ アプリへのアクセスをユーザーに許可する** | この設定をオンにすると、ユーザーがデバイスでWindows セキュリティ アプリを開くことができるようになります。 ユーザーはMicrosoft Defender for Businessで構成した設定をオーバーライドすることはできませんが、必要に応じてクイック スキャンを実行したり、検出された脅威を表示したりできます。 |
| **ウイルス対策の除外** | 除外は、Microsoft Defender ウイルス対策 スキャンによってスキップされるプロセス、ファイル、またはフォルダーです。 *一般に、除外を定義する必要はありません。* Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作と一般的な管理ファイルに基づく多くの自動除外が含まれます。<br/><br/>[除外の詳細を確認する](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **プロセスの除外** | プロセスの除外により、特定のプロセスによって開かれたファイルがMicrosoft Defender ウイルス対策によってスキャンされなくなります。 <br/><br/>[プロセスの除外の詳細を確認する](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイル拡張子の除外** | ファイル拡張子の除外により、特定の拡張子を持つファイルがMicrosoft Defender ウイルス対策によってスキャンされなくなります。<br/><br/>[ファイル拡張子の除外の詳細](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイルとフォルダーの除外** | ファイルとフォルダーの除外は、特定のフォルダー内のファイルがMicrosoft Defender ウイルス対策によってスキャンされないようにします。 <br/><br/>[ファイルとフォルダーの除外の詳細を確認する](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Defender for Business のその他の事前構成済み設定

Defender for Business では、次のセキュリティ設定が事前構成されています。

- リムーバブル ドライブのスキャンが有効になっている ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning))

- 毎日のクイック スキャンに事前設定された時刻がない ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime))

- ウイルス対策スキャンの実行前にセキュリティ インテリジェンス更新プログラムがチェックされます ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan))

- セキュリティ インテリジェンスチェックは 4 時間ごとに行われます ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval))

## <a name="defender-for-business-default-settings-and-microsoft-endpoint-manager"></a>Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー

次の表では、Defender for Business 用に事前構成された設定と、それらの設定がMicrosoft エンドポイント マネージャー (またはMicrosoft Intune) に表示される内容にどのように対応するかについて説明します。 Defender for Business (プレビュー) [で簡略化された構成プロセス](mdb-simplified-configuration.md) を使用している場合は、これらの設定を編集する必要はありません。
<br/><br/>

| 設定  | 説明  |
|---------|---------|
| [クラウド保護](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | クラウド配信保護または Microsoft Advanced Protection Service (MAPS) とも呼ばれることもあります。クラウド保護は、Microsoft Defender ウイルス対策と Microsoft クラウドと連携して、新しい脅威を特定します。場合によっては、1 台のデバイスが影響を受ける前であってもです。 既定では、 [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) がオンになっています。 <br/><br/>[クラウド保護の詳細については、こちらを参照してください](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md)。         |
| [受信ファイルと送信ファイルの監視](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | 受信ファイルと送信ファイルを監視するために、 [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) はすべてのファイルを監視するように設定されています。         |
| [ネットワーク ファイルをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | 既定では、 [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) は有効ではなく、ネットワーク ファイルはスキャンされません。 |
| [電子メール メッセージをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | 既定では、 [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) は有効ではなく、電子メール メッセージはスキャンされません。 |
| [検疫されたマルウェアを保持する日数 (0 ~ 90)](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | 既定では、 [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) この設定はゼロ (0) 日に設定されます。 検疫内のArtifactsは自動的に削除されません。  |
| [サンプルの同意を送信する](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | 既定では、 [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) は安全なサンプルを自動的に送信するように設定されています。 安全なサンプルの例には`.bat`、`.dll``.scr`個人を特定できる情報 (PII) が含まれていないファイル、`.exe`ファイルなどがあります。 ファイルに PII が含まれている場合、ユーザーは、サンプルの送信の続行を許可する要求を受け取ります。<br/><br/>[クラウド保護とサンプル送信の詳細を確認する](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [リムーバブル ドライブをスキャンする](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | 既定では、 [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) は、デバイス上の USB サム ドライブなどのリムーバブル ドライブをスキャンするように構成されています。<br/><br/>[マルウェア対策ポリシー設定の詳細を確認する](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [毎日のクイック スキャン時間を実行する](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | 既定では、 [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) は午前 2 時に設定されます。<br/><br/>[スキャン設定の詳細については、こちらを参照してください](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。   |
| [スキャンを実行する前に署名の更新を確認する](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | 既定では、 [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) は、ウイルス対策/マルウェア対策スキャンを実行する前にセキュリティ インテリジェンス更新プログラムをチェックするように構成されています。<br/><br/>スキャン設定と[セキュリティ インテリジェンスの更新の](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)[詳細について説明](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)します。   |
| [セキュリティ インテリジェンスの更新プログラムを確認する頻度 (0 ~ 24 時間)](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | 既定では、 [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) は、セキュリティ インテリジェンスの更新プログラムを 4 時間ごとにチェックするように構成されています。<br/><br/>スキャン設定と[セキュリティ インテリジェンスの更新の](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)[詳細について説明](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)します。 |


## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)


## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender ポータルにアクセスする](mdb-get-started.md)

- [Microsoft Defender for Businessでファイアウォール設定を管理する](mdb-custom-rules-firewall.md)

- [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender)
