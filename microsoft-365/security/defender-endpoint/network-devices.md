---
title: ネットワーク デバイスの検出と脆弱性の管理
description: スイッチ、ルーター、WLAN コントローラー、ファイアウォールのオペレーティング システムでは、セキュリティに関する推奨事項と脆弱性の検出を利用できます。
keywords: ネットワーク デバイス、ネットワーク デバイスの脆弱性検出、スイッチ、ルーター、WLAN コントローラー、ファイアウォールのオペレーティング システム
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: levinec
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2affbe19484348a511487930d034da6799ca348c
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560217"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>ネットワーク デバイスの検出と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]
> [](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) \( 04-13-2021 に公開されたネットワーク デバイスの検出と脆弱性評価ブログでは、Defender for Endpoint の新しいネットワーク デバイス検出機能に関する分析情報を \) 提供します。 この記事では、ネットワーク デバイスの検出が対処するように設計されている課題の概要と、これらの新機能の使用を開始する方法に関する詳細な情報を提供します。

ネットワーク検出機能は、Microsoft 365 Defenderコンソールの[デバイス インベントリ<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>] セクションMicrosoft 365 Defender使用できます。

指定された Microsoft Defender for Endpoint デバイスは、構成済みのネットワーク デバイスの定期的な認証スキャンを実行するために、各ネットワーク セグメントで使用されます。 検出された Defender for Endpoint の 脅威と脆弱性の管理 機能は、検出されたスイッチ、ルーター、WLAN コントローラー、ファイアウォール、VPN ゲートウェイを保護するための統合ワークフローを提供します。

ネットワーク デバイスが検出され、分類された後、セキュリティ管理者は最新のセキュリティ推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。

## <a name="approach"></a>方法

Defender for Endpoint にはネットワーク デバイス自体にセンサーが組み込かされていないので、ネットワーク デバイスは標準エンドポイントとして管理されません。 これらの種類のデバイスでは、リモート スキャンがデバイスから必要な情報を取得するエージェントレスアプローチが必要です。 ネットワーク トポロジと特性に応じて、Microsoft Defender for Endpoint にオンボードされている 1 台のデバイスまたは数台のデバイスで、SNMP (読み取り専用) を使用してネットワーク デバイスの認証スキャンを実行します。

次の 2 種類のデバイスを念頭に置く必要があります。

- **評価デバイス**: ネットワーク デバイスのスキャンに使用するオンボード済みのデバイス。
- **ネットワーク デバイス**: スキャンとオンボードを計画しているネットワーク デバイス。

### <a name="vulnerability-management-for-network-devices"></a>ネットワーク デバイスの脆弱性管理

ネットワーク デバイスが検出され、分類された後、セキュリティ管理者は最新のセキュリティ推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。

## <a name="operating-systems-that-are-supported"></a>サポートされているオペレーティング システム

現在サポートされているオペレーティング システムは次のとおりです。

- Cisco IOS、IOS-XE、NX-OS
- Juniper JUNOS
- HPE ArubaOS,Procurve Switch Software
- Palo Alto Networks PAN-OS

顧客の使用状況から収集されたデータに基づいて、時間の間に追加されるネットワーク ベンダーと OS の数が多くなされます。 したがって、この一覧で指定されていない場合でも、すべてのネットワーク デバイスを構成してください。

## <a name="how-to-get-started"></a>始める方法

最初の手順は、認証されたネットワーク スキャンを実行するデバイスを選択します。

1. スキャンを計画しているネットワーク デバイスの管理ポートにネットワーク接続を持つ Defender for Endpoint オンボード デバイス (クライアントまたはサーバー) を決定します。

2. Defender for Endpoint 評価デバイスと対象ネットワーク デバイス間の SNMP トラフィックを許可する必要があります (ファイアウォールなど)。

3. 脆弱性に対して評価されるネットワーク デバイスを決定します (たとえば、Cisco スイッチや Palo Alto Networks ファイアウォール)。

