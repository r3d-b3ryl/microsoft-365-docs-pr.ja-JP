---
title: Microsoft Defender for Endpoint内のファイルに対して応答アクションを実行する
description: ファイルを停止して隔離するか、ファイルをブロックしてアクティビティの詳細を確認することで、ファイル関連のアラートに対する応答アクションを実行します。
keywords: 応答、停止と検疫、ファイルのブロック、詳細な分析
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8bfa08a92a011d32cdc30e2f68052715b4075fdf
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665516"
---
# <a name="take-response-actions-on-a-file"></a>ファイルの対応措置を講じる

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-responddile-abovefoldlink)

検出された攻撃に迅速に対応するには、ファイルを停止して検疫するか、ファイルをブロックします。 ファイルに対してアクションを実行した後、アクション センターでアクティビティの詳細を確認できます。

応答アクションは、ファイルの詳細なプロファイル ページで確認できます。 このページで、新しいファイル ページを切り替えることで、 **新しい** ページレイアウトと古いページ レイアウトを切り替えることができます。 この記事の残りの部分では、新しいページ レイアウトについて説明します。

応答アクションは、ファイル ページの上部に沿って実行され、次のものが含まれます。

- ファイルの停止と検疫
- インジケーターの追加
- ファイルをダウンロードする
- 脅威のエキスパートに相談する
- アクション センター

詳細な分析のためにファイルを送信して、セキュリティで保護されたクラウド サンドボックスでファイルを実行することもできます。 分析が完了すると、ファイルの動作に関する情報を提供する詳細なレポートが表示されます。 [詳細 **分析] タブ** を選択すると、詳細な分析のためにファイルを送信し、過去のレポートを読むことができます。ファイル情報カードの下にあります。

一部のアクションには、特定のアクセス許可が必要です。 次の表では、特定のアクセス許可がポータブル実行可能ファイル (PE) ファイルと非 PE ファイルに対して実行できるアクションについて説明します。

|アクセス許可|PE ファイル|PE 以外のファイル|
|---|:---:|:---:|
|データを表示|X|X|
|アラートの調査|&#x2611;|X|
|ライブ応答の基本|X|X|
|ライブ応答の詳細|&#x2611;|&#x2611;|

ロールの詳細については、ロール [ベースのアクセス制御のロールの作成と管理に関する](user-roles.md)ページを参照してください。

## <a name="stop-and-quarantine-files-in-your-network"></a>ネットワーク内のファイルを停止して検疫する

悪意のあるプロセスを停止し、それが観察されたファイルを隔離することで、組織内で攻撃を含めることができます。

> [!IMPORTANT]
> この操作は、次の場合にのみ実行できます。
>
> - アクションを実行しているデバイスは、Windows 10、バージョン 1703 以降、Windows 11実行されています
> - ファイルが信頼されたサード パーティの発行元に属していないか、Microsoft によって署名されていない
> - Microsoft Defender ウイルス対策は、少なくともパッシブ モードで実行されている必要があります。 詳細については、「[Microsoft Defender ウイルス対策の互換性](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)」を参照してください。

[ **ファイルの停止と検疫]** アクションには、プロセスの実行の停止、ファイルの検疫、レジストリ キーなどの永続的なデータの削除が含まれます。

このアクションは、Windows 10 バージョン 1703 以降、およびWindows 11のデバイスで有効になります。この場合、ファイルは過去 30 日間に観察されました。

> [!NOTE]
> ファイルはいつでも検疫から復元できます。

### <a name="stop-and-quarantine-files"></a>ファイルの停止と検疫

