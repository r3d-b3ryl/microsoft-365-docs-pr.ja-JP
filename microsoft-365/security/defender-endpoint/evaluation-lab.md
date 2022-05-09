---
title: Microsoft Defender for Endpoint評価ラボ
description: Microsoft Defender for Endpoint機能、攻撃シミュレーションの実行、脅威の防止、検出、修復方法について説明します。
keywords: Microsoft Defender for Endpointの評価, 評価, ラボ, シミュレーション, Windows 10, Windows Server 2019, 評価ラボ
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
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a>Microsoft Defender for Endpoint評価ラボ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

包括的なセキュリティ製品評価を実施することは、エンド ツー エンドの攻撃シミュレーションを実際に実行する前に、煩雑な環境とデバイス構成を必要とする複雑なプロセスになる可能性があります。 複雑さに加えて、シミュレーションアクティビティ、アラート、および結果が評価中に反映される場所を追跡する課題があります。

Microsoft Defender for Endpoint評価ラボは、デバイスと環境の構成の複雑さを排除するように設計されているため、プラットフォームの機能の評価、シミュレーションの実行、防止、検出、修復機能の動作の確認に集中できます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUM]

簡単なセットアップ エクスペリエンスを使用すると、独自のテスト シナリオと事前に作成されたシミュレーションの実行に集中して、Defender for Endpoint のパフォーマンスを確認できます。

自動調査、高度な捜索、脅威分析など、プラットフォームの強力な機能にフル アクセスできるため、Defender for Endpoint が提供する包括的な保護スタックをテストできます。

Windows 10、Windows 11、Windows Server 2019、Windows Server 2016、Linux (Ubuntu) デバイスを追加して、最新の OS バージョンと適切なセキュリティ コンポーネントをインストールし、Office 2019 Standard をインストールできます。

脅威シミュレーターをインストールすることもできます。 Defender for Endpoint は、業界をリードする脅威シミュレーション プラットフォームと提携し、ポータルから離れることなく Defender for Endpoint 機能をテストするのに役立ちます。

任意のシミュレーターをインストールし、評価ラボ内でシナリオを実行し、プラットフォームのパフォーマンスを即座に確認できます。すべて追加コストなしで便利に利用できます。 また、シミュレーション カタログからアクセスして実行できるさまざまなシミュレーションに簡単にアクセスできます。

## <a name="before-you-begin"></a>開始する前に

[ライセンス要件](minimum-requirements.md#licensing-requirements)を満たすか、評価ラボにアクセスするためにMicrosoft Defender for Endpointへの試用版アクセス権を持っている必要があります。

次に対する **セキュリティ設定の管理** アクセス許可が必要です。

- ラボを作成する
- デバイスを作成する
- パスワードのリセット
- シミュレーションを作成する

ロールベースのアクセス制御 (RBAC) を有効にし、少なくとも 1 つのマシン グループを作成した場合、ユーザーはすべてのマシン グループにアクセスできる必要があります。

詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink)

## <a name="get-started-with-the-lab"></a>ラボでの概要

メニューからラボにアクセスできます。 ナビゲーション メニューで、 **評価ラボ>評価とチュートリアル** を選択します。

> [!NOTE]
>
> - 選択した環境構造の種類に応じて、デバイスはアクティブ化日から指定された時間に使用できます。
> - 各環境は、限られた一連のテスト デバイスでプロビジョニングされます。 プロビジョニングされたデバイスを使い切って削除したら、さらにデバイスを要求できます。
> - ラボ リソースの要求は、月に 1 回行うことができます。

ラボは既に存在しますか? 新しい脅威シミュレーターを有効にし、アクティブなデバイスを持っていることを確認します。

## <a name="setup-the-evaluation-lab"></a>評価ラボをセットアップする

1. ナビゲーション ウィンドウで、[ **評価&チュートリアル** \> **評価ラボ**] を選択し、[ **セットアップ ラボ**] を選択します。

   :::image type="content" source="../../media/evaluationtutormenu.png" alt-text="評価ラボのウェルカム ページ" lightbox="../../media/evaluationtutormenu.png":::

