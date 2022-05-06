---
title: パイロット環境でインシデント対応機能をMicrosoft 365 Defenderしてみてください
description: Microsoft 365 Defenderのインシデント対応機能を試して、インシデントの優先順位付けと管理、調査の自動化、脅威検出での高度な捜索の使用を行います。
keywords: 試用版のMicrosoft 365 Defender、Microsoft 365 Defenderの試用、Microsoft 365 Defenderの評価、評価ラボのMicrosoft 365 Defender、Microsoft 365 Defender パイロット、サイバー セキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0ad2fc9a1566e7816b3ff806b7d07ac29347cc89
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754771"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>パイロット環境でインシデント対応機能をMicrosoft 365 Defenderしてみてください

**適用対象:**
- Microsoft 365 Defender

この記事は、パイロット環境を使用してMicrosoft 365 Defenderでインシデントの調査と対応を実行するプロセスの[手順 2/2](eval-defender-investigate-respond.md) です。 このプロセスの詳細については、 [概要](eval-defender-investigate-respond.md) に関する記事を参照してください。

[シミュレートされた攻撃に対してインシデント対応を](eval-defender-investigate-respond-simulate-attack.md)実行したら、次のMicrosoft 365 Defender機能を調べることができます。

|機能 |説明 |
|:-------|:-----|
| [インシデントの優先順位付け](#prioritize-incidents) | インシデント キューのフィルター処理と並べ替えを使用して、次に対処するインシデントを特定します。 |
| [インシデントの管理](#manage-incidents) | インシデントのプロパティを変更して、正しい割り当て、タグとコメントの追加、インシデントの解決を行います。 |
| [自動調査および対応](#examine-automated-investigation-and-response-with-the-action-center) | 自動調査と対応 (AIR) 機能を使用して、セキュリティ運用チームがより効率的かつ効果的に脅威に対処できるようにします。 アクション センターは、保留中の修復アクションの承認など、インシデントタスクとアラート タスクの "1 つのウィンドウ" エクスペリエンスです。 |
| [高度な追求](#use-advanced-hunting) | クエリを使用して、ネットワーク内のイベントを事前に検査し、脅威インジケーターとエンティティを見つけます。 また、インシデントの調査と修復中に高度な捜索を使用します。 |


## <a name="prioritize-incidents"></a>インシデントの優先度を設定する

Microsoft 365 Defender ポータルのクイック起動時に **、インシデント&アラート>インシデントからインシデント** キューにアクセス <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender ポータルの [インシデント&アラート] セクション" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::


[ **最新のインシデントとアラート]** セクションには、受信したアラートの数と過去 24 時間に作成されたインシデントのグラフが表示されます。

インシデントの一覧を調べ、割り当てと調査の重要度を優先順位付けするには、次のことができます。 

- カスタマイズ可能な列を構成する ( **[列の選択] を選択**) して、インシデントや影響を受けるエンティティのさまざまな特性を把握できるようにします。 これにより、分析のためにインシデントの優先順位付けに関する情報に基づいた意思決定を行うことができます。

- フィルター処理を使用して、特定のシナリオまたは脅威に焦点を当てます。 インシデント キューにフィルターを適用すると、どのインシデントに即座に注意が必要かを判断するのに役立ちます。 

既定のインシデント キューから [ **フィルター** ] を選択すると、[ **フィルター]** ウィンドウが表示され、そこから特定のインシデントセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Microsoft 365 Defender ポータルの [インシデント&アラート] セクションの [フィルター] ウィンドウ" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

詳細については、「インシデントの [優先順位付け](incident-queue.md)」を参照してください。

## <a name="manage-incidents"></a>インシデントを管理する

インシデントを管理するには、インシデント用の[**インシデントの管理**] ウィンドウから行います。 次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Microsoft 365 Defender ポータルの [インシデント&アラート] セクションの [インシデントの管理] ウィンドウ" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

このウィンドウは、次のページの [ **インシデントの管理** ] リンクから表示できます。

- インシデント キュー内のインシデントの [プロパティ] ウィンドウ。
- インシデント **の概要** ページ。

インシデントを管理する方法を次に示します。

- インシデント名を編集する

  セキュリティ チームのベスト プラクティスに基づいて、自動的に割り当てられた名前を変更します。
  
- インシデント タグを追加する

  セキュリティ チームがインシデントを分類するために使用するタグを追加します。これは後でフィルター処理できます。
  
- インシデントを割り当てる

  ユーザー アカウント名に割り当てます。後でフィルター処理できます。
  
- インシデントを解決する

  修復後にインシデントを閉じます。
  
- その分類と決定を設定する

  インシデントを解決するときに、脅威の種類を分類して選択します。
  
- コメントを追加する

  セキュリティ チームのベスト プラクティスに基づいて、進行状況、メモ、その他の情報にコメントを使用します。 完全なコメント履歴は、インシデントの詳細ページの **[コメントと履歴** ] オプションから使用できます。

詳細については、「インシデントの [管理](manage-incidents.md)」を参照してください。

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>アクション センターで自動調査と対応を調べる

組織に対して自動調査機能と応答機能を構成する方法に応じて、修復アクションが自動的に実行されるか、セキュリティ運用チームの承認に基づいてのみ実行されます。 保留中か完了かを問わず、すべてのアクションが [アクション センター](m365d-action-center.md)に一覧表示され、デバイス、電子メール &コラボレーション コンテンツ、ID の保留中と完了済みの修復アクションが 1 つの場所に一覧表示されます。

次に例を示します。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender ポータルの統合アクション センター" lightbox="../../media/m3d-action-center-unified.png":::

アクション センターから保留中のアクションを選択し、ポップアップ ウィンドウで承認または拒否できます。 次に例を示します。

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Microsoft 365 Defender ポータルでアクションを承認または拒否するオプションを表示するウィンドウ" lightbox="../../media/air-actioncenter-itemselected.png":::


保留中のアクションをできるだけ早く承認 (または拒否) して、自動調査を適切なタイミングで進め、完了できるようにします。

詳細については、「[自動調査と対応と](m365d-autoir.md)[アクション センター」を](m365d-action-center.md)参照してください。

## <a name="use-advanced-hunting"></a>高度なハンティングを使用する

> [!NOTE]
> 高度なハンティング シミュレーションについて説明する前に、次のビデオを参照して高度なハンティングの概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作に役立つ方法を確認してください。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


オプションの [ファイルレス PowerShell 攻撃シミュレーション](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) が、既に資格情報アクセス ステージに達していた実際の攻撃であった場合は、調査の任意の時点で高度な捜索を使用して、生成されたアラートと影響を受けるエンティティから既に知っていることを使用して、ネットワーク内のイベントやレコードを事前に検索できます。 

たとえば、[ユーザーと IP アドレス偵察 (SMB)](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity) アラートの情報に基づいて、テーブルを`IdentityDirectoryEvents`使用してすべての SMB セッション列挙イベントを検索したり、テーブルを使用して`IdentityQueryEvents`データのMicrosoft Defender for Identity他のさまざまなプロトコルで探索アクティビティを検索したりできます。


### <a name="hunting-environment-requirements"></a>ハンティング環境の要件

このシミュレーションには、1 つの内部メールボックスとデバイスが必要です。 テスト メッセージを送信するには、外部メール アカウントも必要です。

1. テナントで[Microsoft 365 Defenderが有効](m365d-enable.md#confirm-that-the-service-is-on)になっていることを確認します。
2. 電子メールの受信に使用するターゲット メールボックスを特定します。

   - このメールボックスは、Microsoft Defender for Office 365によって監視する必要があります

   - 要件 3 のデバイスは、このメールボックスにアクセスする必要があります

3. テスト デバイスを構成します。

    a.  Windows 10 バージョン 1903 以降のバージョンを使用していることを確認します。

    b. テスト デバイスをテスト ドメインに参加させます。

    c. [Windows Defender ウイルス対策をオンにします](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 Windows Defender ウイルス対策を有効にできない場合は、[このトラブルシューティング トピックを](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)参照してください。

    d. [Microsoft Defender for Endpointにオンボード](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)します。

### <a name="run-the-simulation"></a>シミュレーションを実行する

1. 外部メール アカウントから、ハンティング環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。 既存の電子メール フィルター ポリシーで許可される添付ファイルを含めます。 このファイルは、悪意のあるファイルや実行可能ファイルである必要はありません。 推奨されるファイルの種類は<i>、.pdf</i>、 <i>.exe</i> (許可されている場合)、Word ファイルなどのOfficeドキュメントの種類です。

2. ハンティング環境の要件セクションの手順 3 で定義されているように構成されたデバイスから送信された電子メールを開きます。 添付ファイルを開くか、デバイスにファイルを保存します。

#### <a name="go-hunting"></a>ハンティングに行く

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>を開きます。

2. ナビゲーション ウィンドウで、[ **ハンティング>高度なハンティング**] を選択します。

3. メール イベントの収集から始まるクエリを作成します。

   1. [ **クエリ] > [新規**] を選択します。

   1. [**高度な検索**] の [**電子メール** グループ] で、[**EmailEvents**] をダブルクリックします。 クエリ ウィンドウにこれが表示されます。

      ```console
      EmailEvents
      ```

   1. クエリの時間枠を過去 24 時間に変更します。 上記のシミュレーションを実行したときに送信したメールが過去 24 時間であったと想定し、それ以外の場合は必要に応じて時間枠を変更します。

   1. **[クエリの実行]** を選択します。 パイロット環境によって結果が異なる場合があります。

      > [!NOTE]
      > データの戻り値を制限するフィルター オプションについては、次の手順を参照してください。

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-1.png" alt-text="Microsoft 365 Defender ポータルの [高度なハンティング] ページ" lightbox="../../media/advanced-hunting-incident-response-try-1.png":::

        > [!NOTE]
        > 高度な検索では、クエリ結果が表形式のデータとして表示されます。 グラフなどの他の形式でデータを表示することもできます。

   1. 結果を確認し、開いたメールを特定できるかどうかを確認します。 高度な捜索でメッセージが表示されるまでに最大 2 時間かかる場合があります。 結果を絞り込むために、クエリに **where** 条件を追加して、SenderMailFromDomain として "yahoo.com" を持つメールのみを検索できます。 次に例を示します。

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. レコードを調べるには、クエリから結果の行をクリックします。

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-2.png" alt-text="Microsoft 365 Defender ポータルの [高度なハンティング] ページの [検査レコード] セクション" lightbox="../../media/advanced-hunting-incident-response-try-2.png":::

4. メールが表示されることを確認したので、添付ファイルのフィルターを追加します。 環境内の添付ファイルを含むすべてのメールに焦点を当てます。 このシミュレーションでは、環境から送信されるメールではなく、受信メールに焦点を当てます。 追加したフィルターを削除してメッセージを探し、"| **ここで AttachmentCount > 0** と **EmailDirection** == **"Inbound""**

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

   :::image type="content" source="../../media/advanced-hunting-incident-response-try-3.png" alt-text="Microsoft 365 Defender ポータルの [高度な検索] ページの [クエリ編集] セクション" lightbox="../../media/advanced-hunting-incident-response-try-3.png":::

   > [!NOTE]
   > **[検出ルールの作成**] をクリックすると、クエリに構文エラーが発生しても、検出ルールは保存されません。 クエリを再確認して、エラーがないことを確認します。

2. 必要なフィールドに、セキュリティ チームがアラートを理解できるようにする情報、それが生成された理由、および必要なアクションを入力します。

   :::image type="content" source="../../media/mtp/fig23.png" alt-text="Microsoft 365 Defender ポータルの [アラートの詳細] ページ" lightbox="../../media/mtp/fig23.png":::

   この検出ルールアラートに関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください

3. このアラートで影響を受けたエンティティを選択します。 この場合は、[ **デバイス** ] と [メールボックス] を選択 **します**。

   :::image type="content" source="../../media/mtp/fig24.png" alt-text="Microsoft 365 Defender ポータルの影響を受けたエンティティの詳細ページ" lightbox="../../media/mtp/fig24.png":::

4. アラートがトリガーされた場合に実行するアクションを決定します。 この場合はウイルス対策スキャンを実行しますが、他のアクションを実行することもできます。

   :::image type="content" source="../../media/mtp/fig25.png" alt-text="Microsoft 365 Defender ポータルの [アクション] ページ" lightbox="../../media/mtp/fig25.png":::

5. アラート ルールのスコープを選択します。 このクエリにはデバイスが含まれるため、デバイス グループは、Microsoft Defender for Endpointコンテキストに従ってこのカスタム検出に関連します。 影響を受けるエンティティとしてデバイスを含まないカスタム検出を作成する場合、スコープは適用されません。

   :::image type="content" source="../../media/mtp/fig26.png" alt-text="Microsoft 365 Defender ポータルの [スコープ] ページ" lightbox="../../media/mtp/fig26.png":::


   このパイロットでは、このルールを運用環境のテスト デバイスのサブセットに制限することができます。

6. **[作成]** を選択します。 次に、ナビゲーション パネルから **[カスタム検出規則** ] を選択します。

   :::image type="content" source="../../media/mtp/fig27a.png" alt-text="Microsoft 365 Defender ポータルの [カスタム検出規則規則] オプション" lightbox="../../media/mtp/fig27a.png":::

   :::image type="content" source="../../media/mtp/fig27b.png" alt-text="Microsoft 365 Defender ポータルで検出ルールと実行の詳細を表示するページ" lightbox="../../media/mtp/fig27b.png":::

   このページから検出ルールを選択すると、詳細ページが開きます。

   :::image type="content" source="../../media/mtp/fig28.png" alt-text="Microsoft 365 Defender ポータルでトリガーされたアラートの詳細を表示するページ" lightbox="../../media/mtp/fig28.png":::


### <a name="expert-training-on-advanced-hunting"></a>高度な捜索に関するエキスパート トレーニング

**敵対者を追跡** することは、新しいセキュリティ アナリストと経験豊富な脅威の専門家向けの Web キャスト シリーズです。 高度な捜索の基本をガイドして、独自の高度なクエリを作成します。 

[高度なハンティングに関するエキスパート トレーニングを](advanced-hunting-expert-training.md)受けて作業を開始する方法に関する説明をご覧ください。

### <a name="navigation-you-may-need"></a>必要なナビゲーション

[Microsoft 365 Defender評価環境を作成する](eval-create-eval-environment.md)