1. 停止して検疫するファイルを選択します。 次のいずれかのビューからファイルを選択するか、[検索] ボックスを使用できます。

   - **アラート - アラート** ストーリーのタイムラインの [説明] または [詳細] から対応するリンクをクリックします
   - **検索ボックス** - ドロップダウン メニューから **[ファイル** ] を選択し、ファイル名を入力します

   > [!NOTE]
   > 停止ファイルと検疫ファイルアクションは、最大 1,000 台のデバイスに制限されます。 多数のデバイスでファイルを停止するには、「ファイルを [ブロックまたは許可するインジケーターを追加する](#add-indicator-to-block-or-allow-a-file)」を参照してください。

2. 上部のバーに移動し、[ **ファイルの停止と検疫**] を選択します。

   :::image type="content" source="images/atp-stop-quarantine-file.png" alt-text="ファイルの停止と検疫のアクション" lightbox="images/atp-stop-quarantine-file.png":::

3. 理由を指定し、[ **確認**] を選択します。

   :::image type="content" source="images/atp-stop-quarantine.png" alt-text="[停止ファイルと検疫ファイル] ページ" lightbox="images/atp-stop-quarantine.png":::

   アクション センターには、提出情報が表示されます。

   :::image type="content" source="images/atp-stopnquarantine-file.png" alt-text="ファイルの停止と検疫のアクション センター" lightbox="images/atp-stopnquarantine-file.png":::

   - **送信時間** - アクションが送信された日時を示します。
   - **成功** - ファイルが停止して検疫されたデバイスの数を示します。
   - **失敗 - アクションが失敗した** デバイスの数とエラーの詳細を示します。
   - **保留中** - ファイルがまだ停止および検疫されていないデバイスの数を示します。 これは、デバイスがオフラインであるか、ネットワークに接続されていない場合に時間がかかる場合があります。

4. 状態インジケーターのいずれかを選択して、アクションの詳細を表示します。 たとえば、[ **失敗]** を選択して、アクションが失敗した場所を確認します。

#### <a name="notification-on-device-userf"></a>デバイス の userf に関する通知

デバイスからファイルを削除すると、次の通知が表示されます。

:::image type="content" source="images/atp-notification-file.png" alt-text="デバイス ユーザーに対する通知 a" lightbox="images/atp-notification-file.png":::

デバイスタイムラインでは、ファイルが停止して検疫されたデバイスごとに新しいイベントが追加されます。

組織全体で広く使用されているファイルに対してアクションが実装される前に、警告が表示されます。 操作が意図されていることを検証するためです。

## <a name="restore-file-from-quarantine"></a>検疫からファイルを復元する

調査後にファイルがクリーンであると判断した場合は、ファイルをロールバックして検疫から削除できます。 ファイルが検疫された各デバイスで次のコマンドを実行します。

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。

   1. **[スタート]** をクリックし、「_cmd_」と入力します。

   1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

   ```dos
   "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
   ```

   > [!NOTE]
   > 一部のシナリオでは、 **ThreatName** が EUS:Win32/CustomEnterpriseBlock!cl のように表示されることがあります。
   >
   > Defender for Endpoint は、過去 30 日間にこのデバイスで検疫され、カスタム ブロックされたすべてのファイルを復元します。

> [!IMPORTANT]
> 潜在的なネットワークの脅威として検疫されたファイルは回復できない可能性があります。 検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。 これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなったことが原因である可能性があります。 通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果として生じます。

## <a name="download-or-collect-file"></a>ファイルをダウンロードまたは収集する

応答アクションから **[ファイルのダウンロード** ] を選択すると、ファイルを含むローカルのパスワードで保護された.zipアーカイブをダウンロードできます。 ポップアップが表示され、ファイルをダウンロードする理由を記録し、パスワードを設定できます。

既定では、検疫中のファイルをダウンロードできる必要があります。

:::image type="content" source="images/atp-download-file-action.png" alt-text="ファイルのダウンロード アクション" lightbox="images/atp-download-file-action.png":::

### <a name="download-quarantined-files"></a>検疫済みファイルをダウンロードする

Microsoft Defender ウイルス対策またはセキュリティ チームによって検疫されたファイルは、[サンプル送信構成](enable-cloud-protection-microsoft-defender-antivirus.md)に従って準拠した方法で保存されます。 セキュリティ チームは、[ファイルのダウンロード] ボタンを使用して、ファイルの詳細ページから直接ファイルをダウンロードできます。 **このプレビュー機能は、既定で "オン" になっています**。

場所は、組織の地域設定 (EU、英国、または米国) によって異なります。 検疫されたファイルは、組織ごとに 1 回だけ収集されます。 Service Trust Portal https://aka.ms/STPの Microsoft のデータ保護の詳細については、以下をご覧ください。

この設定をオンにすると、セキュリティ チームは、潜在的に悪いファイルを調べ、インシデントを迅速かつリスクの低い方法で調査するのに役立ちます。 ただし、この設定をオフにする必要がある場合は、**設定** \> **Endpoints** \> **Advanced 機能** \> **検疫済みファイルをダウンロード** して設定を調整します。 [高度な機能の詳細を確認する](advanced-features.md)

#### <a name="backing-up-quarantined-files"></a>検疫済みファイルのバックアップ

ユーザーは、 [サンプルの送信構成](enable-cloud-protection-microsoft-defender-antivirus.md#use-group-policy-to-turn-on-cloud-protection)に応じて、検疫されたファイルをバックアップする前に明示的な同意を求められる場合があります。

この機能は、サンプルの提出がオフになっている場合は機能しません。 自動サンプル送信がユーザーにアクセス許可を要求するように設定されている場合は、ユーザーが送信に同意したサンプルのみが収集されます。

> [!IMPORTANT]
> 検疫済みファイルの要件をダウンロードする:
>
> - 組織がアクティブ モードでMicrosoft Defender ウイルス対策を使用する
> - ウイルス対策エンジンのバージョンは 1.1.17300.4 以降です。 [毎月のプラットフォームとエンジンのバージョンを確認する](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)
> - クラウドベースの保護が有効になっている。 [クラウド配信保護を有効にする方法に関する説明を](enable-cloud-protection-microsoft-defender-antivirus.md)参照してください
> - サンプル提出が有効になっている
> - デバイスWindows 10バージョン 1703 以降、またはサーバー 2016 または 2019 Windows、またはサーバー 2022 Windows、またはWindows 11

### <a name="collect-files"></a>ファイルを収集する

ファイルがMicrosoft Defender for Endpointによってまだ保存されていない場合は、ダウンロードできません。 代わりに、同じ場所に **[ファイルの収集** ] ボタンが表示されます。 過去 30 日間に組織内にファイルが表示されていない場合、 **ファイルの収集** は無効になります。
> [!Important]
> 潜在的なネットワークの脅威として検疫されたファイルは回復できない可能性があります。 検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。 これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなったことが原因である可能性があります。 通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果として生じます。

## <a name="add-indicator-to-block-or-allow-a-file"></a>ファイルをブロックまたは許可するインジケーターを追加する

悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内での攻撃の伝播をさらに防ぎます。 悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルがわかっている場合は、ブロックできます。 この操作により、組織内のデバイスで読み取り、書き込み、または実行できなくなります。

> [!IMPORTANT]
>
> - この機能は、組織がMicrosoft Defender ウイルス対策を使用し、クラウド配信保護が有効になっている場合に使用できます。 詳細については、「 [クラウド配信保護の管理](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)」を参照してください。
>
> - マルウェア対策クライアントバージョンは、4.18.1901.x 以降である必要があります。
> - この機能は、疑わしいマルウェア (または悪意のあるファイル) が Web からダウンロードされないように設計されています。 現在、.exeファイルや _.dll_ ファイルを含むポータブル実行可能ファイル (PE) ファイル _が_ サポートされています。 カバレッジは時間の経過と共に延長されます。
> - この応答アクションは、Windows 10、バージョン 1703 以降、およびWindows 11上のデバイスで使用できます。
> - 許可またはブロックアクションの前にファイルの分類がデバイスのキャッシュに存在する場合、許可またはブロック関数はファイルに対して実行できません。

> [!NOTE]
> このアクションを実行するには、PE ファイルがデバイスタイムラインに含まれている必要があります。
>
> アクションが実行されてから実際のファイルがブロックされるまでに、数分の待機時間がかかることがあります。

### <a name="enable-the-block-file-feature"></a>ブロック ファイル機能を有効にする

ファイルのブロックを開始するには、最初にブロック [を有効にするか、設定で **機能を許可**](advanced-features.md)する必要があります。

### <a name="allow-or-block-file"></a>ファイルを許可またはブロックする

ファイルにインジケーター ハッシュを追加するときに、アラートを発生させ、組織内のデバイスがファイルを実行しようとするたびにファイルをブロックすることを選択できます。

インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートは引き続きアラート キューに表示されます。

ファイル [に対するアラートの](manage-indicators.md) ブロックと発生の詳細については、インジケーターの管理に関するページを参照してください。

ファイルのブロックを停止するには、インジケーターを削除します。 これを行うには、ファイルのプロファイル ページの **[インジケーターの編集]** アクションを使用します。 このアクションは、インジケーターを追加する前に、 **インジケーターの追加** アクションと同じ位置に表示されます。

インジケーターは、**設定** ページの [**ルール** \> **インジケーター**] で編集することもできます。 インジケーターは、ファイルのハッシュによってこの領域に一覧表示されます。

## <a name="consult-a-threat-expert"></a>脅威のエキスパートに相談する

侵害された可能性のあるデバイス、または既に侵害されたデバイスについて詳しくは、Microsoft の脅威の専門家に問い合わせてください。 Microsoft 脅威エキスパートは、タイムリーで正確な対応のために、Microsoft 365 Defender ポータル内から直接取り組みます。 専門家は、侵害される可能性のあるデバイスに関する分析情報を提供し、複雑な脅威とターゲットを絞った攻撃通知を理解するのに役立ちます。 また、ポータル ダッシュボードに表示されるアラートまたは脅威インテリジェンス コンテキストに関する情報を提供することもできます。

詳細については、 [Microsoft Threat Expert](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) に問い合わせてください。

## <a name="check-activity-details-in-action-center"></a>アクション センターでアクティビティの詳細を確認する

**アクション センター** は、デバイスまたはファイルで実行されたアクションに関する情報を提供します。 次の詳細を表示できます。

- 調査パッケージコレクション
- ウイルス対策スキャン
- アプリの制限
- デバイスの分離

送信日時、ユーザーの送信、アクションが成功または失敗した場合など、他のすべての関連する詳細も表示されます。

:::image type="content" source="images/action-center-details.png" alt-text="情報を含むアクション センター" lightbox="images/action-center-details.png":::

## <a name="deep-analysis"></a>詳細分析

サイバー セキュリティの調査は通常、アラートによってトリガーされます。 アラートは、多くの場合、新しいファイルまたは不明な 1 つ以上の監視ファイルに関連しています。 ファイルを選択すると、ファイル ビューに移動し、ファイルのメタデータを確認できます。 ファイルに関連するデータをエンリッチするには、詳細な分析のためにファイルを送信します。

ディープ分析機能は、セキュリティで保護された完全にインストルメント化されたクラウド環境でファイルを実行します。 詳細な分析結果は、ファイルのアクティビティ、観察された動作、および関連する成果物 (ドロップされたファイル、レジストリの変更、IP との通信など) を示します。
現在、詳細分析では、ポータブル実行可能ファイル (PE) ファイル (.exeファイルや _.dll_ ファイルを含む) の広範な分析 _が_ サポートされています。

ファイルの詳細な分析には数分かかります。 ファイル分析が完了すると、[ディープ分析] タブが更新され、概要と使用可能な最新の結果の日付と時刻が表示されます。

詳細な分析の概要には、観察された *動作* の一覧が含まれています。一部は悪意のあるアクティビティを示し、ディスク上に作成された連絡先の IP やファイルを含む *監視可能な* アクティビティを示すことができます。 何も見つからなかった場合、これらのセクションには簡単なメッセージが表示されます。

詳細な分析の結果は脅威インテリジェンスと照合され、一致すると適切なアラートが生成されます。

詳細な分析機能を使用して、通常はアラートの調査中、または悪意のある動作が疑われるその他の理由で、ファイルの詳細を調査します。 この機能は、ファイルのプロファイル ページの [ **ディープ分析** ] タブで使用できます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4aAYy?rel=0]

ファイルが Defender for Endpoint バックエンド サンプル コレクションで使用可能な場合、または詳細分析への送信をサポートするWindows 10 デバイスで観察された場合は、詳細 **な分析** のために送信が有効になります。

> [!NOTE]
> Windows 10とWindows 11からのファイルのみを自動的に収集できます。

Windows 10 デバイス (またはWindows 11) でファイルが観察されなかった場合は、Microsoft 365 Defender [ポータル](https://www.microsoft.com/security/portal/submission/submit.aspx)からサンプルを送信し、**詳細な分析** ボタンが使用可能になるまで送信を待機することもできます。

> [!NOTE]
> Microsoft 365 Defender ポータルのバックエンド処理フローにより、ファイルの送信と Defender for Endpoint の詳細分析機能の可用性の間に最大 10 分間の待機時間が発生する可能性があります。

### <a name="submit-files-for-deep-analysis"></a>詳細な分析のためにファイルを送信する

1. 詳細な分析のために送信するファイルを選択します。 次のいずれかのビューからファイルを選択または検索できます。

    - **[アラート] - [** アラート ストーリー] タイムラインの **[説明** ] または **[詳細** ] からファイル リンクを選択します
    - **デバイスの一覧** - **[組織のデバイス**] セクションの **[説明**] または **[詳細**] セクションからファイル リンクを選択します。
    - **検索ボックス** - ドロップダウン メニューから **[ファイル** ] を選択し、ファイル名を入力します

2. ファイル ビューの [ **詳細分析** ] タブで、[送信] を選択 **します**。

   :::image type="content" source="images/submit-file.png" alt-text="[PE ファイルの送信] ボタン" lightbox="images/submit-file.png":::

   > [!NOTE]
   > _.exe_ ファイルと _.dll_ ファイルを含む PE ファイルのみがサポートされます。

   進行状況バーが表示され、分析のさまざまな段階に関する情報が表示されます。 その後、分析が完了したときにレポートを表示できます。

> [!NOTE]
> デバイスの可用性に応じて、サンプル収集時間は異なる場合があります。 サンプル コレクションには 3 時間のタイムアウトがあります。 コレクションは失敗し、その時点でオンライン Windows 10 デバイス (またはWindows 11) レポートがない場合、操作は中止されます。 詳細な分析のためにファイルを再送信して、ファイルの新しいデータを取得できます。

### <a name="view-deep-analysis-reports"></a>詳細な分析レポートを表示する

提供された詳細な分析レポートを表示して、送信したファイルに関する詳細な分析情報を確認します。 この機能は、ファイル ビュー コンテキストで使用できます。

次のセクションの詳細を示す包括的なレポートを表示できます。

- Behaviors
- Observables

提供された詳細は、潜在的な攻撃の兆候があるかどうかを調査するのに役立ちます。

1. 詳細な分析のために送信したファイルを選択します。
2. [ **詳細分析** ] タブを選択します。以前のレポートがある場合は、このタブにレポートの概要が表示されます。

   :::image type="content" source="images/analysis-results-nothing500.png" alt-text="さまざまなカテゴリにわたる詳細情報を示す詳細な分析レポート" lightbox="images/analysis-results-nothing500.png":::

#### <a name="troubleshoot-deep-analysis"></a>詳細な分析のトラブルシューティング

ファイルの送信時に問題が発生した場合は、次のトラブルシューティングの各手順を試してください。

1. 該当するファイルが PE ファイルであることを確認します。 PE ファイルには通常、 _.exe_ または _.dll_ 拡張機能 (実行可能プログラムまたはアプリケーション) があります。

2. サービスがファイルへのアクセス権を持ち、ファイルがまだ存在し、破損または変更されていないことを確認します。

3. しばらく待ってから、もう一度ファイルを送信してください。 キューがいっぱいになっているか、一時的な接続または通信エラーが発生しました。

4. サンプル コレクション ポリシーが構成されていない場合、既定の動作はサンプル コレクションを許可することです。 構成されている場合は、ファイルを再度送信する前に、ポリシー設定でサンプル コレクションが許可されていることを確認します。 サンプル コレクションが構成されている場合は、次のレジストリ値を確認します。

    ```text
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 - block sample collection
      Value = 1 - allow sample collection
    ```

5. グループ ポリシーを使用して組織単位を変更します。 詳細については、「[グループ ポリシーを使用した構成」を](configure-endpoints-gp.md)参照してください。

6. これらの手順で問題が解決しない場合は、サポートにお問い合わせください。

## <a name="related-topics"></a>関連項目

- [デバイスの対応措置を講じる](respond-machine-alerts.md)
- [ファイルの調査](investigate-files.md)
- [Microsoft Defender for Endpoint プラン 1 の手動応答アクション](defender-endpoint-plan-1.md#manual-response-actions)
