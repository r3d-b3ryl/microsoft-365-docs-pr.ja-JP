---
title: インサイダー リスク管理ブラウザーのシグナル検出について説明し、構成する
description: Microsoft 365でのインサイダー リスク管理ブラウザーのシグナル検出について説明します
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
ms.openlocfilehash: e904c4576081cd459ca905a56e3dd6cec5b1af31
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758731"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection"></a>インサイダー リスク管理ブラウザーのシグナル検出について説明し、構成する

Web ブラウザーは、組織内の機密ファイルと非機密ファイルの両方にアクセスするためにユーザーによってよく使用されます。 インサイダー リスク管理を使用すると、組織は[、Microsoft Edge](https://www.microsoft.com/edge)および [Google Chrome](https://www.google.com/chrome) ブラウザーで表示されるすべての実行可能ファイルに対するブラウザー流出シグナルを検出して処理できます。 これらのシグナルにより、アナリストと調査担当者は、これらのブラウザーを使用するときに、スコープ内のポリシー ユーザーが次のいずれかのアクティビティを実行したときに迅速に動作します。

- 個人用クラウド ストレージにコピーされたファイル
- ローカル デバイスまたはネットワーク デバイスに印刷されたファイル
- ネットワーク共有に転送またはコピーされたファイル
- USB デバイスにコピーされたファイル

これらのイベントのシグナルは、組み込みのブラウザー機能を使用し、*Microsoft コンプライアンス拡張機能* アドオンを使用してMicrosoft Edgeで検出されます。 Google Chrome では、お客様は Microsoft *コンプライアンス拡張機能* を使用してシグナル検出を行います。

次の表は、検出された各ブラウザーのアクティビティと拡張機能のサポートをまとめたものです。

| **検出されたアクティビティ**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| 個人用クラウド ストレージにコピーされたファイル         | ネイティブ             | 拡張子         |
| ローカル デバイスまたはネットワーク デバイスに印刷されたファイル      | ネイティブ             | 拡張子         |
| ネットワーク共有に転送またはコピーされたファイル | 拡張子          | 拡張子         |
| USB デバイスにコピーされたファイル                    | 拡張子          | 拡張子         |

## <a name="common-requirements"></a>一般的な要件

Microsoft Edge アドオンまたは Google Chrome 拡張機能をインストールする前に、お客様は、スコープ内ポリシー ユーザーのデバイスが次の要件を満たしていることを確認する必要があります。

- 最新のWindows 10 x64 ビルドをお勧めします。信号検出のサポートには、x64 ビルド 1809 Windows 10最小です。 ブラウザー信号の検出は、現在、Windows以外のデバイスではサポートされていません。
- インサイダー リスク管理のサポートを備えた現在の[Microsoft 365 サブスクリプション](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing)。
- デバイスは、Microsoft 365 コンプライアンス ポータルに[オンボード](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices)する必要があります。

特定のブラウザー構成要件については、この記事の後半のMicrosoft Edgeと Google Chrome のセクションを参照してください。

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>Microsoft Edgeのブラウザー信号検出を構成する

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edge ブラウザーの要件

- 一般的な要件を満たす
- Microsoft Edge x64、91.0.864.41 以降
- *Microsoft Compliance Extension* アドオン バージョン 1.0.0.44 以降
- Edge.exeが未承認のブラウザーとして構成されていない

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>オプション 1: 基本的なセットアップ (Edge でのテストに推奨)

このオプションを使用して、ブラウザーの信号検出をテストするときに、組織内の各デバイスに対して単一のマシン セルフホストを構成します。

基本的なセットアップ オプションについては、次の手順を実行します。

1. [Microsoft コンプライアンス拡張機能](https://microsoftedge.microsoft.com/addons/detail/microsoft-compliance-exte/lcmcgbabdcbngcbcfabdncmoppkajglo)に移動します。
2. 拡張機能をインストールします。

### <a name="option-2-intune-setup-for-edge"></a>オプション 2: Edge のセットアップをIntuneする

Intuneを使用して組織の拡張機能と要件を構成するには、このオプションを使用します。

Intuneセットアップ オプションでは、次の手順を実行します。

1. 管理者のアクセス許可を使用して[、Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。
2. **[構成プロファイル]** に移動します。
3. **[プロファイルの作成]** を選択します。
4. プラットフォームとして **Windows 10** を選択します。
5. *[プロファイルの種類*] として [**管理用テンプレート**] を選択し、[作成] を選択します **。**
6. **[設定]** タブを選択します。
7. **Edge バージョン 77 以降を** 選択します。
8. **拡張機能** を検索すると、拡張機能に関連するすべての設定の概要が表示されます。
9. サイレント モードで **インストールする拡張機能を制御する** 設定を選択します。
10. [ **有効] を選択します。**
11. プロンプトが表示されたら、拡張機能 ID を追加します。 *lcmcgbabdcbnbcfabdncmoppkajglo***。**
12. [ **OK] を選択します。**

### <a name="option-3-group-policy-setup-for-edge"></a>オプション 3: Edge のセットアップをグループ ポリシーする

グループ ポリシーを使用して組織全体で拡張機能と要件を構成するには、このオプションを使用します。

グループ ポリシーセットアップ オプションで、次の手順を実行します。

**手順 1: 最新のMicrosoft Edge管理テンプレート (.admx) ファイルをインポートします。**

デバイスはグループ ポリシーを使用して管理可能である必要があり[、すべてのMicrosoft Edge管理用テンプレート](https://www.microsoft.com/edge/business/download)を グループ ポリシー Central Store にインポートする必要があります。 詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。

**手順 2: *Microsoft コンプライアンス拡張機能* アドオンを *[強制インストール* ] の一覧に追加します。**

拡張機能を追加するには、次の手順を実行します。

1. **グループ ポリシー管理エディター** で、組織単位 (OU) に移動します。
2. 次のパス **を展開します。コンピューター/ユーザー構成** \> **ポリシー** \> **管理テンプレート** **クラシック管理テンプレート** \> \> **Microsoft Edge** \> **拡張機能** です。 このパスは、組織の構成によって異なる場合があります。
3. [**サイレント インストールする拡張機能を構成する]** を選択します。
4. 右クリックして **[編集]** を選択します。
5. **[有効]** ラジオ ボタンをオンにします。
6. **[表示]** を選択します。
7. **Value** には、次のエントリを追加します。*lcmcgbabdcbnbcfabdncmoppkajglo;https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. **[OK] を** 選択し、[**適用**] を選択します。

## <a name="configure-browser-signal-detection-for-google-chrome"></a>Google Chrome のブラウザー信号検出を構成する

Google Chrome のインサイダー リスク管理ブラウザーシグナル検出のサポートは、 *Microsoft コンプライアンス拡張機能* を通じて有効になっています。 この拡張機能では、Chrome 上のエンドポイント DLP もサポートされています。 エンドポイント DLP のサポートの詳細については、「[Microsoft コンプライアンス拡張機能 (プレビュー)の概要](/microsoft-365/compliance/dlp-chrome-get-started)」を参照してください。

### <a name="google-chrome-browser-requirements"></a>Google Chrome ブラウザーの要件

- 一般的な要件を満たす
- Google Chrome x64 の最新バージョン
- *Microsoft コンプライアンス拡張機能* バージョン 2.0.0.183 以降
- Chrome.exeが未承認のブラウザーとして構成されていない

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>オプション 1: 基本的なセットアップ (Chrome でのテストに推奨)

このオプションを使用して、ブラウザーの信号検出をテストするときに、組織内の各デバイスに対して単一のマシン セルフホストを構成します。

基本的なセットアップ オプションについては、次の手順を実行します。

**手順 1: PowerShell で必要なレジストリ キーを有効にする**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>拡張機能の適切な機能を確保するには、これらのレジストリ キーが必要です。 シグナルをテストする前に、これらのレジストリ キーを有効にする必要があります。

**手順 2: *Microsoft コンプライアンス拡張機能* をインストールする**

1. [Microsoft コンプライアンス拡張機能](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)に移動します。
2. 拡張機能をインストールします。

### <a name="option-2-intune-setup-for-chrome"></a>オプション 2: Chrome のセットアップをIntuneする

Intuneを使用して組織の拡張機能と要件を構成するには、このオプションを使用します。

Intuneセットアップ オプションでは、次の手順を実行します。

**手順 1: Intuneで必要なレジストリ キーを有効にする**

1. 次の PowerShell スクリプトを実行します。

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。
3. **デバイス** \> **スクリプト** に移動し、[**追加**] を選択します。
4. プロンプトが表示されたら、作成したスクリプトの場所を参照してください。
5. 次の設定を選択します。

    - ログオンした資格情報を使用してこのスクリプトを実行します。 *はい*
    - スクリプト署名チェックを適用する: *いいえ*
    - 64 ビット PowerShell ホストでスクリプトを実行する: *はい*

6. 適切なデバイス グループを選択し、ポリシーを適用します。

**手順 2: 強制インストールIntune構成する**

強制インストールされた拡張機能の一覧に Microsoft DLP Chrome 拡張機能を追加する前に、Intune管理用の Chrome 管理テンプレート (.admx) ファイルをインストールする必要があります。 詳細なガイダンスについては、「[Microsoft Intuneを使用した Chrome ブラウザーの管理](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)」を参照してください。 管理用テンプレート ファイルをインストールしたら、次の手順を実行します。

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。
2. **[構成プロファイル]** に移動します。
3. **[プロファイルの作成]** を選択します。
4. プラットフォームとして **Windows 10** を選択 *します*。
5. *プロファイル* の種類として [**カスタム]** を選択します。
6. **[設定]** タブを選択します。
7. [ **追加] を選択します。**
8. 次のポリシー情報を入力します。

    - OMA-URI: *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - データ型: *文字列*
    - 値： *\<enabled/\>\<data id="ExtensionInstallForcelistDesc" value="1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/\>*

9. **[作成]** を選択します。

### <a name="option-3-group-policy-setup-for-chrome"></a>オプション 3: Chrome のセットアップをグループ ポリシーする

グループ ポリシーを使用して組織全体で拡張機能と要件を構成するには、このオプションを使用します。

グループ ポリシーセットアップ オプションで、次の手順を実行します。

**手順 1: Chrome 管理用テンプレート ファイルをインポートする**

デバイスはグループ ポリシーを使用して管理可能である必要があり、すべての [Chrome 管理用テンプレート](https://chromeenterprise.google/browser/download/)を グループ ポリシー Central Store にインポートする必要があります。 詳細については、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)」を参照してください。

**手順 2: PowerShell で必要なレジストリ キーを有効にする**

1. 次のコンテンツを使用して PowerShell スクリプトを作成します。

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. **グループ ポリシー管理コンソール** を開き、自分の組織単位 (OU) に移動します。
3. 右クリックして [ **このドメインに GPO を作成する] を選択し、ここにリンクします**。 メッセージが表示されたら、このグループ ポリシー オブジェクト (GPO) にわかりやすい名前を割り当てます。 たとえば、 *DLP Chrome イミディエイト PowerShell スクリプト* です。
4. GPO を作成したら、右クリックして **[編集]** を選択します。 この選択により、グループ ポリシー オブジェクトに移動します。
5. **[コンピューター構成** \> **の基本設定]** **コントロール パネルの**\>設定 \> **[スケジュールされたタスク]** に移動します。
6. **[スケジュールされたタスク**] の下の空白領域を右クリックし、[**新しい** \> **イミディエイト タスク] (少なくとも Windows 7)** を選択します。
7. タスク *の名前* と説明を入力 *します*。
8. 対応するアカウントを選択して、即時タスクを実行します。 たとえば、 *NT 機関などです*。
9. **[最上位の特権で実行する]** を選択します。
10. Windows 10 用のポリシーを構成します。
11. [ **アクション]** タブで、[ **プログラムの開始]** を選択します。
12. **手順 1** で作成したプログラム/スクリプトのパスを入力します。
13. **[適用]** を選択します。

**手順 3: Chrome 拡張機能を [強制インストール] ボックスの一覧に追加する**

1. **グループ ポリシー管理エディター** で、組織単位 (OU) に移動します。
2. 次のパス **を展開します コンピューター/ユーザー構成** \> **ポリシー** \> **管理用テンプレート** \> **クラシック管理テンプレート** \> **Google** \> **Chrome** \> **拡張機能**。 このパスは、組織の構成によって異なる場合があります。
3. **[強制インストールされた拡張機能の一覧を構成する**] を選択します。
4. 右クリックして **[編集]** を選択します。
5. [ **有効]** ラジオ ボタンを選択します。
6. **[表示]** を選択します。
7. **[値]** に、*次https://clients2.google.com/service/update2/crx* のエントリを追加します。
8. **[OK] を** 選択し、[**適用**] を選択します。

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>インサイダー リスク管理ブラウザーのシグナル検出のテストと検証

1. デバイス インジケーターが有効になっているインサイダー リスク管理ポリシーを作成します。
2. 個人用クラウド ストレージにコピーされたファイルのシグナル検出をテストするには、サポートされているWindows デバイスから次の手順を実行します。

    - シグナル検出用に構成したブラウザーの種類で、ファイル共有 Web サイト (Microsoft OneDrive、Google ドライブなど) を開きます。
    - ブラウザーで、非実行可能ファイルを Web サイトにアップロードします。
3. ローカルデバイスまたはネットワーク デバイスに印刷されたファイル、ネットワーク共有に転送またはコピーされたファイル、USB デバイスにコピーされたファイルの信号検出をテストするには、サポートされているWindows デバイスから次の手順を実行します。

    - 非実行可能ファイルをブラウザーで直接開きます。 ファイルは、エクスプローラーから直接開くか、Web ページではなく新しいブラウザー タブで開く必要があります。
    - ファイルを印刷します。
    - USB デバイスにファイルを保存します。
    - ファイルをネットワーク ドライブに保存します。
  
4. 最初のインサイダー リスク管理ポリシーが作成されると、約 24 時間後にアクティビティ インジケーターからアラートを受け取り始めます。 テストされたアクティビティのインサイダー リスク管理アラートについては、 [アラート ダッシュボード](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) を確認してください。
