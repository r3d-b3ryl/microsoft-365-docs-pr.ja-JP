---
title: 攻撃面の減少ルールをカスタマイズする
description: 監査モード、ブロック モード、または無効モードでルールを個別に設定し、攻撃表面の縮小ルールから除外する必要があるファイルとフォルダーを追加する
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、カスタマイズ、構成、除外
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 232f7133f177e3d0aa93fcb2835fb86bcfd0d37c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769325"
---
# <a name="customize-attack-surface-reduction-rules"></a>攻撃面の減少ルールをカスタマイズする

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[攻撃表面の縮小ルールは](enable-attack-surface-reduction.md) 、デバイスやネットワークを侵害するために悪用されるソフトウェアの動作を防ぐのに役立ちます。 たとえば、攻撃者が署名されていないスクリプトを USB ドライブから実行したり、Office ドキュメント内のマクロで Win32 API を直接呼び出したりする可能性があります。 攻撃表面の縮小ルールは、このような危険な動作を制限し、組織の防御態勢を向上させる可能性があります。

ファイルとフォルダーを除外するか、ユーザーの[](#exclude-files-and-folders)コンピューターに表示される通知[](#customize-the-notification)通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズする方法について説明します。

次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。
- Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)グループ ポリシー、PowerShell、およびモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、これらの設定を構成できます。

## <a name="exclude-files-and-folders"></a>ファイルとフォルダーを除外する

ファイルとフォルダーを攻撃表面の縮小ルールによって評価される対象から除外できます。 除外されると、攻撃表面の縮小ルールでファイルに悪意のある動作が含まれていると検出された場合でも、ファイルの実行がブロックされません。

> [!WARNING]
> これにより、安全でないファイルを実行してデバイスに感染する可能性があります。 ファイルやフォルダーを除外すると、攻撃面の減少ルールで指定された保護機能が著しく低下します。 ルールによってブロックされたファイルの実行が許可され、レポートやイベントは記録されません。

除外は、除外を許可するすべてのルールに適用されます。 リソースの個別のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。 ただし、除外を特定のルールに制限することはできません。

除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。

攻撃表面の縮小は、環境変数とワイルドカードをサポートします。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する [」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。
検出すべきではないと思うファイルを検出するルールで問題が発生した場合は、監査モードを使用して [ルールをテストします](evaluate-attack-surface-reduction.md)。

| ルールの説明 | GUID |
|:----|:----|:----|
| すべてのアプリケーションOffice子プロセスの作成をブロックする | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| 難読化される可能性のあるスクリプトの実行をブロックする | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| Win32 API 呼び出しをブロックOfficeマクロ | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| 実行可能Office作成するアプリケーションのブロック | `3B576869-A4EC-4529-8536-B80A7769E899` |
| アプリケーションOffice他のプロセスへのコードの挿入をブロックする | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| メール クライアントと Web メールから実行可能なコンテンツをブロックする | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| 有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| ランサムウェアに対する高度な保護の使用 | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| PSExec および WMI コマンドから発生するプロセス作成をブロックする | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| 通信Office子プロセスの作成をブロックする | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| Adobe Reader の子プロセスの作成をブロックする | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| WMI イベント サブスクリプションによる永続化のブロック | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

各ルールの [詳細については、攻撃表面](attack-surface-reduction.md) の縮小に関するトピックを参照してください。

### <a name="use-group-policy-to-exclude-files-and-folders"></a>グループ ポリシーを使用してファイルとフォルダーを除外する

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **、Exploit Guard 攻撃Windows縮小**  >    >  **Microsoft Defender ウイルス対策Windows Defenderコンポーネント**  >  **を展開します**。

4. [攻撃表面の縮小 **ルールからファイル** とパスを除外する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。 各 **アイテムの [** 値] **列に 0** を入力します。

> [!WARNING]
> [値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。

### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell を使用してファイルとフォルダーを除外する

1. [**スタート] メニューに「powershell」** と入力し、[管理者 **Windows PowerShellを右** クリックし、[管理者として **実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにフォルダーを追加します。

> [!IMPORTANT]
> リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM CSP を使用してファイルとフォルダーを除外する

除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。

## <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされた場合の通知をカスタマイズし、アプリまたはファイルをブロックできます。 詳しくは[、Windows セキュリティをご覧](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)ください。

## <a name="related-topics"></a>関連項目

* [攻撃表面の縮小ルールを使用して攻撃表面を削減する](attack-surface-reduction.md)
* [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
* [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
* [攻撃面の減少の FAQ](attack-surface-reduction.md)
