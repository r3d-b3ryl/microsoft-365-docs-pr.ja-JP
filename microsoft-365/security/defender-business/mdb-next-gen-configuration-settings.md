---
title: Microsoft Defender for Business の次世代保護構成設定について (プレビュー)
description: Microsoft Defender for Business の次世代保護の構成設定について (プレビュー)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: ab2d82c3b5db6b114b8172e0f4bf4aa3658eb28a
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507244"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business の次世代の構成設定について (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) の次世代保護には、堅牢なウイルス対策およびマルウェア対策保護が含まれています。 既定のポリシーは、生産性を妨げることなくデバイスとユーザーを保護するように設計されています。ただし、ビジネス ニーズに合わせてポリシーをカスタマイズすることもできます。 

**この記事では、以下について説明します**。

- [次世代の保護の設定とオプション](#next-generation-protection-settings-and-options)
- [その他の事前構成済み設定](#additional-preconfigured-settings) 

## <a name="next-generation-protection-settings-and-options"></a>次世代の保護の設定とオプション

次の表に、設定とオプションの一覧を示します。<br/><br/>

| Setting | 説明 |
|:---|:---|
| **リアルタイム保護**  |  |
| **リアルタイム保護を有効にする** | 既定で有効になっているリアルタイム保護は、デバイス上でマルウェアが実行されるのを見つけて停止します。 *リアルタイム保護を有効にすることをお勧めします。*<br/><br/>リアルタイム保護を有効にすると、次の設定が構成されます。<br/>- 動作の監視がオンになっている[(AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender))<br/>- ダウンロードしたファイルと添付ファイルはすべてスキャンされます ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender))<br/>- Microsoft ブラウザーで使用されるスクリプトがスキャンされます ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender))   |
| **事前ブロック** | 既定で有効にすると、検出から数秒でマルウェアがブロックされ、分析用にサンプル ファイルを送信できる時間 (秒) が増加し、検出レベルが High に設定されます。 *一目でブロックをオンにすることをお勧めします。*<br/><br/>一目でブロックをオンにすると、次の設定が行Microsoft Defender ウイルス対策。 <br/>- 疑わしいファイルのブロックとスキャンが高ブロック レベル ([CloudBlockLevel ) に設定されている](/windows/client-management/mdm/policy-csp-defender)<br/>- ブロックおよびチェックするファイルの秒の数を 50 秒に設定します ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender)) <br/><br/>**重要**: 一目でブロックをオフにすると、ブロックが影響を受け `CloudBlockLevel` `CloudExtendedTimeout` 、Microsoft Defender ウイルス対策。  |
| **ネットワーク保護を有効にする** | オンにすると、ネットワーク保護は、インターネット上のフィッシング詐欺、悪用ホスティング サイト、悪意のあるコンテンツから保護するのに役立ちます。 また、ユーザーはネットワーク保護をオフにできます。<br/><br/>ネットワーク保護は、次のいずれかのモードに設定できます。<br/>- **ブロック モード** (この設定は既定) で、ユーザーが安全でないと見なされるサイトにアクセスできません。 *ネットワーク保護をブロック モードに設定することをお勧めします。*<br/>- **ユーザーが安全** でない可能性があるサイトにアクセスし、そのようなサイトとの間でネットワーク アクティビティを追跡できる監査モード <br/>- **無効モード**:安全でない可能性のあるサイトへのアクセスや、そのようなサイトとの間のネットワーク アクティビティの追跡を行うユーザーをブロックするネザー モード |
| **修復**  |  |
| **望ましくない可能性のあるアプリに対するアクション (PUA)** | PUA には、広告ソフトウェア、署名されていない他のソフトウェアのインストールを提供するバンドル ソフトウェア、およびセキュリティ機能を回避しようとする回避ソフトウェアが含まれます。 PUA は必ずしもウイルス、マルウェア、その他の種類の脅威とは限りませんが、PUA はデバイスのパフォーマンスに影響を与える可能性があります。<br/><br/>PUA 保護は、PUA として検出されたアイテムをブロックします。 PUA 保護は、次のいずれかの設定に設定できます。 <br/>- **有効** (この設定は既定)、デバイスで PUA として検出されたアイテムをブロックします。 *PUA 保護を有効にすることをお勧めします。*<br/>- **監査モード**(PUA として検出されたアイテムに対してアクションを実行しません) <br/>- **無効**(PUA の可能性があるアイテムを検出または実行しない) |
| **スキャン**   |  |
| **スケジュールされたスキャンの種類** | デバイスで毎週ウイルス対策スキャンを実行する方法を検討してください。 次のスキャンの種類のオプションから選択できます。 <br/>- **クイックスキャンは** 、レジストリ キーやスタートアップ フォルダーなどの場所をチェックします。マルウェアを登録してデバイスから開始できます。 *クイックスキャン オプションの使用をお勧めします。* <br/>- **Fullscan は** 、デバイス上のすべてのファイルとフォルダーをチェックします。 <br/>- **無効にすると** 、スケジュールされたスキャンは実行されません。 ユーザーは、自分のデバイスでスキャンを実行できます。 (一般に、スケジュールされたスキャンを無効にすることをお勧めしません。 <br/><br/> [スキャンの種類について詳しくは、以下を参照してください](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **スケジュールされたスキャンを実行する週の日** | 定期的な毎週のウイルス対策スキャンを実行する日を選択します。 |
| **スケジュールされたスキャンを実行する時刻** | 定期的にスケジュールされたウイルス対策スキャンを実行する時間を選択します。 |
| **低パフォーマンスの使用** | この設定は既定でオフになっています。 *この設定をオフにすることをお勧めします。* ただし、この設定をオンにすると、スケジュールされたスキャン中に使用されるデバイス のメモリとリソースを制限できます。 <br/><br/>**大事な**[低パフォーマンスを **使用する] をオン** にした場合は、次の設定を構成Microsoft Defender ウイルス対策。 <br/>- アーカイブ ファイルがスキャンされない ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender))<br/>- スキャンには CPU 優先度が低い[(EnableLowCPUPriority ) が割り当てられます](/windows/client-management/mdm/policy-csp-defender)。 <br/>- 完全なウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません[(DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender)) <br/>- クイック ウイルス対策スキャンが見つからない場合、キャッチアップ スキャンは実行されません[(DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender)) <br/>- ウイルス対策スキャン中の平均 CPU 負荷率を 50% から 20% に減少します ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender)) |
| **ユーザーの操作性**   |  |
| **ユーザーがアプリにアクセスWindows セキュリティする** | この設定をオンにすると、ユーザーはデバイスでアプリWindows セキュリティ開くことができる。 ユーザーは、Microsoft Defender for Business (プレビュー) で構成した設定を上書きできますが、必要に応じてクイック スキャンを実行したり、検出された脅威を表示したりできます。 |
| **ウイルス対策の除外** | 除外は、スキャンによってスキップされるプロセス、ファイル、またはMicrosoft Defender ウイルス対策です。 *一般に、除外を定義する必要はない必要があります。* Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作と一般的な管理ファイルに基づく多くの自動除外が含まれます。<br/><br/>[除外の詳細](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **プロセスの除外** | プロセスの除外により、特定のプロセスによって開いたファイルが、特定のプロセスによってスキャンMicrosoft Defender ウイルス対策。 <br/><br/>[プロセスの除外の詳細](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイル拡張子の除外** | ファイル拡張子の除外により、特定の拡張子を持つファイルがファイルのスキャンMicrosoft Defender ウイルス対策。<br/><br/>[ファイル拡張子の除外の詳細](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **ファイルとフォルダーの除外** | ファイルとフォルダーの除外により、特定のフォルダー内のファイルがユーザーによってスキャンMicrosoft Defender ウイルス対策。 <br/><br/>[ファイルとフォルダーの除外の詳細](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="additional-preconfigured-settings"></a>その他の事前構成済み設定

Defender for Business (プレビュー) の次世代保護のために、次の追加設定が事前構成されています。

- リムーバブル ドライブのスキャンが有効になっている ([AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender))
- 毎日のクイック スキャンには、あらかじめ設定された時間[(ScheduleQuickScanTime ) が設定されていない](/windows/client-management/mdm/policy-csp-defender)
- ウイルス対策スキャンが実行される前にセキュリティ インテリジェンスの更新プログラムがチェックされます[(CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender))
- セキュリティ インテリジェンスチェックは 4 時間ごとに行われます ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender))

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)


## <a name="see-also"></a>関連項目

- [ポータルにアクセスMicrosoft 365 Defenderする](mdb-get-started.md)

- [Microsoft Defender for Business のファイアウォール設定を管理する (プレビュー)](mdb-custom-rules-firewall.md)

- [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender)