---
title: インサイダー リスク管理ブラウザーのシグナル検出の詳細と構成
description: インサイダー リスク管理ブラウザーのシグナル検出について詳しくは、Microsoft 365
keywords: Microsoft 365, インサイダー リスク管理, リスク管理, コンプライアンス
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 5cde3a6f03c1c876878fc5ddda5ac4a8bc698977
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662530"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection"></a>インサイダー リスク管理ブラウザーのシグナル検出の詳細と構成

Web ブラウザーは、多くの場合、組織内の機密性の高いファイルと機密性の高いファイルの両方にアクセスするために使用されます。 Insider リスク管理を使用すると、組織は、Microsoft Edge および[Google Chrome](https://www.google.com/chrome)ブラウザーで表示される実行可能でない[](https://www.microsoft.com/edge)すべてのファイルに対して、ブラウザーの外へ出るシグナルを検出して処理できます。 これらのシグナルを使用すると、アナリストや調査担当者は、これらのブラウザーを使用する場合、スコープ内のポリシー ユーザーが次のアクティビティを実行した場合に迅速に処理できます。

- 個人用クラウド ストレージにコピーされたファイル
- ローカル デバイスまたはネットワーク デバイスに印刷されるファイル
- ネットワーク共有に転送またはコピーされたファイル
- USB デバイスにコピーされたファイル

これらのイベントのシグナルは、組み込Microsoft Edge機能を使用し *、Microsoft Insider Risk Extension* アドオンを使用する場合に検出されます。 Google Chrome では、お客様は *信号検出に Microsoft コンプライアンス拡張機能* を使用します。

次の表は、各ブラウザーで検出されたアクティビティと拡張機能のサポートの概要を示しています。

| **検出されたアクティビティ**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| 個人用クラウド ストレージにコピーされたファイル         | ネイティブ             | 拡張子         |
| ローカル デバイスまたはネットワーク デバイスに印刷されるファイル      | ネイティブ             | 拡張子         |
| ネットワーク共有に転送またはコピーされたファイル | 拡張子          | 拡張子         |
| USB デバイスにコピーされたファイル                    | 拡張子          | 拡張子         |

## <a name="common-requirements"></a>一般的な要件

*Microsoft Insider Risk Extension* または Microsoft  Compliance Extension をインストールする前に、スコープ内ポリシー ユーザーのデバイスが次の要件を満たしていることを確認する必要があります。

- 最新のWindows 10 x64 ビルドをお勧めします。信号検出のサポートWindows 10 x64 ビルド 1809 の最小バージョンです。 ブラウザー信号の検出は、現在、デバイス以外のデバイスWindowsされていません。
- イン[サイMicrosoft 365のリスク管理](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing)サポートを使用した現在のサブスクリプション。
- デバイスは、[コンプライアンス ポータルに](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices)オンボードMicrosoft 365必要があります。

特定のブラウザー構成要件については、この記事の「Microsoft Edge」および「Google Chrome」セクションを参照してください。

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>ブラウザーのブラウザー信号検出を構成Microsoft Edge

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edgeの要件

- 共通の要件を満たす
- Microsoft Edge x64、91.0.864.41 バージョン以上
- *Microsoft Insider Risk Extension* アドオン バージョン 1.0.0.44 以上
- Edge.exeが許可されていないブラウザーとして構成されていない

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>オプション 1: 基本的なセットアップ (Edge でのテストに推奨)

このオプションを使用して、ブラウザーの信号検出をテストする際に、組織内のデバイスごとに 1 台のコンピューターセルフホストを構成します。

基本的なセットアップ オプションについては、次の手順を実行します。

1. [[Microsoft Insider Risk Extension] に移動します](https://microsoftedge.microsoft.com/addons/detail/microsoft-insider-risk-ex/lcmcgbabdcbngcbcfabdncmoppkajglo)。
2. 拡張機能をインストールします。

### <a name="option-2-intune-setup-for-edge"></a>オプション 2: エッジの Intune セットアップ

Intune を使用して組織の拡張機能と要件を構成するには、このオプションを使用します。

Intune セットアップ オプションの場合は、次の手順を実行します。

1. 管理者のアクセス許可を使用[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。
2. [構成プロファイル **] に移動します**。
3. **[プロファイルの作成]** を選択します。
4. プラットフォーム **Windows 10** を選択します。
5. [プロファイル **の種類] として [管理用テンプレート***] を選択し、[* 作成] を **選択します。**
6. **[設定]** タブを選択します。
7. [ **エッジ バージョン 77 以降] を選択します。**
8. 拡張機能に **関連する設定** の概要を示す拡張機能を検索します。
9. [サイレント モードで **インストールする拡張機能を制御する] の設定を選択します。**
10. [有効] **を選択します。**
11. プロンプトが表示されたら、拡張子 ID を追加します *。lcmcgbabdcbngcbcfabdncmoppkajglo***。**
12. **[OK] を選択します。**

### <a name="option-3-group-policy-setup-for-edge"></a>オプション 3: エッジのグループ ポリシーのセットアップ

グループ ポリシーを使用して拡張機能と要件を組織全体で構成するには、このオプションを使用します。

[グループ ポリシーのセットアップ] オプションで、次の手順を実行します。

**手順 1: 管理用テンプレート (.admx) Microsoft Edgeをインポートします。**

デバイスはグループ ポリシーを使用して管理可能である必要がありますMicrosoft Edge[管理](https://www.microsoft.com/edge/business/download)用テンプレートをグループ ポリシー の中央ストアにインポートする必要があります。 詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。

**手順 2: *Microsoft Insider リスク管理拡張機能* アドオンを強制インストール リスト *に追加* します。**

拡張機能を追加するには、次の手順を実行します。

1. グループ ポリシー **管理エディターで、** 組織単位 (OU) に移動します。
2. [コンピューター/ユーザー構成 **ポリシー]** 管理用テンプレート [従来の管理用テンプレート] および [拡張機能] のMicrosoft Edge \>  \>  \>  \>  \> **展開します**。 このパスは、組織の構成によって異なる場合があります。
3. [ **サイレント インストールされている拡張機能を構成する] を選択します。**
4. 右クリックし、[編集] を **選択します**。
5. [有効] **ラジオ ボタン** を確認します。
6. **[表示]** を選択します。
7. [**値]** に、次のエントリを *追加します。lcmcgbabdcbngcbcfabdncmoppkajglo。 https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. **[OK] を選択** し、[適用] を **選択します**。

## <a name="configure-browser-signal-detection-for-google-chrome"></a>Google Chrome のブラウザー信号検出を構成する

Google Chrome の Insider リスク管理ブラウザーシグナル検出サポートは、Microsoft コンプライアンス拡張機能 *を通じて有効になります*。 この拡張機能では、Chrome の Endpoint DLP もサポートしています。 エンドポイント DLP のサポートの詳細については、「Microsoft コンプライアンス拡張機能の概要 [(プレビュー)」を参照してください](/microsoft-365/compliance/dlp-chrome-get-started)。

### <a name="google-chrome-browser-requirements"></a>Google Chrome ブラウザーの要件

- 一般的な要件を満たす
- Google Chrome x64 の最新バージョン
- *Microsoft Compliance Extension* バージョン 2.0.0.183 以上
- Chrome.exeが許可されていないブラウザーとして構成されていない

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>オプション 1: 基本的なセットアップ (Chrome でのテストに推奨)

このオプションを使用して、ブラウザーの信号検出をテストする際に、組織内のデバイスごとに 1 台のコンピューターセルフホストを構成します。

基本的なセットアップ オプションについては、次の手順を実行します。

**手順 1: PowerShell で必要なレジストリ キーを有効にする**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>これらのレジストリ キーは、拡張機能の適切な機能を確保するために必要です。 シグナルをテストする前に、これらのレジストリ キーを有効にする必要があります。*

**手順 2: *Microsoft コンプライアンス拡張機能をインストールする***

1. [Microsoft コンプライアンス [拡張機能] に移動します](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。
2. 拡張機能をインストールします。

### <a name="option-2-intune-setup-for-chrome"></a>オプション 2: Chrome の Intune セットアップ

Intune を使用して組織の拡張機能と要件を構成するには、このオプションを使用します。

Intune セットアップ オプションの場合は、次の手順を実行します。

**手順 1: Intune で必要なレジストリ キーを有効にする**

1. 次の PowerShell スクリプトを実行します。

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. 管理者センターにサインイン[Microsoft エンドポイント マネージャーします](https://endpoint.microsoft.com)。
3. [デバイス スクリプト **] に** \> **移動し、[** 追加] を **選択します。**
4. プロンプトが表示されたら、作成したスクリプトの場所を参照してください。
5. 次の設定を選択します。

    - ログオンした資格情報を使用してこのスクリプトを実行します。 *はい*
    - スクリプト署名チェックの適用: *いいえ*
    - 64 ビット PowerShell ホストでスクリプトを実行する: *はい*

6. 適切なデバイス グループを選択し、ポリシーを適用します。

**手順 2: Intune Force Install を構成する**

強制インストールされた拡張機能の一覧に Microsoft DLP Chrome 拡張機能を追加する前に、Intune 管理用の Chrome 管理テンプレート (.admx) ファイルをインストールする必要があります。 詳細なガイダンスについては、「Chrome ブラウザーを管理[する」を参照Microsoft Intune。](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune) 管理用テンプレート ファイルをインストールしたら、次の手順を実行します。

1. 管理者センターにサインイン[Microsoft エンドポイント マネージャーします](https://endpoint.microsoft.com)。
2. [構成プロファイル **] に移動します**。
3. **[プロファイルの作成]** を選択します。
4. [**プラットフォームWindows 10]** を *選択します*。
5. プロファイルの **種類として [** カスタム *] を* 選択します。
6. **[設定]** タブを選択します。
7. [追加 **] を選択します。**
8. 次のポリシー情報を入力します。

    - OMA-URI: *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - データ型: *文字列*
    - 値: *\<enabled/\>\<data id=”ExtensionInstallForcelistDesc” value=”1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/\>*

9. **[作成]** を選択します。

### <a name="option-3-group-policy-setup-for-chrome"></a>オプション 3: Chrome のグループ ポリシーのセットアップ

グループ ポリシーを使用して拡張機能と要件を組織全体で構成するには、このオプションを使用します。

[グループ ポリシーのセットアップ] オプションで、次の手順を実行します。

**手順 1: Chrome 管理用テンプレート ファイルをインポートする**

デバイスはグループ ポリシーを使用して管理可能である必要があります。 [また、すべての Chrome 管理](https://chromeenterprise.google/browser/download/) 用テンプレートをグループ ポリシー の中央ストアにインポートする必要があります。 詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。

**手順 2: PowerShell で必要なレジストリ キーを有効にする**

1. 次のコンテンツを使用して PowerShell スクリプトを作成します。

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. **グループ ポリシー管理コンソール** を開き、自分の組織単位 (OU) に移動します。
3. 右クリックして[この **ドメインに GPO を作成する] を選択し、ここにリンクします**。 メッセージが表示されたら、このグループ ポリシー オブジェクト (GPO) にわかりやすい名前を割り当てる必要があります。 たとえば *、DLP Chrome イミディエイト PowerShell スクリプトです*。
4. GPO を作成した後、右クリックして [編集] を **選択します**。 この選択では、グループ ポリシー オブジェクトに移動します。
5. [コンピューターの構成 **]** \> **[基本設定] コントロール** \> **パネルの設定 [スケジュール** \> **されたタスク] に移動します**。
6. [スケジュールされたタスク] の下の空白領域を右 **クリック** し、[新しいイミディエイト タスク] (少なくとも \> **7) をWindowsします。**
7. タスク名と *説明を**入力します*。
8. 対応するアカウントを選択して、即時タスクを実行します。 たとえば *、NT Authority*.
9. **[最上位の特権で実行する]** を選択します。
10. Windows 10 用のポリシーを構成します。
11. [操作] **タブで** 、[プログラムの開始 **] を選択します**。
12. 手順 1 で作成したプログラム/スクリプトへのパス **を入力します**。
13. **[適用]** を選択します。

**手順 3: Chrome 拡張機能を [強制インストール] リストに追加する**

1. グループ ポリシー **管理エディターで、** 組織単位 (OU) に移動します。
2. 次のパス **を展開する コンピューター/ユーザー構成** ポリシー 管理用テンプレート 従来の管理用テンプレート \>  \>  \>  \> **Google** \> **Google Chrome** \> **Extensions**. このパスは、組織の構成によって異なる場合があります。
3. [強制 **インストールされた拡張機能の一覧を構成する] を選択します**。
4. 右クリックし、[編集] を **選択します**。
5. [有効] **ラジオ ボタン** を選択します。
6. **[表示]** を選択します。
7. [**値]** に *、echcggldkblhodogklpincgchnpgcdco というエントリ https://clients2.google.com/service/update2/crx を追加します。*
8. **[OK] を選択** し、[適用] を **選択します**。

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>インサイダー リスク管理ブラウザーのシグナル検出をテストおよび確認する

1. デバイス インジケーターを有効にしたインサイダー リスク管理ポリシーを作成します。
2. 個人用クラウド ストレージにコピーされたファイルの信号検出をテストするには、サポートされているデバイスから次の手順Windowsします。

    - 信号検出用に構成Microsoft OneDriveブラウザー Google ドライブファイル共有 Web サイト (Google ドライブ など) を開きます。
    - ブラウザーで、実行可能でないファイルを Web サイトにアップロードします。
3. ローカル デバイスまたはネットワーク デバイスに印刷されるファイル、ネットワーク共有に転送またはコピーされたファイル、USB デバイスにコピーされたファイルの信号検出をテストするには、サポートされているデバイスから次の手順Windowsします。

    - ブラウザーで実行可能でないファイルを直接開きます。 ファイルはエクスプローラーから直接開く必要があります。または Web ページではなく新しいブラウザー タブで開く必要があります。
    - ファイルを印刷します。
    - ファイルを USB デバイスに保存します。
    - ファイルをネットワーク ドライブに保存します。
  
4. 最初のインサイダー リスク管理ポリシーが作成された後、約 24 時間後にアクティビティ インジケーターからアラートの受信を開始します。 テスト済み [アクティビティのイン](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) サイダー リスク管理アラートについては、アラート ダッシュボードを確認します。
