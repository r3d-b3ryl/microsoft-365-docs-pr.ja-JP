---
title: Microsoft Defender for Endpoint 評価ラボ
description: Microsoft Defender for Endpoint の機能について説明し、攻撃シミュレーションを実行し、脅威を防止、検出、修復する方法を確認します。
keywords: エンドポイント用 Microsoft Defender の評価、評価、ラボ、シミュレーション、Windows 10、Windows Server 2019、評価ラボ
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.prod: m365-security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2b4c1cd9c37921fbb54633c0fc1bf2e42d308081
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472883"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a>Microsoft Defender for Endpoint 評価ラボ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

包括的なセキュリティ製品評価を行う場合、エンドツーエンドの攻撃シミュレーションを実際に実行する前に、複雑な環境とデバイス構成が必要になる複雑なプロセスになる可能性があります。 複雑さを加えるのは、シミュレーション アクティビティ、アラート、および結果が評価中に反映される場所を追跡する際の課題です。

Microsoft Defender for Endpoint 評価ラボは、プラットフォームの機能の評価、シミュレーションの実行、予防、検出、修復機能の実行に集中できるよう、デバイスと環境構成の複雑さを排除するように設計されています。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUM]

セットアップの簡略化により、独自のテスト シナリオと事前に作成されたシミュレーションの実行に集中して、Defender for Endpoint のパフォーマンスを確認できます。

自動調査、高度な狩猟、脅威分析など、プラットフォームの強力な機能に完全にアクセスでき、Defender for Endpoint が提供する包括的な保護スタックをテストできます。

Windows 10、Windows 11、Windows Server 2019、Windows Server 2016、および Linux (Ubuntu) デバイスを追加して、最新の OS バージョンと適切なセキュリティ コンポーネントと Office 2019 Standard をインストールするように事前に構成できます。

また、脅威シミュレーターをインストールできます。 Defender for Endpoint は、業界をリードする脅威シミュレーション プラットフォームと提携し、ポータルから出ることなく Defender for Endpoint の機能をテストするのに役立ちます。

お好みのシミュレーターをインストールし、評価ラボ内でシナリオを実行し、プラットフォームのパフォーマンスを即座に確認できます。 また、さまざまなシミュレーションにアクセスして、シミュレーション カタログから実行できます。

## <a name="before-you-begin"></a>はじめに

評価ラボにアクセスするには、ライセンス[](minimum-requirements.md#licensing-requirements)要件を満たすか、Microsoft Defender for Endpoint への試用版アクセス権が必要です。

次のセキュリティ設定 **の管理権限** が必要です。

- ラボを作成する
- デバイスの作成
- パスワードのリセット
- シミュレーションの作成

役割ベースのアクセス制御 (RBAC) を有効にし、少なくとも 1 つのコンピューター グループを作成した場合、ユーザーはすべてのコンピューター グループにアクセスできる必要があります。

詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink)

## <a name="get-started-with-the-lab"></a>ラボの使用を開始する

メニューからラボにアクセスできます。 ナビゲーション メニューで、[評価とチュートリアル] **を選択し、[>] を選択します**。

> [!NOTE]
>
> - 選択した環境構造の種類に応じて、デバイスはライセンス認証日から指定された時間数で利用できます。
> - 各環境は、制限された一連のテスト デバイスでプロビジョニングされます。 プロビジョニングされたデバイスを使用し、それらを削除した場合は、より多くのデバイスを要求できます。
> - 月に 1 回、ラボ リソースを要求できます。

ラボを既に持っていますか? 新しい脅威シミュレーターを有効にし、アクティブなデバイスを持っている必要があります。

## <a name="setup-the-evaluation-lab"></a>評価ラボのセットアップ

1. ナビゲーション ウィンドウで、[評価] を選択 **&評価** \> **ラボ** で、[セットアップ ラボ] **を選択します**。

   :::image type="content" source="../../media/evaluationtutormenu.png" alt-text="評価ラボのウェルカム ページ" lightbox="../../media/evaluationtutormenu.png":::