4. 構成済みのすべてのネットワーク デバイスで SNMP 読み取り専用が有効になっているので、Defender for Endpoint 評価デバイスが構成済みのネットワーク デバイスに対してクエリを実行できます。 この機能の適切な機能には「SNMP 書き込み」は必要とされません。

5. スキャンするネットワーク デバイス (またはこれらのデバイスが展開されているサブネット) の IP アドレスを取得します。

6. ネットワーク デバイスの SNMP 資格情報を取得します (たとえば、Community String、noAuthNoPriv、authNoPriv、authPriv)。 新しい評価ジョブを構成するときに資格情報を指定する必要があります。

7. プロキシ クライアントの構成: Defender for Endpoint デバイス プロキシの要件以外に、追加の構成は必要ありません。

8. ネットワーク スキャナーを認証して適切に動作するには、次のドメイン/URL を追加する必要があります。

    - login.windows.net
    - \*.security.microsoft.com
    - login.microsoftonline.com
    - \*.blob.core.windows.net/networkscannerstable/\*

    > [!NOTE]
    > すべての URL が Defender for Endpoint で指定されている場合は、許可されるデータ収集の一覧が文書化されています。

## <a name="permissions"></a>アクセス許可

評価ジョブを構成するには、Defender でセキュリティ設定を管理するというユーザーアクセス許可オプション **が必要です**。 アクセス許可は、ロールにアクセスして **設定** \> **できます**。 詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](user-roles.md)。

## <a name="install-the-network-scanner"></a>ネットワーク スキャナーのインストール

