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
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bfdfd2badce75294376d6406ba3d3078f26a9857
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222865"
---
# <a name="customize-attack-surface-reduction-rules"></a>攻撃面の減少ルールをカスタマイズする

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

[攻撃表面の縮小ルールは](enable-attack-surface-reduction.md) 、デバイスやネットワークを侵害するために悪用されるソフトウェアの動作を防ぐのに役立ちます。 たとえば、攻撃者が署名されていないスクリプトを USB ドライブから実行したり、Office ドキュメント内のマクロで Win32 API を直接呼び出したりする可能性があります。 攻撃表面の縮小ルールは、このような危険な動作を制限し、組織の防御態勢を向上させる可能性があります。

ファイルとフォルダーを除外するか、ユーザーの[](#exclude-files-and-folders)コンピューターに表示される通知[](#customize-the-notification)通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズする方法について説明します。

次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。

- Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降
- Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

グループ ポリシー、PowerShell、およびモバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して、これらの設定を構成できます。

サポート [されるオペレーティング システムと](enable-attack-surface-reduction.md#requirements) 追加の要件情報については、「攻撃表面縮小ルールを有効にする」の記事の「要件」を参照してください。

## <a name="exclude-files-and-folders"></a>ファイルとフォルダーを除外する

ファイルとフォルダーを攻撃表面の縮小ルールによって評価される対象から除外できます。 除外すると、攻撃表面の縮小ルールでファイルに悪意のある動作が含まれていると検出された場合でも、ファイルの実行がブロックされません。

たとえば、次のランサムウェア ルールを考え出します。

ランサムウェア ルールは、企業のお客様がビジネスの継続性を確保しながら、ランサムウェア攻撃のリスクを軽減するために設計されています。 既定では、ランサムウェア ルールのエラーは注意の側で発生し、まだ十分な評価と信頼を得ていないファイルから保護します。 再フェーズを行う場合、ランサムウェア ルールは、何百万人もの顧客の利用状況指標に基づいて、十分な肯定的な評価と普及率を得てないファイルでのみトリガーされます。 通常、ブロックは自己解決されます。各ファイルの "評価と信頼" の値は、問題ない使用法が増えるほど段階的にアップグレードされます。

ブロックが自己解決されない場合、お客様は自己のリスクで、セルフサービス メカニズムまたは IOC (IOC) ベースの "許可リスト" 機能を利用して、ファイル自体のブロックを解除できます。 

> [!WARNING]
> ファイルまたはフォルダーのブロックを除外または解除すると、安全でないファイルが実行され、デバイスに感染する可能性があります。 ファイルやフォルダーを除外すると、攻撃面の減少ルールで指定された保護機能が著しく低下します。 ルールによってブロックされたファイルの実行が許可され、レポートやイベントは記録されません。

除外は、除外を許可するすべてのルールに適用されます。 リソースの個別のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。 ただし、除外を特定のルールに制限することはできません。

除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。

攻撃表面の縮小は、環境変数とワイルドカードをサポートします。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する [」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。
検出すべきではないと思うファイルを検出するルールで問題が発生した場合は、監査モードを使用して [ルールをテストします](evaluate-attack-surface-reduction.md)。

<br>

****

|ルールの説明|GUID|
|---|---|
|悪用された脆弱な署名済みドライバーの悪用をブロックする|`56a863a9-875e-4185-98a7-b882c64b5ce5`|
|Adobe Reader の子プロセスの作成をブロックする|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|
|すべてのアプリケーションOffice子プロセスの作成をブロックする|`d4f940ab-401b-4efc-aadc-ad5f3c50688a`|
|ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|
|メール クライアントと Web メールから実行可能なコンテンツをブロックする|`be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`|
|有病率、年齢、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする|`01443614-cd74-433a-b99e-2ecdc07bfc25`|
|難読化される可能性のあるスクリプトの実行をブロックする|`5beb7efe-fd9a-4556-801d-275e5ffc04cc`|
|JavaScript または VBScript のダウンロード済み実行可能コンテンツの起動をブロックする|`d3e037e1-3eb8-44c8-a917-57927947596d`|
|実行可能Office作成するアプリケーションのブロック|`3b576869-a4ec-4529-8536-b80a7769e899`|
|アプリケーションOffice他のプロセスへのコードの挿入をブロックする|`75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`|
|通信Office子プロセスの作成をブロックする|`26190899-1602-49e8-8b27-eb1d0a1ce869`|
|WMI イベント サブスクリプションによる永続化のブロック|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|
|PSExec および WMI コマンドから発生するプロセス作成をブロックする|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|
|USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|
|Win32 API 呼び出しをブロックOfficeマクロ|`92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`|
|ランサムウェアに対する高度な保護の使用|`c1db55ab-c21a-4637-bb3f-a12568109d35`|
|

各ルールの [詳細については、攻撃表面](attack-surface-reduction.md) の縮小に関するトピックを参照してください。

### <a name="use-group-policy-to-exclude-files-and-folders"></a>グループ ポリシーを使用してファイルとフォルダーを除外する

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **、攻撃Windows縮小** \> **Microsoft Defender ウイルス対策Microsoft Defender Exploit Guard** \>  \> **コンポーネントを表示します**。

4. [攻撃表面の縮小 **ルールからファイル** とパスを除外する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。 各 **アイテムの [** 値] **列に 0** を入力します。

> [!WARNING]
> [値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。

### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell を使用してファイルとフォルダーを除外する

1. **[powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**
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

- [攻撃表面の縮小ルールを使用して攻撃表面を削減する](attack-surface-reduction.md)
- [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
- [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
- [攻撃面の減少の FAQ](attack-surface-reduction.md)