2. 評価のニーズに応じて、より長い期間のデバイスが少ない環境をセットアップするか、より短い期間のデバイスを多く設定するかを選択できます。 お好みのラボ構成を選択し、[ **次へ**] を選択します。

    :::image type="content" source="images/lab-creation-page.png" alt-text="ラボ構成オプション" lightbox="images/lab-creation-page.png":::

3. (省略可能)ラボに脅威シミュレーターをインストールすることを選択できます。

    :::image type="content" source="images/install-agent.png" alt-text="シミュレーターエージェントのインストール ページ" lightbox="images/install-agent.png":::

   > [!IMPORTANT]
   > 最初に、条項と情報共有に関する声明に同意し、同意する必要があります。

4. 使用する脅威シミュレーション エージェントを選択し、詳細を入力します。 後で脅威シミュレーターをインストールすることもできます。 ラボのセットアップ中に脅威シミュレーション エージェントをインストールすることを選択した場合は、追加したデバイスに簡単にインストールできるという利点があります。

   :::image type="content" source="images/lab-setup-summary.png" alt-text="概要ページ" lightbox="images/lab-setup-summary.png":::

5. 概要を確認し、[ **セットアップ ラボ]** を選択します。

ラボのセットアップ プロセスが完了したら、デバイスを追加してシミュレーションを実行できます。

## <a name="add-devices"></a>デバイスを追加する

環境にデバイスを追加すると、Defender for Endpoint によって接続の詳細が適切に構成されたデバイスが設定されます。 Windows 10、Windows 11、Windows Server 2019、Windows Server 2016、Linux (Ubuntu) を追加できます。

デバイスは、最新バージョンの OS と Office 2019 Standard のほか、Java、Python、SysIntenals などの他のアプリで構成されます。

ラボのセットアップ中に脅威シミュレーターを追加することを選択した場合、すべてのデバイスに、追加したデバイスに脅威シミュレーター エージェントがインストールされます。

デバイスは、推奨されるWindowsセキュリティ コンポーネントをオンにして監査モードでテナントに自動的にオンボードされます。お客様の側で作業を行う必要はありません。

テスト デバイスでは、次のセキュリティ コンポーネントが事前に構成されています。

