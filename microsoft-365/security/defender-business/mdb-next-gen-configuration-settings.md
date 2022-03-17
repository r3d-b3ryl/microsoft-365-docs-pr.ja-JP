---
title: Microsoft Defender for Business の次世代保護構成設定について
description: Microsoft Defender for Business の次世代保護の構成設定について
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
ms.openlocfilehash: 263d6457c8e913bdd3d8224af71f201156e24b5a
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525558"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>Microsoft Defender for Business の次世代の構成設定について

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Defender for Business の次世代保護には、堅牢なウイルス対策およびマルウェア対策保護が含まれます。 既定のポリシーは、生産性を妨げることなくデバイスとユーザーを保護するように設計されています。ただし、ビジネス ニーズに合わせてポリシーをカスタマイズすることもできます。 また、セキュリティ ポリシーを使用しているMicrosoft エンドポイント マネージャー、セキュリティ ポリシーを管理するために使用できます。

**この記事では、次の情報について説明します**。

- [次世代の保護の設定とオプション](#next-generation-protection-settings-and-options)

- [Defender for Business のその他の事前構成済み設定](#other-preconfigured-settings-in-defender-for-business) 

- [Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー](#defender-for-business-default-settings-and-microsoft-endpoint-manager)

## <a name="next-generation-protection-settings-and-options"></a>次世代の保護の設定とオプション

次の表に、設定とオプションの一覧を示します。<br/><br/>

| Setting | 説明 |
|:---|:---|
| **リアルタイム保護**  |  |
| **リアルタイム保護を有効にする** | 既定で有効になっているリアルタイム保護は、デバイス上でマルウェアが実行されるのを見つけて停止します。 *リアルタイム保護を有効にすることをお勧めします。*<br/><br/>リアルタイム保護を有効にすると、次の設定が構成されます。<br/>- 動作の監視が有効になっている ([AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring))<br/>- ダウンロードしたファイルと添付ファイルはすべてスキャンされます ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection))<br/>- Microsoft ブラウザーで使用されるスクリプトがスキャンされます ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))   |
| **事前ブロック** | 既定で有効にすると、検出から数秒でマルウェアがブロックされ、分析用にサンプル ファイルを送信できる時間 (秒) が増加し、検出レベルが High に設定されます。 *一目でブロックをオンにすることをお勧めします。*<br/><br/>一目でブロックをオンにすると、次の設定が行Microsoft Defender ウイルス対策。 <br/>- 疑わしいファイルのブロックとスキャンが高ブロック レベル ([CloudBlockLevel) に設定されている](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)<br/>- ブロックおよびチェックするファイルの秒の数を 50 秒に設定します ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout)) <br/><br/>**重要**: 一目でブロックをオフにすると、ブロックが`CloudBlockLevel``CloudExtendedTimeout`影響を受け、Microsoft Defender ウイルス対策。  |
| **ネットワーク保護を有効にする** | オンにすると、ネットワーク保護は、インターネット上のフィッシング詐欺、悪用ホスティング サイト、悪意のあるコンテンツから保護するのに役立ちます。 また、ユーザーはネットワーク保護をオフにできます。<br/><br/>ネットワーク保護は、次のいずれかのモードに設定できます。<br/>- **ブロック モード** (この設定は既定) で、ユーザーが安全でないと見なされるサイトにアクセスできません。 *ネットワーク保護をブロック モードに設定することをお勧めします。*<br/>- **ユーザーが安全** でない可能性があるサイトにアクセスし、そのようなサイトとの間でネットワーク アクティビティを追跡できる監査モード <br/>- **無効モード**:安全でない可能性のあるサイトへのアクセスや、そのようなサイトとの間のネットワーク アクティビティの追跡を行うユーザーをブロックするネザー モード |
| **修復**  |  |
| **望ましくない可能性のあるアプリに対するアクション (PUA)** | PUA には、広告ソフトウェア、署名されていない他のソフトウェアのインストールを提供するバンドル ソフトウェア、およびセキュリティ機能を回避しようとする回避ソフトウェアが含まれます。 PUA は必ずしもウイルス、マルウェア、その他の種類の脅威とは限りませんが、PUA はデバイスのパフォーマンスに影響を与える可能性があります。<br/><br/>PUA 保護は、PUA として検出されたアイテムをブロックします。 PUA 保護は、次のいずれかの設定に設定できます。 <br/>- **有効** (この設定は既定)、デバイスで PUA として検出されたアイテムをブロックします。 *PUA 保護を有効にすることをお勧めします。*<br/>- **監査モード**(PUA として検出されたアイテムに対してアクションを実行しません) <br/>- **無効**(PUA の可能性があるアイテムを検出または実行しない) |
| **スキャン**   |  |
| **スケジュールされたスキャンの種類** | デバイスで毎週ウイルス対策スキャンを実行する方法を検討してください。 次のスキャンの種類のオプションから選択できます。 <br/>- **クイックスキャンは** 、レジストリ キーやスタートアップ フォルダーなどの場所をチェックします。マルウェアを登録してデバイスから開始できます。 *クイックスキャン オプションの使用をお勧めします。* <br/>- **Fullscan は** 、デバイス上のすべてのファイルとフォルダーをチェックします。 <br/>- **無効にすると** 、スケジュールされたスキャンは実行されません。 ユーザーは、自分のデバイスでスキャンを実行できます。 (一般に、スケジュールされたスキャンを無効にすることをお勧めしません)。 <br/><br/> [スキャンの種類について詳しくは、以下を参照してください](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **スケジュールされたスキャンを実行する週の日** | 定期的な毎週のウイルス対策スキャンを実行する日を選択します。 |
| **スケジュールされたスキャンを実行する時刻** | 定期的にスケジュールされたウイルス対策スキャンを実行する時間を選択します。 |
| **低パフォーマンスの使用** | この設定は既定でオフになっています。 *この設定をオフにすることをお勧めします。* ただし、この設定をオンにすると、スケジュールされたスキャン中に使用されるデバイス のメモリとリソースを制限できます。 <br/><br/>**大事な**[低パフォーマンスを **使用する] をオン** にした場合は、次の設定を構成Microsoft Defender ウイルス対策。 <br/>- アーカイブ ファイルがスキャンされない ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning))<br/>- スキャンには CPU 優先度が低く割り当てられます ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority)) <br/>- 完全なウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan)) <br/>- クイック ウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません ([DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan)) <br/>- ウイルス対策スキャン中の平均 CPU 負荷率を 50% から 20% に減少します ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor)) |
| **ユーザーの操作性**   |  |
| **ユーザーがアプリにアクセスWindows セキュリティする** | この設定をオンにすると、ユーザーはデバイスでアプリWindows セキュリティ開くことができる。 ユーザーは Microsoft Defender for Business で構成した設定を上書きできますが、必要に応じてクイック スキャンを実行したり、検出された脅威を表示したりできます。 |
| **ウイルス対策の除外** | 除外は、スキャンによってスキップされるプロセス、ファイル、またはMicrosoft Defender ウイルス対策です。 *一般に、除外を定義する必要はない必要があります。* Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作と一般的な管理ファイルに基づく多くの自動除外が含まれます。<br/><br/>[除外の詳細](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **プロセスの除外** | プロセスの除外により、特定のプロセスによって開いたファイルが、特定のプロセスによってスキャンMicrosoft Defender ウイルス対策。 <br/><br/>[プロセスの除外の詳細](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイル拡張子の除外** | ファイル拡張子の除外により、特定の拡張子を持つファイルがファイルのスキャンをMicrosoft Defender ウイルス対策。<br/><br/>[ファイル拡張子の除外の詳細](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイルとフォルダーの除外** | ファイルとフォルダーの除外により、特定のフォルダー内のファイルがユーザーによってスキャンMicrosoft Defender ウイルス対策。 <br/><br/>[ファイルとフォルダーの除外の詳細](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Defender for Business のその他の事前構成済み設定

Defender for Business では、以下のセキュリティ設定が事前構成されています。

- リムーバブル ドライブのスキャンが有効になっている ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning))

- 毎日のクイック スキャンに事前設定された時間が設定されている ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime))