1. [エンドポイント評価 **Microsoft 365の設定** に移動します \>  \>  \> ([**ネットワーク評価] の下**)。
    1. このポータルMicrosoft 365 Defender、[評価ジョブ] ページ設定 >移動します。

2. ネットワーク スキャナーをダウンロードし、指定された Defender for Endpoint 評価デバイスにインストールします。

    > [!div class="mx-imgBorder"]
    > ![[スキャナーのダウンロード] ボタン。](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a>ネットワーク スキャナーのインストール&登録

サインイン プロセスは、指定された評価デバイス自体または他のデバイス (個人用クライアント デバイスなど) で完了できます。

ネットワーク スキャナーの登録プロセスを完了するには、次の手順を実行します。

1. コマンド ラインに表示される URL をコピーしてフォローし、提供されたインストール コードを使用して登録プロセスを完了します。

    > [!NOTE]
    > URL をコピーするには、コマンド プロンプトの設定を変更する必要があります。

2. コードを入力し、"Defender でセキュリティ設定を管理する" というエンドポイントの Defender アクセス許可を持つ Microsoft アカウントを使用してサインインします。

3. 完了すると、サインインしたというメッセージが表示されます。

## <a name="configure-a-new-assessment-job"></a>新しい評価ジョブを構成する

[評価ジョブ] ページ **で、[ネットワーク** 設定ジョブの **追加] を選択します**。 セットアップ プロセスに従って、定期的にスキャンしてデバイス インベントリに追加するネットワーク デバイスを選択します。

ネットワーク デバイス インベントリでデバイスの重複を防止するには、各 IP アドレスが複数の評価デバイスで 1 回だけ構成されていることを確認します。

> [!div class="mx-imgBorder"]
> ![[ネットワーク評価ジョブの追加] ボタン。](images/assessment-jobs-add.png)

ネットワーク評価ジョブステップの追加:

1. ネットワーク スキャナーがインストールされた 'Assessment job' 名と 'Assessment device' を選択します。 このデバイスは、定期的に認証されたスキャンを実行します。

2. スキャンするターゲット ネットワーク デバイス (またはこれらのデバイスが展開されているサブネット) の IP アドレスを追加します。

3. ターゲット ネットワーク デバイスの必要な SNMP 資格情報を追加します。

4. 新しく構成されたネットワーク評価ジョブを保存して、定期的なネットワーク スキャンを開始します。

### <a name="scan-and-add-network-devices"></a>ネットワーク デバイスのスキャンと追加

セットアップ プロセス中に、1 回のテスト スキャンを実行して、次の処理を確認できます。

- Defender for Endpoint 評価デバイスと構成済みのターゲット ネットワーク デバイスの間に接続があります。
- 構成済みの SNMP 資格情報が正しい。

各評価デバイスは、最大 1,500 の成功した IP アドレス スキャンをサポートできます。 たとえば、10 の異なるサブネットをスキャンすると、100 の IP アドレスだけが成功した結果を返す場合、同じ評価デバイス上の他のサブネットから 1,400 の IP 追加アドレスをスキャンできます。

スキャンする IP アドレス範囲/サブネットが複数ある場合、テスト スキャンの結果が表示されるのに数分かかります。 テスト スキャンは、最大 1,024 アドレスで使用できます。

結果が表示された後、定期的なスキャンに含めるデバイスを選択できます。 スキャン結果の表示をスキップすると、構成済みのすべての IP アドレスがネットワーク評価ジョブに追加されます (デバイスの応答に関係なく)。 スキャン結果をエクスポートできます。

## <a name="device-inventory"></a>デバイス一覧

新しく検出されたデバイスは、[デバイス インベントリ] ページの [新しい **ネットワーク** デバイス] タブ **に表示** されます。 デバイスが更新されるまで、評価ジョブを追加するまでに最大 2 時間かかる場合があります。

> [!div class="mx-imgBorder"]
> ![[デバイス インベントリ] の [ネットワーク デバイス] セクション。](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="network-scanner-installation-has-failed"></a>ネットワーク スキャナーのインストールに失敗しました

ファイアウォール設定で、許可されているドメインに必要な URL が追加されるのを確認します。 また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従ってプロキシ [設定が構成されていることを確認します](configure-proxy-internet.md)。

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>Web Microsoft.com/devicelogin が表示されない

必要な URL がファイアウォールで許可されているドメインに追加されるのを確認します。 また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従ってプロキシ [設定が構成されていることを確認します](configure-proxy-internet.md)。

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>数時間後にネットワーク デバイスがデバイス インベントリに表示されない

スキャン結果は、評価ジョブの構成が完了した後に行った最初のスキャンの数時間後に更新する必要があります。

デバイスがまだ表示されない場合は、ネットワーク スキャナーをインストールした評価デバイスでサービス 'MdatpNetworkScanService' が実行されていることを確認し、関連する評価ジョブ構成で "スキャンの実行" を実行します。

5 分後に結果が得られた場合は、サービスを再起動します。

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>デバイスの最終表示時間が 24 時間を超える

スキャナーが正しく実行されていることを確認します。 次に、スキャン定義に移動し、[テストの実行] を選択します。 関連する IP アドレスから返されるエラー メッセージを確認します。

### <a name="required-threat-and-vulnerability-management-user-permission"></a>必須脅威と脆弱性の管理ユーザーアクセス許可

登録が完了し、エラーが発生しました。"新しいエージェントを追加するための十分なアクセス許可がないように見えます。 必要なアクセス許可は、「Defender のセキュリティ設定を管理する」です。

任意のキーを押して終了します。

必要なアクセス許可を割り当てるには、システム管理者に問い合わせてください。 または、別の関連メンバーにサインイン コードとリンクを提供してサインイン プロセスを支援します。

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>登録プロセスでコマンド ラインの指定されたリンクを使用して登録プロセスが失敗する

別のブラウザーを試したり、サインイン リンクとコードを別のデバイスにコピーしたりします。

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>テキストが小さすぎるか、コマンド ラインからテキストをコピーできない

デバイスのコマンド ライン設定を変更して、テキスト サイズのコピーと変更を許可します。

## <a name="related-articles"></a>関連記事

- [デバイス一覧](machines-view-overview.md)
- [高度な機能を構成する](advanced-features.md)
