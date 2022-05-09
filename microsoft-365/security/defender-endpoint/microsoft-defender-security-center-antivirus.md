---
title: Windows セキュリティ アプリのMicrosoft Defender ウイルス対策
description: Microsoft Defender ウイルス対策がWindows セキュリティ アプリに含まれるようになったので、一般的なタスクを確認、比較、実行できます。
keywords: wdav, ウイルス対策, ファイアウォール, セキュリティ, Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 1c5177946ff3d54ab64c78e9013a8e0c07b0fd11
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468129"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows セキュリティ アプリのMicrosoft Defender ウイルス対策

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Windows 10バージョン 1703 以降では、Windows Defender アプリはWindows セキュリティの一部です。

Windows Defender クライアントとメイン Windows 設定の一部であった設定が結合され、Windows 10 バージョン 1703 の一部として既定でインストールされる新しいアプリに移動されました。

> [!IMPORTANT]
> Windows セキュリティ アプリ サービスを無効にしても、ファイアウォールのMicrosoft Defender ウイルス対策や[Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)は無効になりません。 サード パーティのウイルス対策またはファイアウォール製品がインストールされ、最新の状態に保たれている場合、これらは自動的に無効になります。
>
> Windows セキュリティ アプリ サービスを無効にしたり、関連付けられたグループ ポリシー設定を構成して起動や実行を妨げる場合、Windows セキュリティ アプリには、デバイスにインストールしたウイルス対策製品やファイアウォール製品に関する古い情報や不正確な情報が表示されることがあります。
> また、古い、または古いサード パーティ製のウイルス対策を使用している場合、または以前にインストールした可能性があるサードパーティのウイルス対策製品をアンインストールした場合、Microsoft Defender ウイルス対策がそれ自体を有効にできない場合もあります。
> これにより、デバイスの保護が大幅に低下し、マルウェア感染につながる可能性があります。

アプリで監視できるその他のWindowsセキュリティ機能の詳細については、Windows セキュリティ[の記事](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)を参照してください。

Windows セキュリティ アプリは、Windows 10 バージョン 1703 以降のクライアント インターフェイスです。 Microsoft Defender for Endpointの確認と管理に使用されるのは、[Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) Web ポータルではありません。

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Windows セキュリティ アプリでウイルスと脅威の保護の設定を確認する

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Windows セキュリティ アプリのウイルスと脅威の保護の設定" lightbox="../../media/wdav-protection-settings-wdsc.png":::

1. タスク バーのシールド アイコンをクリックするか、Windows セキュリティのスタート メニューを検索して **、Windows セキュリティ アプリを** 開きます。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

以降のセクションでは、Windows セキュリティ アプリでMicrosoft Defender ウイルス対策によって提供される脅威保護を確認または操作するときに、最も一般的なタスクの一部を実行する方法について説明します。

> [!NOTE]
> これらの設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できなくなります。 グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。 「[Microsoft Defender ウイルス対策でのエンド ユーザー操作の構成](configure-end-user-interaction-microsoft-defender-antivirus.md)」トピックでは、ローカル ポリシーオーバーライド設定を構成する方法について説明します。

## <a name="run-a-scan-with-the-windows-security-app"></a>Windows セキュリティ アプリでスキャンを実行する

1. [**セキュリティ**] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. **[クイック スキャン**] を選択します。 または、フル スキャンを実行するには、[ **スキャン] オプション** を選択し、[ **フル スキャン**] などのオプションを選択します。

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>セキュリティ インテリジェンス更新プログラムのバージョンを確認し、Windows セキュリティ アプリで最新の更新プログラムをダウンロードする

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="セキュリティ インテリジェンスのバージョン番号" lightbox="../../media/wdav-wdsc-defs.png":::

1. [*セキュリティ*] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. **[ウイルス&脅威対策の更新プログラム**] を選択します。 現在インストールされているバージョンが、ダウンロードされた日時に関するいくつかの情報と共に表示されます。 手動でダウンロードできる最新バージョンに対して現在のバージョンを確認したり、そのバージョンの変更ログを確認したりできます。 [Microsoft Defender ウイルス対策およびその他の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラムに関](https://www.microsoft.com/wdsi/defenderupdates)するページを参照してください。

4. [ **更新プログラムの確認** ] を選択して、新しい保護更新プログラムをダウンロードします (存在する場合)。

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Windows セキュリティ アプリでMicrosoft Defender ウイルス対策が有効になっていることを確認する

1. [*セキュリティ*] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. **[ウイルス&脅威保護の設定] を選択します**。

4. **リアルタイム保護** スイッチを **[オン]** に切り替えます。

    > [!NOTE]
    > **リアルタイム保護** をオフに切り替えると、短い遅延後に自動的にオンに戻ります。 これは、マルウェアや脅威から確実に保護するためです。
    > 別のウイルス対策製品をインストールすると、Microsoft Defender ウイルス対策自動的に無効になり、Windows セキュリティ アプリでそのように示されます。 一定の [定期的なスキャン](limited-periodic-scanning-microsoft-defender-antivirus.md)を有効にできる設定が表示されます。

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows セキュリティ アプリでMicrosoft Defender ウイルス対策の除外を追加する

1. [*セキュリティ*] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. **[ウイルスと脅威保護設定]** で **[設定の管理]** を選択します。

4. [ **除外]** で、[ **除外の追加と削除**] を選択します。

5. プラスアイコン (**+**) を選択して種類を選択し、除外ごとにオプションを設定します。

次の表は、除外の種類と動作をまとめたものです。

<br>

****
|除外の種類|によって定義される|動作|
|---|---|---|
|**ファイル**|Location <br/>例: `c:\sample\sample.test`|特定のファイルはMicrosoft Defender ウイルス対策によってスキップされます。|
|**Folder**|Location <br/>例: `c:\test\sample`|指定したフォルダー内のすべての項目は、Microsoft Defender ウイルス対策によってスキップされます。|
|**ファイルの種類**|ファイル拡張子 <br/>例: `.test`|デバイス上の任意の`.test`場所にある拡張子を持つすべてのファイルは、Microsoft Defender ウイルス対策によってスキップされます。|
|**プロセス**|実行可能ファイルのパス <br>例: `c:\test\process.exe`|特定のプロセスとそのプロセスによって開かれたすべてのファイルは、Microsoft Defender ウイルス対策によってスキップされます。|
|

詳細については、次のリソースを参照してください。

- [ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する](./configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成する](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-for-cloud-app"></a>クラウド アプリのWindows Defenderで脅威検出履歴を確認する

1. [*セキュリティ*] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. [ **保護履歴**] を選択します。 最近使用したアイテムがすべて一覧表示されます。

## <a name="set-ransomware-protection-and-recovery-options"></a>ランサムウェアの保護と回復のオプションを設定する

1. [*セキュリティ*] の [スタート] メニューを検索し、Windows セキュリティを選択して、**Windows セキュリティ アプリを開きます**。

2. **[ウイルス&脅威保護**] タイル (または左側のメニュー バーのシールド アイコン) を選択します。

3. [ **ランサムウェア保護**] で、[ **ランサムウェア保護の管理**] を選択します。

4. **フォルダー アクセスの制御** 設定を変更するには、「フォルダー アクセス [の制御を使用して重要なフォルダーを保護する」を](/microsoft-365/security/defender-endpoint/controlled-folders)参照してください。

5. ランサムウェア回復オプションを設定するには、[**ランサムウェア データ復旧**] で **[セットアップ**] を選択し、ランサムウェア攻撃から簡単に回復できるように、OneDrive アカウントをリンクまたは設定する手順に従います。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