2. 評価のニーズに応じて、より長い期間、またはより短い期間のデバイスが少ない環境をセットアップできます。 優先するラボ構成を選択し、[次へ] を **選択します**。

    :::image type="content" source="images/lab-creation-page.png" alt-text="ラボ構成オプション" lightbox="images/lab-creation-page.png":::

3. (省略可能)ラボに脅威シミュレーターをインストールできます。

    :::image type="content" source="images/install-agent.png" alt-text="[シミュレーター エージェントのインストール] ページ" lightbox="images/install-agent.png":::

   > [!IMPORTANT]
   > 最初に、条項と情報共有に関する声明に同意し、同意する必要があります。

4. 使用する脅威シミュレーション エージェントを選択し、詳細を入力します。 また、後で脅威シミュレーターをインストールすることもできます。 ラボのセットアップ中に脅威シミュレーション エージェントをインストールする場合は、追加するデバイスに脅威シミュレーション エージェントを簡単にインストールできます。

   :::image type="content" source="images/lab-setup-summary.png" alt-text="概要ページ" lightbox="images/lab-setup-summary.png":::

5. 概要を確認し、[セットアップ ラボ] **を選択します**。

ラボのセットアップ プロセスが完了したら、デバイスを追加してシミュレーションを実行できます。

## <a name="add-devices"></a>デバイスを追加する

環境にデバイスを追加すると、Defender for Endpoint は接続の詳細を示す構成済みのデバイスをセットアップします。 サーバー 2019、Windows 10 11、Windowsサーバー 2019、Windows Linux (Ubuntu) Windows Server 2016追加できます。

デバイスは、OS および Office 2019 Standard の最新バージョンと、Java、Python、SysIntenals などの他のアプリで構成されます。

ラボのセットアップ中に脅威シミュレーターの追加を選択した場合、すべてのデバイスに追加するデバイスに脅威シミュレーター エージェントがインストールされます。

デバイスは自動的にテナントにオンボードされ、推奨されるセキュリティ コンポーネントWindowsオンおよび監査モードになります。作業は不要です。

次のセキュリティ コンポーネントは、テスト デバイスで事前に構成されています。

