---
title: ネットワーク デバイスの検出と脆弱性の管理
description: スイッチ、ルーター、WLAN コントローラー、ファイアウォールのオペレーティング システムで、セキュリティに関する推奨事項と脆弱性の検出を利用できるようになりました。
keywords: ネットワーク デバイス、ネットワーク デバイスの脆弱性検出、スイッチのオペレーティング システム、ルーター、WLAN コントローラー、ファイアウォール
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
ms.openlocfilehash: f5c2f1c7c73f150c02192fa7e275a07b12c64c79
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65438380"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>ネットワーク デバイスの検出と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]
> 2021\) 年 4 月 13 日に公開された [ネットワーク デバイスの検出と脆弱性評価](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548)のブログ\(では、Defender for Endpoint の新しい **ネットワーク デバイス検出** 機能に関する分析情報を提供します。 この記事では、 **ネットワーク デバイス検出** が対処するように設計されている課題の概要と、これらの新機能の使用を開始する方法に関する詳細を説明します。

ネットワーク検出機能は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータルとMicrosoft 365 Defender</a> コンソールの [**デバイス インベントリ**] セクションで利用できます。

指定されたMicrosoft Defender for Endpoint デバイスは、構成済みネットワーク デバイスの定期的な認証スキャンを実行するために、各ネットワーク セグメントで使用されます。 検出されると、Defender for Endpoint の脅威と脆弱性の管理機能により、検出されたスイッチ、ルーター、WLAN コントローラー、ファイアウォール、VPN ゲートウェイをセキュリティで保護するための統合ワークフローが提供されます。

ネットワーク デバイスが検出および分類されると、セキュリティ管理者は最新のセキュリティに関する推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。

## <a name="approach"></a>方法

Defender for Endpoint にはネットワーク デバイス自体にセンサーが組み込まれていないため、ネットワーク デバイスは標準エンドポイントとして管理されません。 このような種類のデバイスでは、リモート スキャンでデバイスから必要な情報を取得するエージェントレス アプローチが必要です。 ネットワーク トポロジと特性に応じて、1 台のデバイスまたはMicrosoft Defender for Endpointにオンボードされた少数のデバイスが、SNMP (読み取り専用) を使用してネットワーク デバイスの認証スキャンを実行します。

次の 2 種類のデバイスに注意してください。

- **評価デバイス**: ネットワーク デバイスのスキャンに使用する、既にオンボードされているデバイス。
- **ネットワーク デバイス**: スキャンしてオンボードする予定のネットワーク デバイス。

### <a name="vulnerability-management-for-network-devices"></a>ネットワーク デバイスの脆弱性管理

ネットワーク デバイスが検出および分類されると、セキュリティ管理者は最新のセキュリティに関する推奨事項を受け取り、組織全体に展開されたネットワーク デバイスで最近検出された脆弱性を確認できます。

## <a name="operating-systems-that-are-supported"></a>サポートされているオペレーティング システム

現在、次のオペレーティング システムがサポートされています。

- Cisco IOS、IOS-XE、NX-OS
- Juniper JUNOS
- HPE ArubaOS、Procurve Switch Software
- Palo Alto Networks PAN-OS

顧客の使用状況から収集されたデータに基づいて、より多くのネットワーク ベンダーと OS が時間の経過と共に追加されます。 そのため、この一覧で指定されていない場合でも、すべてのネットワーク デバイスを構成することをお勧めします。

## <a name="how-to-get-started"></a>始める方法

最初の手順では、認証されたネットワーク スキャンを実行するデバイスを選択します。

1. スキャンを計画しているネットワーク デバイスの管理ポートへのネットワーク接続を持つ Defender for Endpoint オンボード デバイス (クライアントまたはサーバー) を決定します。

2. Defender for Endpoint 評価デバイスとターゲット ネットワーク デバイス間の SNMP トラフィックを許可する必要があります (ファイアウォールなど)。

3. 脆弱性について評価するネットワーク デバイス (Cisco スイッチや Palo Alto Networks ファイアウォールなど) を決定します。

4. 構成されているすべてのネットワーク デバイスで SNMP 読み取り専用が有効になっていることを確認し、Defender for Endpoint 評価デバイスが構成済みのネットワーク デバイスに対してクエリを実行できるようにします。 この機能の適切な機能には、'SNMP 書き込み' は必要ありません。

5. スキャンするネットワーク デバイス (またはこれらのデバイスがデプロイされているサブネット) の IP アドレスを取得します。

6. ネットワーク デバイスの SNMP 資格情報を取得します (たとえば、Community String、noAuthNoPriv、authNoPriv、authPriv)。 新しい評価ジョブを構成するときは、資格情報を指定する必要があります。

7. プロキシ クライアント構成: Defender for Endpoint デバイス プロキシの要件以外に追加の構成は必要ありません。

8. ネットワーク スキャナーの認証と正常な動作を許可するには、次のドメイン/URL を追加することが不可欠です。

    - login.windows.net
    - \*.security.microsoft.com
    - login.microsoftonline.com
    - \*.blob.core.windows.net/networkscannerstable/\*

    > [!NOTE]
    > 許可されたデータ収集のドキュメント化された Defender for Endpoint の一覧で、すべての URL が指定されているわけではありません。

## <a name="permissions"></a>アクセス許可

評価ジョブを構成するには、次のユーザーアクセス許可オプションが必要です。 **Defender でセキュリティ設定を管理** します。 ロールの **設定**\>に移動すると、アクセス許可を見 **つけることができます。** 詳細については、「[ロールベースのアクセス制御のロールの作成と管理](user-roles.md)」を参照してください。

## <a name="install-the-network-scanner"></a>ネットワーク スキャナーをインストールする

1. **Microsoft 365セキュリティ** \> **設定** \> **Endpoints** \> **Assessment ジョブ** (**[ネットワーク評価**] の下) に移動します。
    1. Microsoft 365 Defender ポータルで、[評価ジョブ] ページ設定 >移動します。

2. ネットワーク スキャナーをダウンロードし、指定された Defender for Endpoint 評価デバイスにインストールします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/assessment-jobs-download-scanner.png" alt-text="[スキャナーのダウンロード] ボタン" lightbox="images/assessment-jobs-download-scanner.png":::

## <a name="network-scanner-installation--registration"></a>ネットワーク スキャナーのインストール&登録

サインイン プロセスは、指定された評価デバイス自体または他のデバイス (個人用クライアント デバイスなど) で完了できます。

> [!NOTE]
> ユーザーがサインインするアカウントとサインイン プロセスの完了に使用するデバイスの両方が、デバイスがMicrosoft Defender for Endpointにオンボードされているのと同じテナント内にある必要があります。

ネットワーク スキャナーの登録プロセスを完了するには、

1. コマンド ラインに表示される URL をコピーして従い、指定されたインストール コードを使用して登録プロセスを完了します。

    > [!NOTE]
    > URL をコピーできるように、コマンド プロンプトの設定を変更する必要がある場合があります。

2. コードを入力し、Defender for Endpoint アクセス許可を持つ Microsoft アカウントを使用してサインインします。"Defender でセキュリティ設定を管理する" というアクセス許可を持ちます。

3. 完了すると、サインインしたことを確認するメッセージが表示されます。

## <a name="configure-a-new-assessment-job"></a>新しい評価ジョブを構成する

**設定** の [評価ジョブ] ページで、[**ネットワーク評価ジョブの追加**] を選択します。 セットアップ プロセスに従って、定期的にスキャンしてデバイス インベントリに追加するネットワーク デバイスを選択します。

ネットワーク デバイス インベントリ内のデバイスの重複を防ぐために、各 IP アドレスが複数の評価デバイス間で 1 回だけ構成されていることを確認します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/assessment-jobs-add.png" alt-text="[ネットワーク評価ジョブの追加] ボタン" lightbox="images/assessment-jobs-add.png":::

ネットワーク評価ジョブステップの追加:

1. "評価ジョブ" の名前と、ネットワーク スキャナーがインストールされた 'Assessment device' を選択します。 このデバイスは、定期的に認証されたスキャンを実行します。

2. スキャンするターゲット ネットワーク デバイス (またはこれらのデバイスがデプロイされているサブネット) の IP アドレスを追加します。

3. ターゲット ネットワーク デバイスの必要な SNMP 資格情報を追加します。

4. 新しく構成されたネットワーク評価ジョブを保存して、定期的なネットワーク スキャンを開始します。

### <a name="scan-and-add-network-devices"></a>ネットワーク デバイスをスキャンして追加する

セットアップ プロセス中に、1 回限りのテスト スキャンを実行して、次のことを確認できます。

- Defender for Endpoint 評価デバイスと構成されたターゲット ネットワーク デバイスの間には接続があります。
- 構成された SNMP 資格情報が正しい。

各評価デバイスでは、最大 1,500 件の成功した IP アドレス スキャンをサポートできます。 たとえば、100 個の IP アドレスのみが正常な結果を返す 10 個の異なるサブネットをスキャンする場合、同じ評価デバイス上の他のサブネットから 1,400 個の IP 追加アドレスをスキャンできます。

スキャンする IP アドレス範囲/サブネットが複数ある場合、テスト スキャンの結果が表示されるまでに数分かかります。 テスト スキャンは、最大 1,024 個のアドレスで使用できます。

結果が表示されたら、定期的なスキャンに含めるデバイスを選択できます。 スキャン結果の表示をスキップすると、構成されたすべての IP アドレスが (デバイスの応答に関係なく) ネットワーク評価ジョブに追加されます。 スキャン結果はエクスポートすることもできます。

## <a name="device-inventory"></a>デバイス一覧

新しく検出されたデバイスは、[**デバイス インベントリ**] ページの新しい [**ネットワーク デバイス**] タブに表示されます。 デバイスが更新されるまで、評価ジョブを追加してから最大 2 時間かかる場合があります。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/assessment-jobs-device-inventory.png" alt-text="デバイス インベントリの [ネットワーク デバイス] セクション" lightbox="images/assessment-jobs-device-inventory.png":::

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="network-scanner-installation-has-failed"></a>ネットワーク スキャナーのインストールに失敗しました

ファイアウォール設定で許可されているドメインに必要な URL が追加されていることを確認します。 また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従って [プロキシ設定が構成](configure-proxy-internet.md)されていることを確認します。

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>Microsoft.com/devicelogin Web ページが表示されませんでした

ファイアウォールで許可されているドメインに必要な URL が追加されていることを確認します。 また、「デバイス プロキシとインターネット接続の設定を構成する」の説明に従って [プロキシ設定が構成](configure-proxy-internet.md)されていることを確認します。

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>数時間後にネットワーク デバイスがデバイス インベントリに表示されない

評価ジョブの構成が完了した後に行われた最初のスキャンの数時間後に、スキャン結果を更新する必要があります。

デバイスがまだ表示されていない場合は、ネットワーク スキャナーをインストールした評価デバイスでサービス 'MdatpNetworkScanService' が実行されていることを確認し、関連する評価ジョブ構成で "スキャンの実行" を実行します。

5 分後も結果が得られない場合は、サービスを再起動します。

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>最後に表示された時間が 24 時間を超えるデバイス

スキャナーが正しく実行されていることを検証します。 次に、スキャン定義に移動し、[テストの実行] を選択します。 関連する IP アドレスから返されるエラー メッセージを確認します。

### <a name="required-threat-and-vulnerability-management-user-permission"></a>ユーザーアクセス許可脅威と脆弱性の管理必須

"新しいエージェントを追加するための十分なアクセス許可がないようです。 必要なアクセス許可は "Defender でセキュリティ設定を管理する" です。

任意のキーを押して終了します。

システム管理者に、必要なアクセス許可を割り当ててもらう。 または、別の関連するメンバーにサインイン コードとリンクを提供してサインイン プロセスを支援するように依頼します。

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>登録プロセスでコマンド ラインで指定されたリンクを使用して登録プロセスが失敗する

別のブラウザーを試すか、サインイン リンクとコードを別のデバイスにコピーします。

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>テキストが小さすぎるか、コマンド ラインからテキストをコピーできない

デバイスのコマンド ライン設定を変更して、テキスト サイズのコピーと変更を許可します。

## <a name="related-articles"></a>関連資料

- [デバイス一覧](machines-view-overview.md)
- [高度な機能を構成する](advanced-features.md)