- [攻撃面の減少](attack-surface-reduction.md)
- [事前ブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [制御されたフォルダー アクセス](controlled-folders.md)
- [エクスプロイト保護](enable-exploit-protection.md)
- [ネットワーク保護](network-protection.md)
- [望ましくない可能性があるアプリケーション検出](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)
- [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

> [!NOTE]
> Microsoft Defender ウイルス対策はオンになります (監査モードではありません)。 Microsoft Defender ウイルス対策シミュレーションの実行がブロックされている場合は、Windows セキュリティを使用してデバイスのリアルタイム保護をオフにすることができます。 詳細については、「 [常時オン保護を構成する](configure-real-time-protection-microsoft-defender-antivirus.md)」を参照してください。

自動調査の設定は、テナントの設定に依存します。 既定では、半自動化されるように構成されます。 詳細については、「 [自動調査の概要](automated-investigations.md)」を参照してください。

> [!NOTE]
> テスト デバイスへの接続は RDP を使用して行われます。 ファイアウォール設定で RDP 接続が許可されていることを確認します。

1. ダッシュボードで [デバイスの **追加**] を選択します。

2. 追加するデバイスの種類を選択します。 Windows 10、Windows 11、Windows Server 2019、Windows Server 2016、Linux (Ubuntu) の追加を選択できます。

   :::image type="content" source="../../media/add-machine-optionsnew.png" alt-text="デバイス オプションを使用したラボのセットアップ" lightbox="../../media/add-machine-optionsnew.png":::

   > [!NOTE]
   > デバイスの作成プロセスで問題が発生した場合は、通知が送信され、新しい要求を送信する必要があります。 デバイスの作成に失敗した場合、許可されたクォータ全体に対してカウントされません。

3. 接続の詳細が表示されます。 [ **コピー** ] を選択して、デバイスのパスワードを保存します。

   > [!NOTE]
   > パスワードは 1 回だけ表示されます。 後で使用できるように、必ず保存してください。

    :::image type="content" source="../../media/add-machine-eval-lab-new.png" alt-text="接続の詳細と共に追加されたデバイス" lightbox="../../media/add-machine-eval-lab-new.png":::

4. デバイスのセットアップが開始されます。 これには、最大で約 30 分かかる場合があります。

5. [ **デバイス] タブ** を選択して、テスト デバイスの状態、リスクと露出レベル、シミュレーターのインストールの状態を確認します。

   :::image type="content" source="images/machines-tab.png" alt-text="[デバイス] タブ" lightbox="images/machines-tab.png":::
    

   > [!TIP]
   > [ **シミュレーターの状態** ] 列で、情報アイコンにマウス ポインターを合わせると、エージェントのインストール状態を確認できます。


## <a name="request-for-more-devices"></a>その他のデバイスの要求

既存のすべてのデバイスが使用および削除された場合は、より多くのデバイスを要求できます。 ラボ リソースの要求は、月に 1 回行うことができます。

1. 評価ラボ ダッシュボードで、[ **その他のデバイスの要求**] を選択します。

   :::image type="content" source="images/request-more-devices.png" alt-text="[その他のデバイスの要求] オプション" lightbox="images/request-more-devices.png":::

2. 構成を選択します。
3. 要求を送信します。

要求が正常に送信されると、緑色の確認バナーと最後の提出日が表示されます。

要求の状態は、[ **ユーザー アクション]** タブで確認できます。これは、数時間以内に承認されます。

承認されると、要求されたデバイスがラボのセットアップに追加され、より多くのデバイスを作成できるようになります。

> [!TIP]
> ラボの詳細を確認するには、シミュレーション ライブラリを忘れないでください。

## <a name="simulate-attack-scenarios"></a>攻撃シナリオをシミュレートする

テスト デバイスに接続して独自の攻撃シミュレーションを実行するには、テスト デバイスを使用します。

次を使用して、攻撃シナリオをシミュレートできます。

- ["Do It Yourself" 攻撃シナリオ](https://security.microsoft.com/tutorials/all)
- 脅威シミュレーター

[高度な捜索](advanced-hunting-overview.md)を使用して、データと[脅威分析](threat-analytics.md)にクエリを実行して、新たな脅威に関するレポートを表示することもできます。

### <a name="do-it-yourself-attack-scenarios"></a>Do-it-yourself 攻撃シナリオ

事前に作成されたシミュレーションを探している場合は、 ["Do It Yourself" 攻撃シナリオ](https://security.microsoft.com/tutorials/all)を使用できます。 これらのスクリプトは、安全で文書化されており、使いやすいです。 これらのシナリオでは、Defender for Endpoint 機能が反映され、調査エクスペリエンスについて説明します。

> [!NOTE]
> テスト デバイスへの接続は RDP を使用して行われます。 ファイアウォール設定で RDP 接続が許可されていることを確認します。

1. デバイスにConnectし、**Connect** を選択して攻撃シミュレーションを実行します。

    :::image type="content" source="images/test-machine-table.png" alt-text="テスト デバイスの [Connect] ボタン" lightbox="images/test-machine-table.png":::


   :::image type="content" source="images/remote-connection.png" alt-text="リモート デスクトップ接続画面" lightbox="images/remote-connection.png":::

    **Linux デバイス** の場合:ローカル SSH クライアントと指定されたコマンドを使用する必要があります。 


    > [!NOTE]
    > 初期セットアップ中にパスワードのコピーが保存されていない場合は、メニューから [パスワードのリセット] を選択して **パスワードをリセット** できます。
    >
    > :::image type="content" source="images/reset-password-test-machine.png" alt-text="[パスワードのリセット] オプション" lightbox="images/reset-password-test-machine.png":::
    >
    > デバイスの状態が "パスワード リセットの実行" に変更され、数分後に新しいパスワードが表示されます。

3. デバイスの作成手順で表示されたパスワードを入力します。

   :::image type="content" source="images/enter-password.png" alt-text="資格情報を入力する画面" lightbox="images/enter-password.png":::

4. デバイスで Do-it-yourself 攻撃シミュレーションを実行します。

### <a name="threat-simulator-scenarios"></a>脅威シミュレーターのシナリオ

ラボのセットアップ中にサポートされている脅威シミュレーターのいずれかをインストールすることを選択した場合は、評価ラボ デバイスで組み込みのシミュレーションを実行できます。

サード パーティのプラットフォームを使用して脅威シミュレーションを実行することは、ラボ環境の範囲内でMicrosoft Defender for Endpoint機能を評価するのに適した方法です。

> [!NOTE]
>
> シミュレーションを実行する前に、次の要件が満たされていることを確認してください。
>
> - デバイスを評価ラボに追加する必要があります
> - 脅威シミュレーターは評価ラボにインストールする必要があります

1. ポータルで [ **シミュレーションの作成**] を選択します。

2. 脅威シミュレーターを選択します。

   :::image type="content" source="images/select-simulator.png" alt-text="脅威シミュレーターの選択" lightbox="images/select-simulator.png":::

3. シミュレーションを選択するか、シミュレーション ギャラリーを参照して、使用可能なシミュレーションを参照します。

    シミュレーション ギャラリーには、次の情報からアクセスできます。
    - **シミュレーションの概要** タイルまたは
    - ナビゲーション ウィンドウの **[評価とチュートリアル** \> **] シミュレーション&チュートリアル** から移動し、[ **シミュレーション カタログ**] を選択します。

4. シミュレーションを実行するデバイスを選択します。

5. [ **シミュレーションの作成]** を選択します。

6. [シミュレーション] タブを選択して、シミュレーションの進行状況 **を** 表示します。シミュレーションの状態、アクティブなアラート、その他の詳細を表示します。

   :::image type="content" source="images/simulations-tab.png" alt-text="[シミュレーション] タブ" lightbox="images/simulations-tab.png":::

シミュレーションを実行した後は、ラボの進行状況バーを確認し、**自動調査と修復をトリガーしたMicrosoft Defender for Endpoint** を調べてください。 機能によって収集および分析された証拠を確認します。

豊富なクエリ言語と生のテレメトリを使用して高度な捜索を通じて攻撃の証拠を探し、脅威分析に記載されている世界中の脅威を確認します。

## <a name="simulation-gallery"></a>シミュレーション ギャラリー

Microsoft Defender for Endpointは、ポータル内からプラットフォームの機能をテストするための便利なアクセスを提供するために、さまざまな脅威シミュレーション プラットフォームと提携しています。

メニューの [  **シミュレーションとチュートリアル** \> シミュレーション] カタログに移動して、使用可能なすべての **シミュレーション**  を表示します。

サポートされているサードパーティの脅威シミュレーション エージェントの一覧が一覧表示され、特定の種類のシミュレーションと詳細な説明がカタログに表示されます。

カタログから直接使用可能な任意のシミュレーションを簡単に実行できます。

:::image type="content" source="images/simulations-catalog.png" alt-text="シミュレーション カタログ" lightbox="images/simulations-catalog.png":::

各シミュレーションには、攻撃シナリオの詳細な説明と、実行する高度な捜索クエリのサンプルとして使用される MITRE 攻撃手法などの参照が付属しています。

**例:**

:::image type="content" source="images/simulation-details-aiq.png" alt-text="永続化メソッドのシミュレーションの説明の詳細ウィンドウの例" lightbox="images/simulation-details-aiq.png":::

:::image type="content" source="images/simulation-details-sb.png" alt-text="APT29 のシミュレーションの詳細" lightbox="images/simulation-details-sb.png":::

## <a name="evaluation-report"></a>評価レポート

ラボ レポートは、デバイスで実行されたシミュレーションの結果をまとめたものです。

:::image type="content" source="images/eval-report.png" alt-text="評価レポート" lightbox="images/eval-report.png":::

一目で、次の情報をすぐに確認できます。

- トリガーされたインシデント
- 生成されたアラート
- 露出レベルに関する評価
- 観察された脅威カテゴリ
- 検出ソース
- 自動化された調査

## <a name="provide-feedback"></a>フィードバックの提供

お客様のフィードバックは、高度な攻撃から環境を保護するうえで役立ちます。 製品の機能と評価結果から、エクスペリエンスと印象を共有します。

**[フィードバックの提供**] を選択して、お客様の意見をお聞かせください。

:::image type="content" source="images/send-us-feedback-eval-lab.png" alt-text="フィードバック ページ" lightbox="images/send-us-feedback-eval-lab.png":::