- [攻撃面の減少](attack-surface-reduction.md)
- [事前ブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [制御されたフォルダー アクセス](controlled-folders.md)
- [エクスプロイト保護](enable-exploit-protection.md)
- [ネットワーク保護](network-protection.md)
- [望ましくない可能性のあるアプリケーションの検出](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)
- [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

> [!NOTE]
> Microsoft Defender ウイルス対策オンになります (監査モードではありません)。 シミュレーションMicrosoft Defender ウイルス対策ブロックする場合は、デバイスでリアルタイム保護をオフWindows セキュリティ。 詳細については、「Configure [always-on protection」を参照してください](configure-real-time-protection-microsoft-defender-antivirus.md)。

自動調査の設定は、テナントの設定に依存します。 既定では半自動で構成されます。 詳細については、「自動調査 [の概要」を参照してください](automated-investigations.md)。

> [!NOTE]
> テスト デバイスへの接続は RDP を使用して行われます。 ファイアウォールの設定で RDP 接続が許可されている必要があります。

1. ダッシュボードで、[デバイスの追加 **] を選択します**。

2. 追加するデバイスの種類を選択します。 サーバー 2019、Windows 10 11、Windows、Windows Linux (Ubuntu) Windows Server 2016を追加できます。

   :::image type="content" source="../../media/add-machine-optionsnew.png" alt-text="デバイス オプションを使用したラボセットアップ" lightbox="../../media/add-machine-optionsnew.png":::

   > [!NOTE]
   > デバイスの作成プロセスで問題が発生した場合は、通知が送信され、新しい要求を送信する必要があります。 デバイスの作成に失敗した場合は、許可された全体的なクォータに対してカウントされません。

3. 接続の詳細が表示されます。 [ **コピー] を** 選択して、デバイスのパスワードを保存します。

   > [!NOTE]
   > パスワードは 1 回だけ表示されます。 後で使用するために必ず保存してください。

    :::image type="content" source="../../media/add-machine-eval-lab-new.png" alt-text="接続の詳細で追加されたデバイス" lightbox="../../media/add-machine-eval-lab-new.png":::

4. デバイスのセットアップが開始されます。 これには、最大で約 30 分かかる場合があります。

5. [デバイス] タブを選択して、テスト デバイスの状態、リスクと露出レベル、シミュレーターのインストールの状態 **を確認** します。

   :::image type="content" source="images/machines-tab.png" alt-text="[デバイス] タブ" lightbox="images/machines-tab.png":::
    

   > [!TIP]
   > [ **シミュレーターの状態]** 列で、情報アイコンにカーソルを合わせると、エージェントのインストール状態を確認できます。


## <a name="request-for-more-devices"></a>その他のデバイスの要求

すべての既存のデバイスを使用して削除すると、より多くのデバイスを要求できます。 月に 1 回、ラボ リソースを要求できます。

1. 評価ラボ ダッシュボードで、[その他のデバイス **を要求する] を選択します**。

   :::image type="content" source="images/request-more-devices.png" alt-text="[その他のデバイスの要求] オプション" lightbox="images/request-more-devices.png":::

2. 構成を選択します。
3. 要求を送信します。

要求が正常に送信されると、緑色の確認バナーと最後の提出日が表示されます。

要求の状態は [ユーザーの操作] タブで確認できます。これは数時間で承認されます。

承認されると、要求されたデバイスがラボ セットアップに追加され、より多くのデバイスを作成できます。

> [!TIP]
> ラボの詳細を確認するには、シミュレーション ライブラリを確認することを忘れないでください。

## <a name="simulate-attack-scenarios"></a>攻撃シナリオのシミュレーション

テスト デバイスを使用して、テスト デバイスに接続して独自の攻撃シミュレーションを実行します。

攻撃シナリオは、次の方法でシミュレートできます。

- ["Do It Yourself" 攻撃のシナリオ](https://security.microsoft.com/tutorials/all)
- 脅威シミュレーター

高度な検索を使用[してデータ](advanced-hunting-overview.md)をクエリし[](threat-analytics.md)、脅威分析を使用して、新たな脅威に関するレポートを表示することもできます。

### <a name="do-it-yourself-attack-scenarios"></a>Do-it-yourself 攻撃のシナリオ

事前に作成されたシミュレーションを探している場合は、" [Do It Yourself" 攻撃シナリオを使用できます](https://security.microsoft.com/tutorials/all)。 これらのスクリプトは安全で文書化され、使いやすいです。 これらのシナリオは、Defender for Endpoint の機能を反映し、調査のエクスペリエンスについて説明します。

> [!NOTE]
> テスト デバイスへの接続は RDP を使用して行われます。 ファイアウォールの設定で RDP 接続が許可されている必要があります。

1. Connectを選択して、デバイスにアクセスし、攻撃シミュレーション **をConnect**。

    :::image type="content" source="images/test-machine-table.png" alt-text="テスト Connectの [テスト] ボタン" lightbox="images/test-machine-table.png":::


   :::image type="content" source="images/remote-connection.png" alt-text="リモート デスクトップ接続画面" lightbox="images/remote-connection.png":::

    **Linux デバイスの場合**: ローカル SSH クライアントと指定されたコマンドを使用する必要があります。 


    > [!NOTE]
    > 初期セットアップ中にパスワードのコピーを保存しない場合は、メニューから [パスワードのリセット] を選択して **パスワードをリセット** できます。
    >
    > :::image type="content" source="images/reset-password-test-machine.png" alt-text="[パスワードのリセット] オプション" lightbox="images/reset-password-test-machine.png":::
    >
    > デバイスは状態を "パスワードリセットの実行" に変更し、数分で新しいパスワードが表示されます。

3. デバイスの作成手順中に表示されたパスワードを入力します。

   :::image type="content" source="images/enter-password.png" alt-text="資格情報を入力する画面" lightbox="images/enter-password.png":::

4. デバイスで Do-it-yourself 攻撃シミュレーションを実行します。

### <a name="threat-simulator-scenarios"></a>脅威シミュレーターのシナリオ

ラボのセットアップ中にサポートされている脅威シミュレーターのインストールを選択した場合は、評価ラボ デバイスで組み込みのシミュレーションを実行できます。

サード パーティプラットフォームを使用して脅威シミュレーションを実行すると、ラボ環境の範囲内で Microsoft Defender for Endpoint の機能を評価できます。

> [!NOTE]
>
> シミュレーションを実行する前に、次の要件を満たしていることを確認してください。
>
> - 評価ラボにデバイスを追加する必要があります
> - 脅威シミュレーターは評価ラボにインストールする必要があります

1. ポータルで [シミュレーションの作成 **] を選択します**。

2. 脅威シミュレーターを選択します。

   :::image type="content" source="images/select-simulator.png" alt-text="脅威シミュレーターの選択" lightbox="images/select-simulator.png":::

3. シミュレーションを選択するか、シミュレーション ギャラリーを参照して使用可能なシミュレーションを参照します。

    シミュレーション ギャラリーは、次の場所から取得できます。
    - シミュレーションの概要タイルの主 **な** 評価ダッシュボードまたは
    - ナビゲーション ウィンドウの [評価] と [チュートリアル **]** \> から[シミュレーション] & **をクリック** し、[シミュレーション カタログ] **を選択します**。

4. シミュレーションを実行するデバイスを選択します。

5. [シミュレーション **の作成] を選択します**。

6. [シミュレーション] タブを選択して、シミュレーションの進行状況 **を表示** します。シミュレーションの状態、アクティブなアラート、その他の詳細を表示します。

   :::image type="content" source="images/simulations-tab.png" alt-text="[シミュレーション] タブ" lightbox="images/simulations-tab.png":::

シミュレーションを実行した後、ラボの進行状況バーを表示し、 **Microsoft Defender for Endpoint** を調べ、自動調査と修復をトリガーしてください。 機能によって収集および分析された証拠を確認します。

豊富なクエリ言語と生の利用統計情報を使用して高度な検索を通じて攻撃証拠を探し、Threat analytics に記載されている世界全体の脅威を確認します。

## <a name="simulation-gallery"></a>シミュレーション ギャラリー

Microsoft Defender for Endpoint は、さまざまな脅威シミュレーション プラットフォームと提携し、ポータル内からプラットフォームの機能を簡単にテストできます。

メニューから [シミュレーションとチュートリアル]  **シミュレーション** \> カタログに移動して、使用可能なすべての **シミュレーション**  を表示します。

サポートされているサードパーティの脅威シミュレーション エージェントの一覧が一覧表示され、特定の種類のシミュレーションと詳細な説明がカタログに記載されています。

カタログから任意の使用可能なシミュレーションを簡単に実行できます。

:::image type="content" source="images/simulations-catalog.png" alt-text="シミュレーション カタログ" lightbox="images/simulations-catalog.png":::

各シミュレーションには、攻撃シナリオの詳細な説明と、使用する MITRE 攻撃手法や実行する高度な検索クエリのサンプルなどの参照が付属しています。

**例:**

:::image type="content" source="images/simulation-details-aiq.png" alt-text="永続化メソッドのシミュレーションの説明の詳細ウィンドウの例" lightbox="images/simulation-details-aiq.png":::

:::image type="content" source="images/simulation-details-sb.png" alt-text="APT29 のシミュレーションの説明の詳細" lightbox="images/simulation-details-sb.png":::

## <a name="evaluation-report"></a>評価レポート

ラボ レポートは、デバイスで実施されたシミュレーションの結果を要約します。

:::image type="content" source="images/eval-report.png" alt-text="評価レポート" lightbox="images/eval-report.png":::

一目でわかると、次の情報をすばやく確認できます。

- トリガーされたインシデント
- 生成されたアラート
- 露出レベルの評価
- 検出された脅威カテゴリ
- 検出ソース
- 自動化された調査

## <a name="provide-feedback"></a>フィードバックの提供

フィードバックは、高度な攻撃から環境を保護する上で役立ちます。 製品の機能と評価結果からエクスペリエンスとインプレッションを共有します。

[フィードバックの提供] を選択して、ご意見をお **寄せください**。

:::image type="content" source="images/send-us-feedback-eval-lab.png" alt-text="フィードバック ページ" lightbox="images/send-us-feedback-eval-lab.png":::
