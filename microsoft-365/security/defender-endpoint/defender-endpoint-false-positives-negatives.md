---
title: Microsoft Defender for Endpoint での誤検出/検出漏れに対処する
description: Microsoft Defender for Endpoint で偽陽性または偽陰性を処理する方法について説明します。
keywords: ウイルス対策, 例外, 除外, Microsoft Defender for Endpoint, 偽陽性, 偽陰性, ブロックされたファイル, ブロックされた URL
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.date: 12/02/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom:
- FPFN
- admindeeplinkDEFENDER
ms.openlocfilehash: 81c41abffc6ec01c127b901ac63b3a5d3b6c5732
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418458"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint での誤検出/検出漏れに対処する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

エンドポイント保護ソリューションでは、偽陽性とは、ファイルやプロセスなど、エンティティが実際には脅威ではないにもかかわらず、悪意のあるものとして検出および識別されたエンティティです。 偽陰性とは、実際には悪意のあるものであるにもかかわらず、脅威として検出されなかったエンティティです。 偽陽性/偽陰性は、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を含むあらゆる脅威に対する保護ソリューションで発生する可能性があります。

:::image type="content" source="images/false-positives-overview.png" alt-text="Microsoft Defender for Endpoint ポータルの偽陽性と偽陰性の定義" lightbox="images/false-positives-overview.png":::

幸いなことに、これらの種類の問題に対処し、削減するための手順を実行できます。 [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) で偽陽性/偽陰性が発生した場合、セキュリティ操作では、次のプロセスを使用してそれらに対処する手順を実行できます。