- ウイルス対策スキャンが実行される前にセキュリティ インテリジェンスの更新プログラムがチェックされます ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan))

- セキュリティ インテリジェンスチェックは 4 時間ごとに行われます ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval))

## <a name="defender-for-business-default-settings-and-microsoft-endpoint-manager"></a>Defender for Business の既定の設定とMicrosoft エンドポイント マネージャー

次の表では、Defender for Business 用に事前構成されている設定と、これらの設定が Microsoft エンドポイント マネージャー (または Microsoft Intune) に表示される設定とどのように対応するかについて説明します。 Defender [for Business](mdb-simplified-configuration.md) (プレビュー) で簡略化された構成プロセスを使用している場合は、これらの設定を編集する必要があります。
<br/><br/>

| Setting  | 説明  |
|---------|---------|
| [クラウド保護](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | クラウド配信保護または Microsoft Advanced Protection Service (MAPS) と呼ばれる場合、クラウド保護は Microsoft Defender ウイルス対策 と Microsoft クラウドと一緒に動作し、単一のデバイスが影響を受ける前でも、新しい脅威を特定します。 既定では [、AllowCloudProtection は](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) オンになっています。 <br/><br/>[クラウド保護について詳しくは、次のリンクを参照してください](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md)。         |
| [受信ファイルと送信ファイルの監視](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | 受信ファイルと送信ファイルを監視するために、 [RealTimeScanDirection は、](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) すべてのファイルを監視するために設定されます。         |
| [ネットワーク ファイルのスキャン](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | 既定では [、AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) は有効になっていません。ネットワーク ファイルはスキャンされません。 |
| [電子メール メッセージのスキャン](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | 既定では [、AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) は有効になっていません。電子メール メッセージはスキャンされません。 |
| [検疫済みマルウェアを保持する日数 (0 ~ 90)](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | 既定では [、DaysToRetainCleanedMalware この](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) 設定はゼロ (0) 日に設定されています。 Artifactsで自動的に削除されない場合。  |
| [サンプルの同意を送信する](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | 既定では [、SubmitSamplesConsent は](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) 安全なサンプルを自動的に送信します。 安全なサンプルの例には、`.bat`個人`.dll``.scr``.exe`を特定できる情報 (PII) が含まれているファイル 、などです。 ファイルに PII が含まれている場合、ユーザーはサンプル提出の続行を許可する要求を受け取ります。<br/><br/>[クラウド保護とサンプル申請の詳細](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [リムーバブル ドライブのスキャン](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | 既定では [、AllowFullScanRemovableDriveScanning は](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) 、デバイス上の USB サム ドライブなどのリムーバブル ドライブをスキャンするように構成されています。<br/><br/>[マルウェア対策ポリシー設定の詳細](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [毎日のクイック スキャン時間の実行](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | 既定では [、ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) は午前 2:00 に設定されています。<br/><br/>[詳しくは、スキャン設定についてのページを参照してください](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。   |
| [スキャンを実行する前に署名の更新を確認する](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | 既定では、 [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) は、ウイルス対策/マルウェア対策スキャンを実行する前にセキュリティ インテリジェンスの更新プログラムを確認するように構成されています。<br/><br/>[詳しくは、スキャン設定とセキュリティ](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) [インテリジェンス更新プログラムをご覧ください](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。   |
| [セキュリティ インテリジェンスの更新プログラムを確認する頻度 (0 ~ 24 時間)](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | 既定では、 [SignatureUpdateInterval は](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) 4 時間ごとにセキュリティ インテリジェンス更新プログラムを確認するように構成されています。<br/><br/>[詳しくは、スキャン設定とセキュリティ](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) [インテリジェンス更新プログラムをご覧ください](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。 |


## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)


## <a name="see-also"></a>関連項目

- [ポータルにアクセスMicrosoft 365 Defenderする](mdb-get-started.md)

- [Microsoft Defender for Business でファイアウォール設定を管理する](mdb-custom-rules-firewall.md)

- [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender)