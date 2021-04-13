---
title: Windows セキュリティ アプリの Microsoft Defender ウイルス対策
description: Microsoft Defender Antivirus が Windows セキュリティ アプリに含まれるので、一般的なタスクを確認、比較、実行できます。
keywords: wdav, ウイルス対策, ファイアウォール, セキュリティ, Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 042bb67c223631ae1759b62a32c2f5713b4d62e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690922"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows セキュリティ アプリの Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows 10 バージョン 1703 以降では、Windows Defenderは Windows セキュリティの一部です。

Windows Defender クライアントとメインの Windows 設定の一部だった設定が結合され、新しいアプリに移動され、Windows 10 バージョン 1703 の一部として既定でインストールされます。

> [!IMPORTANT]
> Windows セキュリティ センター サービスを無効にしても、Microsoft Defender ウイルス対策やファイアウォールWindows Defender [無効にしない](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 これらは、サードパーティのウイルス対策製品またはファイアウォール製品がインストールされ、最新の状態に保たれ、自動的に無効になります。
>
> Windows セキュリティ センター サービスを無効にするか、関連するグループ ポリシー設定を構成して開始または実行を防ぐ場合、Windows セキュリティ アプリは、デバイスにインストールしたウイルス対策製品またはファイアウォール製品に関する古い情報や不正確な情報を表示する可能性があります。
> また、古いまたは古いサードパーティ製のウイルス対策を使用している場合、または以前にインストールしたサードパーティのウイルス対策製品をアンインストールした場合、Microsoft Defender Antivirus がそれ自体を有効にしなくなっている可能性もあります。
> これにより、デバイスの保護が大幅に低下し、マルウェアの感染につながる可能性があります。

アプリで [監視できる他](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) の Windows セキュリティ機能の詳細については、「Windows セキュリティ」の記事を参照してください。

Windows セキュリティ アプリは、Windows 10 バージョン 1703 以降のクライアント インターフェイスです。 Microsoft Defender for Endpoint の確認と管理に使用される Microsoft Defender セキュリティ センター [Web ポータルではありません](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Windows セキュリティ アプリでウイルスと脅威保護の設定を確認する

![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

1. タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。
   
次のセクションでは、Windows セキュリティ アプリで Microsoft Defender ウイルス対策によって提供される脅威保護を確認または操作する際に、最も一般的なタスクの一部を実行する方法について説明します。

> [!NOTE]
> これらの設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できません。 グループ ポリシー オブジェクトを使用して行った変更は、Windows の設定で設定を更新する前に、最初に個々のエンドポイントに展開する必要があります。 「Microsoft [Defender ウイルス対策によるエンド](configure-end-user-interaction-microsoft-defender-antivirus.md) ユーザー操作の構成」トピックでは、ローカル ポリシーの上書き設定を構成する方法について説明します。

## <a name="run-a-scan-with-the-windows-security-app"></a>Windows セキュリティ アプリでスキャンを実行する

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [クイック **スキャン] を選択します**。 または、フル スキャンを実行するには、[スキャン **オプション]** を選択し、[フル スキャン] などのオプション **を選択します**。

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>セキュリティ インテリジェンス更新プログラムのバージョンを確認し、Windows セキュリティ アプリで最新の更新プログラムをダウンロードする

![セキュリティ インテリジェンスのバージョン番号情報](images/defender/wdav-wdsc-defs.png)

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [ウイルス **対策&更新プログラム] を選択します**。 現在インストールされているバージョンが、ダウンロードされた時点に関する情報と共に表示されます。 手動でダウンロードできる最新バージョンに対して現在の状態を確認するか、そのバージョンの変更ログを確認できます。 「Microsoft [Defender ウイルス対策と他の Microsoft マルウェア](https://www.microsoft.com/en-us/wdsi/defenderupdates)対策のセキュリティ インテリジェンス更新プログラム」を参照してください。

4. [更新 **プログラムの確認] を** 選択して、新しい保護更新プログラムをダウンロードします (ある場合)。

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Windows セキュリティ アプリで Microsoft Defender ウイルス対策が有効になっているか確認する

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [ウイルス **対策&の設定] を選択します**。

4. [リアルタイム保護 **] スイッチを [オン]** に **切り替えます**。

    > [!NOTE]
    > リアルタイム保護を **オフに** した場合、短時間の遅延後に自動的にオンに戻されます。 これは、マルウェアや脅威から保護されます。
    > 別のウイルス対策製品をインストールすると、Microsoft Defender Antivirus は自動的に自身を無効にし、Windows セキュリティ アプリでそのような状態で示されます。 制限された定期的なスキャンを有効にできる [設定が表示されます](limited-periodic-scanning-microsoft-defender-antivirus.md)。

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows セキュリティ アプリで Microsoft Defender ウイルス対策の除外を追加する

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [設定の **管理] で**、[ **ウイルス対策の脅威&設定] を選択します**。

4. [除外 **] 設定で** 、[除外の追加と **削除] を選択します**。 

5. プラス アイコン ( ) を **+** 選択して種類を選択し、除外ごとにオプションを設定します。 

次の表に、除外の種類と実行内容の概要を示します。

|除外の種類  |によって定義される  |結果  |
|---------|---------|---------|
|**File** |場所 <br/>例: `c:\sample\sample.test` |特定のファイルは、Microsoft Defender ウイルス対策によってスキップされます。 |
|**Folder**    |場所 <br/>例: `c:\test\sample`       |指定したフォルダー内のすべてのアイテムは、Microsoft Defender ウイルス対策によってスキップされます。         |
|**ファイルの種類**   |ファイル拡張子 <br/>例: `.test` |デバイス上の任意 `.test` の場所に拡張子を持つすべてのファイルは、Microsoft Defender Antivirus によってスキップされます。         |
|**プロセス**     |実行可能ファイルのパス <br>例: `c:\test\process.exe`         |特定のプロセスと、そのプロセスによって開くファイルは、Microsoft Defender ウイルス対策によってスキップされます。         |

詳細については、次のリソースを参照してください。
- [ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [プロセスによって開いたファイルの除外を構成する](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>セキュリティ センター アプリで脅威検出Windows Defender確認する

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [保護 **履歴] を選択します**。 最近のアイテムが一覧表示されます。

## <a name="set-ransomware-protection-and-recovery-options"></a>ランサムウェアの保護と回復のオプションを設定する

1. [セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。

3. [ **ランサムウェア保護] で、[** ランサムウェア **保護の管理] を選択します**。

4. [フォルダー アクセス **の制御] 設定を変更** するには、「フォルダー アクセスの制御を [使用して重要なフォルダーを保護する」を参照してください](/microsoft-365/security/defender-endpoint/controlled-folders)。

5. ランサムウェアの回復オプションを設定するには、[ランサムウェア のデータ復旧] で [セットアップ] を選択し、OneDrive アカウントをリンクまたはセットアップする手順に従って、ランサムウェア攻撃から簡単に回復できます。

## <a name="see-also"></a>関連項目
- [Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)