1. [アラートを確認して分類する](#part-1-review-and-classify-alerts)
2. [実行された修復処理を確認する](#part-2-review-remediation-actions)
3. [除外を確認および定義する](#part-3-review-or-define-exclusions)
4. [分析用にエンティティを提出する](#part-4-submit-a-file-for-analysis)
5. [脅威に対する保護の設定を確認して調整する](#part-5-review-and-adjust-your-threat-protection-settings)

この記事で説明するタスクを実行した後も、偽陽性/偽陰性に関する問題が解決しない場合は、サポートを受けることができます。 「[さらにヘルプが必要ですか?](#still-need-help)」を参照してください。

:::image type="content" source="images/false-positives-step-diagram.png" alt-text="偽陽性と偽陰性に対処するための手順" lightbox="images/false-positives-step-diagram.png":::

> [!NOTE]
> この記事は、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を使用しているセキュリティ対策担当者とセキュリティ管理者向けのガイダンスを目的としています。

## <a name="part-1-review-and-classify-alerts"></a>パート 1: アラートを確認して分類する

何かが悪意のある、または疑わしいものとして検出されたためにトリガーされた[アラート](alerts.md)が表示された場合は、そのエンティティのアラートを抑制できます。 また、必ずしも偽陽性ではないが重要ではないアラートを抑制することもできます。 アラートを分類することもお勧めします。

アラートを管理し、真陽性/偽陽性を分類すると、脅威に対する保護ソリューションをトレーニングするのに役立ち、時間の経過と共に偽陽性または偽陰性の数を減らすことができます。 これらの手順を実行すると、セキュリティ運用ダッシュボードのノイズを減らして、セキュリティ チームが優先度の高い作業項目に集中できるようになります。

### <a name="determine-whether-an-alert-is-accurate"></a>アラートが正確かどうかを判断する

アラートを分類または抑制する前に、アラートが正確か、偽陽性か、無害であるかを判断します。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[アラート キュー]** を選択します。

3. アラートを選択すると、アラートの詳細が表示されます。 (「[Microsoft Defender for Endpoint でアラートを確認する](review-alerts.md)」を参照してください)。

4. アラートの状態に応じて、次の表に示す手順を実行します。

   |アラートの状態|操作|
   |---|---|
   |アラートは正確です|アラートを割り当て、さらに[調査](investigate-alerts.md)します。|
   |アラートは偽陽性です|1. 偽陽性として[アラートを分類](#classify-an-alert)します。<br/><br/>2. [アラートを抑制](#suppress-an-alert)します。<br/><br/>3. Microsoft Defender for Endpoint の[インジケーターを作成](#indicators-for-microsoft-defender-for-endpoint)します。<br/><br/>4. [分析用に Microsoft にファイルを提出](#part-4-submit-a-file-for-analysis)します。|
   |アラートは正確ですが、問題ありません (重要ではありません)|真陽性として[アラートを分類](#classify-an-alert)し、次に[アラートを抑制](#suppress-an-alert)します。|

### <a name="classify-an-alert"></a>アラートを分類する

Microsoft 365 Defender では、アラートを偽陽性または真陽性として分類できます。 アラートを分類すると、Microsoft Defender for Endpoint のトレーニングに役立ちます。これにより、時間の経過と共に、より多くの真のアラートとより少ない偽のアラートが表示されるようになります。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **[アラート キュー]** を選択し、次にアラートを選択します。

3. 選択したアラートに対して、**[処理]** \> **[アラートを管理]** を選択します。 ポップアップ ウィンドウが開きます。

4. **[アラートの管理]** セクションで、**[アラート (真)]** または **[アラート (偽)]** を選択します。 (**アラート (偽)** を使用して偽陽性を分類します。)

> [!TIP]
> アラートの抑制の詳細については、「[Microsoft Defender for Endpoint でアラートを管理する](/microsoft-365/security/defender-endpoint/manage-alerts)」を参照してください。 また、組織でセキュリティ情報イベント管理 (SIEM) サーバーを使用している場合は、抑制ルールも必ず定義してください。

### <a name="suppress-an-alert"></a>アラートを抑制する

偽陽性、または真陽性であるが重要ではないイベントのアラートがある場合は、Microsoft 365 Defender でそれらのアラートを抑制できます。 アラートを抑制すると、セキュリティ運用ダッシュボードのノイズを軽減できます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[アラート キュー]** を選択します。

3. 非表示にするアラートを選択して、**[詳細]** ウィンドウを開きます。

4. **[詳細]** ウィンドウで省略記号 (**...**) を選択し、**[抑制ルールを作成]** を選択します。

5. 抑制ルールのすべての設定を指定し、**[保存]** を選択 します。

> [!TIP]
> 抑制ルールに関するヘルプが必要な場合は、 「[アラートを抑制し、新しい抑制ルールを作成する](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)」を参照してください。

## <a name="part-2-review-remediation-actions"></a>パート 2: 修復処理を確認する

検疫へのファイルの送信やプロセスの停止などの[修復処理](manage-auto-investigation.md#remediation-actions)は、脅威として検出されたエンティティ (ファイルなど) に対して実行されます。 自動調査と Microsoft Defender ウイルス対策によって、次に示すいくつかの種類の修復処理が自動的に実行されます。

- ファイルの検疫
- レジストリ キーの削除
- プロセスの強制終了
- サービスの停止
- ドライバーの無効化
- スケジュールされたタスクの実行

ウイルス対策スキャンの開始や調査パッケージの収集などのその他の処理は、手動で、または[ライブ応答](live-response.md)を介して実行されます。 ライブ応答を使用して実行された処理を元に戻すことはできません。

アラートを確認した後、次の手順は[修復処理](manage-auto-investigation.md)を確認することです。 偽陽性の結果として何か処理が実行された場合は、ほとんどの種類の修復処理を元に戻すことができます。 具体的には次のことができます。

- [アクション センターから検疫済みファイルを復元する](#restore-a-quarantined-file-from-the-action-center)
- [複数の処理を一度に元に戻す](#undo-multiple-actions-at-one-time)
- [複数のデバイスで検疫からファイルを削除する](#remove-a-file-from-quarantine-across-multiple-devices)。 and
- [検疫からファイルを復元する](#restore-file-from-quarantine)

偽陽性の結果として実行された処理の確認と取り消しが完了したら、「[除外を確認または定義する](#part-3-review-or-define-exclusions)」に進みます。

### <a name="review-completed-actions"></a>完了した処理を確認する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の左側のナビゲーション ウィンドウで、**[アクション センター]** をクリックします。

2. **[履歴]** タブを選択して、実行された処理の一覧を表示します。

3. アイテムを選択すると、実行された修復処理の詳細が表示されます。

### <a name="restore-a-quarantined-file-from-the-action-center"></a>アクション センターから検疫済みファイルを復元する

1. Microsoft 365 Defender ポータルの左側のナビゲーション ウィンドウで **[アクション センター]** をクリックします。

2. **[履歴]** タブで、元に戻す処理を選択します。

3. ポップアップ ウィンドウで **[元に戻す]** を選択します。 この方法で処理を元に戻すことができない場合は、**[元に戻す]** ボタンは表示されません。 (詳細については、「[完了した処理を元に戻す](manage-auto-investigation.md#undo-completed-actions)」を参照してください。)

### <a name="undo-multiple-actions-at-one-time"></a>複数の処理を一度に元に戻す

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の左側のナビゲーション ウィンドウで、**[アクション センター]** をクリックします。

2. **[履歴]** タブで、元に戻す処理を選択します。

3. 画面の右側のウィンドウで、**[元に戻す]** を選択します。

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイスで検疫からファイルを削除する

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/autoir-quarantine-file-1.png" alt-text="検疫ファイル" lightbox="images/autoir-quarantine-file-1.png":::

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の左側のナビゲーション ウィンドウで、**[アクション センター]** をクリックします。

2. **[履歴]** タブで、処理の種類が **[検疫ファイル]** のファイルを選択します。

3. 画面の右側のウィンドウで、**[このファイルのその他 X 個のインスタンスに適用する]** を選択し、**[元に戻す]** を選択します。

### <a name="restore-file-from-quarantine"></a>検疫からファイルを復元する

調査後にファイルがクリーンであると判断した場合は、ファイルをロールバックして検疫から削除できます。 ファイルが検疫された各デバイスで次のコマンドを実行します。

1. デバイスで管理者特権のコマンド ライン プロンプトを開きます。

   1. **[スタート]** をクリックし、「_cmd_」と入力します。
   2. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter キー** を押します。

    ```console
    "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
    ```

    > [!IMPORTANT]
    > シナリオによっては、**ThreatName** が `EUS:Win32/CustomEnterpriseBlock!cl` として表示される場合があります。 Defender for Endpoint は、過去 30 日間にこのデバイスで検疫され、カスタム ブロックされたすべてのファイルを復元します。
    >
    > 潜在的なネットワークの脅威として検疫されたファイルは回復できない可能性があります。 検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。 これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなったことが原因である可能性があります。 通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果として生じます。

3. 画面の右側のウィンドウで、**[このファイルのその他 X 個のインスタンスに適用する]** を選択し、**[元に戻す]** を選択します。

## <a name="part-3-review-or-define-exclusions"></a>パート 3: 除外を確認または定義する

除外とは、修復処理の例外として指定するエンティティ (ファイルや URL など) です。 除外されたエンティティは引き続き検出されますが、そのエンティティに対して修復処理は実行されません。 つまり、検出されたファイルまたはプロセスが、Microsoft Defender for Endpoint によって停止、検疫に送信、削除、変更されることはありません。

Microsoft Defender for Endpoint 全体で除外を定義するには、次のタスクを実行します。

- [Microsoft Defender ウイルス対策の除外を定義する](#exclusions-for-microsoft-defender-antivirus)
- [Microsoft Defender for Endpoint の "許可" インジケーターを作成する](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Microsoft Defender ウイルス対策の除外はウイルス対策保護にのみ適用され、他の Microsoft Defender for Endpoint 機能には適用されません。 ファイルを広範囲に除外するには、Microsoft Defender ウイルス対策の除外と Microsoft Defender for Endpoint の[カスタム インジケーター](/microsoft-365/security/defender-endpoint/manage-indicators)を使用します。

このセクションの手順では、除外とインジケーターを定義する方法について説明します。

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の除外

一般に、Microsoft Defender ウイルス対策の除外を定義する必要はありません。 除外を慎重に定義し、偽陽性が発生するファイル、フォルダー、プロセス、およびプロセスで開かれたファイルのみを含めます。 また、定義済みの除外を定期的に確認してください。 [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)を使用して、ウイルス対策の除外を定義または編集することをお勧めします。ただし、[グループ ポリシー](/azure/active-directory-domain-services/manage-group-policy)など、他の方法を使用することもできます (「[Microsoft Defender for Endpoint を管理する](manage-mde-post-migration.md)」を参照してください)。

> [!TIP]
> ウイルス対策の除外に関するヘルプが必要な場合は、 「[Microsoft Defender ウイルス対策のスキャンの除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)」を参照してください。

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>Microsoft エンドポイント マネージャーを使用してウイルス対策の除外を管理する (既存のポリシーの場合)

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[エンドポイント セキュリティ]** \> **[ウイルス対策]** を選択し、既存のポリシーを選択します。 (既存のポリシーがない場合、または新しいポリシーを作成する場合は、[次の手順](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)に進みます)。

3. **[プロパティ ]** を選択し、**[構成設定]** の横にある **[編集]** を選択します。

4. **[Microsoft Defender ウイルス対策の除外]** を展開し、除外を指定します。

5. **[確認と保存]** を選択し、**[保存]** を選択します。

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>Microsoft エンドポイント マネージャーを使用して、除外を含む新しいウイルス対策ポリシーを作成する

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[エンドポイント セキュリティ]** \> **[ウイルス対策]** \> **[+ ポリシーの作成]** を選択します。

3. プラットフォーム (**Windows 10 以降**、**macOS**、**Windows 10 および Windows Server** など) を選択します。

4. **[プロファイル]** で **[Microsoft Defender ウイルス対策の除外]** を選択し、**[作成]** を選択します。

5. プロファイルの名前と説明を指定し、**[次へ]** を選択します。

6. **[構成設定]** タブで、ウイルス対策の除外を指定し、**[次へ]** を選択します。

7. **[スコープ タグ]** タブでは、組織でスコープ タグを使用している場合は、作成するポリシーのスコープ タグを指定します。 (「[スコープ タグ](/mem/intune/fundamentals/scope-tags)」を参照してください。)

8. **[割り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、**[次へ]** を選択します。 (割り当てに関するヘルプが必要な場合は、「[Microsoft Intune でユーザーおよびデバイスのプロファイルを割り当てる](/mem/intune/configuration/device-profile-assign)」を参照してください。)

9. **[確認と作成]** タブで、設定を確認し、**[作成]** を選択します。

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のインジケーター

[インジケーター](/microsoft-365/security/defender-endpoint/manage-indicators) (特に、侵害インジケーター、いわゆる IoC) を使用することで、セキュリティ運用チームはエンティティの検出、防止、除外を定義できます。 たとえば、Microsoft Defender for Endpoint のスキャンと修復処理から除外するように特定のファイルを指定できます。 または、インジケーターを使用して、特定のファイル、IP アドレス、または URL に対するアラートを生成できます。

Microsoft Defender for Endpoint の除外としてエンティティを指定するには、それらのエンティティ用の "許可" インジケーターを作成します。 Microsoft Defender for Endpoint のこのような "許可" インジケーターは、[次世代の保護](microsoft-defender-antivirus-in-windows-10.md)、[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)、[調査と修復の自動化](/microsoft-365/security/defender-endpoint/automated-investigations)に適用されます。

"許可" インジケーターは、以下を対象として作成できます。

- [Files](#indicators-for-files)
- [IP アドレス、URL、ドメイン](#indicators-for-ip-addresses-urls-or-domains)
- [アプリケーション証明書](#indicators-for-application-certificates)

:::image type="content" source="images/false-positives-indicators.png" alt-text="インジケーターの種類" lightbox="images/false-positives-indicators.png":::

#### <a name="indicators-for-files"></a>ファイルのインジケーター

[ファイル (実行可能ファイルなど) の "許可" インジケーターを作成](/microsoft-365/security/defender-endpoint/indicator-file)すると、組織で使用しているファイルがブロックされるのを防ぐのに役立ちます。 ファイルには、ポータブル実行可能ファイル (PE) (`.exe`、`.dll` ファイルなど) を含めることもできます。

ファイルのインジケーターを作成する前に、次の要件を満たしていることを確認してください。

- Microsoft Defender ウイルス対策保護は、クラウドベースの保護が有効になるように構成されている (「[クラウドベースの保護の管理](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)」を参照してください)
- マルウェア対策クライアントのバージョンは 4.18.1901.x 以降である
- デバイスは、Windows 10 バージョン 1703 以降または Windows 11、Windows Server 2016、Windows Server 2019、または Windows Server 2022 を実行している
- ["ブロックまたは許可" 機能がオンになっている](/microsoft-365/security/defender-endpoint/advanced-features)

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>IP アドレス、URL、またはドメインのインジケーター

[IP アドレス、URL、またはドメイン の "許可" インジケーターを作成](/microsoft-365/security/defender-endpoint/indicator-ip-domain)すると、組織で使用するサイトまたは IP アドレスがブロックされるのを防ぐのに役立ちます。

IP アドレス、URL、またはドメインのインジケーターを作成する前に、次の要件を満たしていることを確認してください。

- Defender for Endpoint のネットワーク保護がブロック モードで有効になっている (「[ネットワーク保護を有効 にする](/microsoft-365/security/defender-endpoint/enable-network-protection)」を参照してください)
- マルウェア対策クライアントのバージョンは 4.18.1906.x 以降である
- デバイスは Windows 10 バージョン 1709 以降または Windows 11 を実行している

カスタム ネットワーク インジケーターは、[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) でオンになっています。 詳細については、「[高度な機能](/microsoft-365/security/defender-endpoint/advanced-features)」を参照してください。

#### <a name="indicators-for-application-certificates"></a>アプリケーション証明書のインジケーター

[アプリケーション証明書 の "許可" インジケーターを作成](/microsoft-365/security/defender-endpoint/indicator-certificates)すると、組織で使用するアプリケーション (内部で開発されたアプリケーションなど) がブロックされるのを防ぐのに役立ちます。 `.CER` または `.PEM` ファイル拡張子がサポートされています。

アプリケーション証明書のインジケーターを作成する前に、次の要件を満たしていることを確認してください。

- Microsoft Defender ウイルス対策保護は、クラウドベースの保護が有効になるように構成されている (「[クラウドベースの保護の管理](deploy-manage-report-microsoft-defender-antivirus.md)」を参照してください)
- マルウェア対策クライアントのバージョンは 4.18.1901.x 以降である
- デバイスは、Windows 10 バージョン 1703 以降または Windows 11、Windows Server 2016、Windows Server 2019、または Windows Server 2022 を実行している
- ウイルスと脅威に対する保護の定義は最新である

> [!TIP]
> インジケーターを作成する場合は、それらを 1 つずつ定義するか、複数のアイテムを一度にインポートすることができます。 1 つのテナントには 15,000 個のインジケーターの制限があることに注意してください。 また、ファイル ハッシュ情報など、特定の詳細を最初に収集する必要がある場合があります。 [インジケーターを作成](manage-indicators.md)する前に、前提条件を確認してください。

## <a name="part-4-submit-a-file-for-analysis"></a>パート 4: 分析用にファイルを提出する

ファイルやファイルレス検出などのエンティティを、分析用に Microsoft に提出できます。 提出されたものはすべて、Microsoft のセキュリティ研究者によって分析されます。また、その結果は Microsoft Defender for Endpoint の脅威に対する保護の能力を知らせるのに役立ちます。 提出サイトでサインインすると、提出を追跡できます。

### <a name="submit-a-file-for-analysis"></a>分析用にファイルを提出する

悪意のあるファイルとして誤って検出された、または見つからないファイルがある場合は、次の手順に従って分析用のファイルを提出します。

1. 「[分析用にファイルを提出する](/windows/security/threat-protection/intelligence/submission-guide)」のガイドラインを確認してください。

2. [Microsoft セキュリティ インテリジェンスの提出サイト](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission) にアクセスし、ファイルを提出します。

### <a name="submit-a-fileless-detection-for-analysis"></a>分析用にファイルレス検出を提出する

何かが動作に基づいてマルウェアとして検出され、ファイルがない場合は、分析用に `Mpsupport.cab` ファイルを提出することができます。 Windows 10 または Windows 11 の Microsoft マルウェア対策コマンドライン ユーティリティ (MPCmdRun.exe) ツールを使用して、*.cab* ファイルを取得できます。

1. ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` に移動し、管理者として `MpCmdRun.exe` を実行します。

2. 「`mpcmdrun.exe -GetFiles`」と入力して、**Enter** キーを押します。

   さまざまな診断ログを含む .cab ファイルが生成されます。 ファイルの場所は、コマンド プロンプトの出力で指定されます。 既定では、場所は `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` です。

3. 「[分析用にファイルを提出する](/windows/security/threat-protection/intelligence/submission-guide)」のガイドラインを確認してください。

4. [Microsoft セキュリティ インテリジェンスの提出サイト](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission) にアクセスし、.cab ファイルを提出します。

### <a name="what-happens-after-a-file-is-submitted"></a>ファイルの提出後に何が行われますか?

アナリストがケースの処理を開始する前に、お客様の提出が直ちにシステムによってスキャンされ、最新の判断が下されます。 ファイルが既に提出されていて、アナリストによって処理されている可能性があります。 そのような場合、決定は迅速に行います。

まだ処理されていない提出については、次のように分析の優先順位が設定されます。

- 多数のコンピューターに影響を与える可能性のある一般的なファイルは優先度が高くなります。
- 認証されたお客様、特に有効な[ソフトウェア アシュアランス ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) をお持ちのエンタープライズのお客様は、優先度が高くなります。
- SAID 所有者によって優先度が高いフラグが付けられた提出には、直ちに注意が払われます。

提出に関する更新情報を確認するには、[Microsoft セキュリティ インテリジェンス提出サイト](https://www.microsoft.com/wdsi/filesubmission)でサインインしてください。

> [!TIP]
> 詳細については、「[分析用にファイルを提出する](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)」を参照してください。

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>パート 5: 脅威に対する保護の設定を確認して調整する

Microsoft Defender for Endpoint には、さまざまな機能の設定を微調整する機能など、さまざまなオプションが用意されています。 多数の偽陽性が発生している場合は、必ず組織の脅威に対する保護設定を確認してください。 次の調整が必要になる場合があります。

- [クラウドによる保護](#cloud-delivered-protection)
- [望ましくない可能性のあるアプリケーションに対する修復](#remediation-for-potentially-unwanted-applications)
- [調査と修復の自動化](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>クラウドによる保護

Microsoft Defender ウイルス対策のクラウドによる保護のレベルを確認します。 既定では、クラウドによる保護は **[未構成]** に設定されています。これは、ほとんどの組織の通常レベルの保護に対応します。 クラウドによる保護が **[高]**、**[高 +]**、または **[ゼロ トレランス]** に設定されている場合は、偽陽性の数が多くなる可能性があります。

> [!TIP]
> クラウドによる保護の構成に関する詳細については、「[クラウドによる保護のレベルを指定する](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)」を参照してください。

[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)を使用して、クラウドによる保護設定を編集または設定することをお勧めします。ただし、[グループ ポリシー](/azure/active-directory-domain-services/manage-group-policy)など、他の方法を使用することもできます (「[Microsoft Defender for Endpoint を管理する](manage-mde-post-migration.md)」を参照してください)。

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>Microsoft エンドポイント マネージャーを使用して、クラウドによる保護設定を確認および編集する (既存のポリシーの場合)

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[エンドポイント セキュリティ]** \> **[ウイルス対策]** を選択し、既存のポリシーを選択します。 (既存のポリシーがない場合、または新しいポリシーを作成する場合は、[次の手順](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)に進みます)。

3. **[管理]** で **[プロパティ]** を選択します。 **[構成設定]** の横にある **[編集]** を選択します。

4. **[クラウド保護]** を展開し、**[クラウドによる保護のレベル]** 行で現在の設定を確認します。 クラウドによる保護を **[未構成]** に設定することをお勧めします。これにより、偽陽性が発生する可能性を減らしながら、強力な保護が提供されます。

5. **[確認と保存]**、**[保存]** の順に選択します。

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>Microsoft エンドポイント マネージャーを使用して、クラウドによる保護設定を設定する (新しいポリシーの場合)

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[エンドポイント セキュリティ]** \> **[ウイルス対策]** \> **[+ ポリシーの作成]** を選択します。

3. **[プラットフォーム]** でオプションを選択し、**[プロファイル]** で **[ウイルス対策]** または **[Microsoft Defender ウイルス対策]** を選択します (特定のオプションは、**[プラットフォーム]** で選択した内容によって異なります)。次に、**[作成]** を選択します。

4. **[基本]** タブで、このポリシーの名前と説明を指定します。 **[次へ]** を選択します。

5. **[構成設定]** タブで **[クラウド保護]** を展開し、次の設定を指定します。

   - **[クラウドによる保護を有効にする]** を **[はい]** に設定します。
   - **[クラウド配信の保護レベル]** を **[未構成]** に設定します。 (このレベルでは、偽陽性が発生する可能性を減らしながら、強力なレベルの保護が提供されます。)

6. **[スコープ タグ]** タブでは、組織でスコープ タグを使用している場合は、ポリシーのスコープ タグを指定します。 (「[スコープ タグ](/mem/intune/fundamentals/scope-tags)」を参照してください。)

7. **[割り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、**[次へ]** を選択します。 (割り当てに関するヘルプが必要な場合は、「[Microsoft Intune でユーザーおよびデバイスのプロファイルを割り当てる](/mem/intune/configuration/device-profile-assign)」を参照してください。)

8. **[確認と作成]** タブで、設定を確認し、**[作成]** を選択します。

### <a name="remediation-for-potentially-unwanted-applications"></a>望ましくない可能性のあるアプリケーションに対する修復

望ましくない可能性のあるアプリケーション (PUA) は、デバイスの実行速度の低下、予期しない広告の表示、予期しないまたは望ましくない可能性のある他のソフトウェアのインストールを引き起こす可能性のあるソフトウェアのカテゴリです。 PUA の例としては、広告ソフトウェア、バンドル ソフトウェア、セキュリティ製品とは動作が異なる回避ソフトウェアがあります。 PUA はマルウェアとは見なされませんが、一部の種類のソフトウェアは、その動作と評判に基づいて PUA であるとされます。

> [!TIP]
> PUA の詳細については、「[望ましくない可能性のあるアプリケーションを検出してブロックする](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)」を参照してください。

組織が使用しているアプリによっては、PUA の保護設定の結果として偽陽性が発生する場合があります。 必要に応じて、しばらくの間、監査モードで PUA の保護を実行するか、組織内のデバイスのサブセットに PUA の保護を適用することを検討してください。 PUA の保護は、Microsoft Edge ブラウザーとMicrosoft Defender ウイルス対策用に構成できます。

[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)を使用して、PUA の保護設定を編集または設定することをお勧めします。ただし、[グループ ポリシー](/azure/active-directory-domain-services/manage-group-policy)など、他の方法を使用することもできます (「[Microsoft Defender for Endpoint を管理する](manage-mde-post-migration.md)」を参照してください)。

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>Microsoft エンドポイント マネージャーを使用して PUA の保護を編集する (既存の構成プロファイルの場合)

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[デバイス]** \> **[構成プロファイル]** を選択し、既存のポリシーを選択します。 (既存のポリシーがない場合、または新しいポリシーを作成する場合は、[次の手順](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)に進みます。)

3. **[管理]** で、**[プロパティ]** を選択し、**[構成設定]** の横にある **[編集]** を選択します。

4. **[構成設定]** タブで、下にスクロールして **[Microsoft Defender ウイルス対策]** を展開します。

5. **[望ましくない可能性のあるアプリケーションの検出]** を **[監査]** に設定します。 (オフにできますが、監査モードを使用すると、検出を確認できます。)

6. **[確認と保存]** を選択し、**[保存]** を選択します。

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>Microsoft エンドポイント マネージャーを使用して PUA の保護を設定する (新しい構成プロファイルの場合)

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[デバイス]** \> **[構成プロファイル]** \> **[+ プロファイルの作成]** を選択します。

3. **[プラットフォーム]** で、**[Windows 10 以降]** を選択し、**[プロファイル]** で **[デバイスの制限]** を選択します。

4. **[基本]** タブで、ポリシーの名前と説明を指定します。 **[次へ]** を選択します。

5. **[構成設定]** タブで、下にスクロールして **[Microsoft Defender ウイルス対策]** を展開します。

6. **[望ましくない可能性のあるアプリケーションの検出]** を **[監査]** に設定し、**[次へ]** を選択します。 (PUA の保護をオフにできますが、監査モードを使用すると、検出を確認できます)。

7. **[割り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、**[次へ]** を選択します。 (割り当てに関するヘルプが必要な場合は、「[Microsoft Intune でユーザーおよびデバイスのプロファイルを割り当てる](/mem/intune/configuration/device-profile-assign)」を参照してください。)

8. **[適用性ルール]** タブで、ポリシーに含めるかポリシーから除外する OS エディションまたはバージョンを指定します。 たとえば、特定のエディションの Windows 10 のすべてのデバイスに適用されるようにポリシーを設定できます。 **[次へ]** を選択します。

9. **[確認と作成]** タブで、設定を確認し、**[作成]** を選択します。

### <a name="automated-investigation-and-remediation"></a>調査と修復の自動化

[調査と修復の自動化](automated-investigations.md) (AIR) 機能は、アラートを調査し、侵害を解決するための処理を直ちに実行するように設計されています。 アラートがトリガーされ、自動調査が実行されると、調査された証拠ごとに判定が生成されます。 判定は、*悪意のある*、*疑わしい*、または *脅威なし* のいずれかです。

組織に設定されている [自動化のレベル](/microsoft-365/security/defender-endpoint/automation-levels)やその他のセキュリティ設定に応じて、*悪意のある*、または *疑わしい* と見なされるアーティファクトに対して修復処理が実行されます。 場合によっては、自動的に修復処理が実行されます。それ以外の場合は、修復処理は手動で、またはセキュリティ運用チームによって承認された場合にのみ実行されます。

- [自動化レベルの詳細をご確認ください](/microsoft-365/security/defender-endpoint/automation-levels)。次に、
- [Defender for Endpoint で AIR 機能を構成します](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)。

> [!IMPORTANT]
> 調査と修復の自動化には、*完全自動化* を使用することをお勧めします。 偽陽性が原因でこれらの機能をオフにしないでください。 代わりに、["許可" インジケーターを使用して例外を定義](#indicators-for-microsoft-defender-for-endpoint)して、自動的に適切な処理が実行されるように調査と修復の自動化を設定します。 [このガイダンス](automation-levels.md#levels-of-automation)に従うと、セキュリティ運用チームが処理する必要があるアラートの数を減らすことができます。

## <a name="still-need-help"></a>さらにヘルプが必要ですか?

この記事のすべての手順を実行しても引き続きサポートが必要な場合は、テクニカル サポートにお問い合わせください。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> に移動してサインインします。

2. 右上隅にある疑問符 (**?**) を選択し、**[Microsoft サポート]** を選択します。

3. **[サポート アシスタント]** ウィンドウで、問題について説明し、メッセージを送信します。 これで、お問い合わせを開くことができます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md) 

## <a name="see-also"></a>関連項目

[Microsoft Defender for Endpoint を管理する](manage-mde-post-migration.md)

[Microsoft 365 Defender ポータルの概要](/microsoft-365/security/defender-endpoint/use)
