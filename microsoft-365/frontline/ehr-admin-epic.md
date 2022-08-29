---
title: Teams での仮想アクセス - Epic EHR への統合
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ansantam
description: Teams EHR コネクタを統合して、組織内の医療プロバイダーが Epic EHR システムから直接 Teams の患者または他のプロバイダーと仮想予約を行えるようにする方法について説明します。
ms.openlocfilehash: 6cf48c01e804a6a8a473ae42883c000a9577ea01
ms.sourcegitcommit: 0c8934129b5ed147fb873fc3f4d201042c313571
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67333788"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Teams での仮想アクセス - Epic EHR への統合

Microsoft Teams の電子健康記録 (EHR) コネクタを使用すると、臨床医は簡単に仮想患者の予定を開始したり、Epic EHR システムから Microsoft Teams の別のプロバイダーと直接相談したりできます。 Microsoft 365 クラウド上に構築された Teams は、HIPAA、HITECH 認定などのコンプライアンスをサポートする 1 つのハブで、チャット、ビデオ、音声、ヘルスケア ツールとの簡単で安全なコラボレーションとコミュニケーションを実現します。

Teams のコミュニケーションとコラボレーション プラットフォームにより、臨床医は断片化されたシステムの混乱を簡単に切り取り、可能な限り最善のケアを提供することに集中できます。 Teams EHR コネクタを使用すると、次のことができます。

- 統合された臨床ワークフローを使用して、Epic EHR システムから Teams 仮想予定を起動します。
- 患者が患者ポータル内または SMS 経由で Teams 仮想予定に参加できるようにします。
- マルチ参加者、グループ訪問、インタープリター サービスなど、その他のシナリオをサポートします。
- Teams 仮想予定に関するメタデータを EHR システムに書き戻し、出席者が接続、切断、自動監査と記録の保持を有効にしたときに記録します。
- EHR に接続された予定の消費データ レポートとカスタマイズ可能な通話品質情報を表示します。

この記事では、Epic プラットフォームと統合するように Teams EHR コネクタを設定して構成する方法について説明します。 また、Epic EHR システムの Teams 仮想予定エクスペリエンスの概要についても説明します。

## <a name="before-you-begin"></a>はじめに

作業を開始する前に、統合の準備を行うためにいくつかの操作を行う必要があります。

### <a name="get-familiar-with-the-integration-process"></a>統合プロセスについて理解する

統合プロセス全体を理解するには、次の情報を確認してください。

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="統合プロセス全体の手順をまとめた画像。":::

| &nbsp; |アプリへのアクセスを要求する|アプリの有効化|コネクタの構成|Epic 構成|テスト|
|--------|---------|---------|---------|---------|---------|
| **Duration** | 約 12 ~ 24 時間| 約 24 時間 | 約 1 ~ 3 日 | 約 1 ~ 3 日 | &nbsp; |
| **操作**| [Teams アプリへのアクセスを要求します](#request-access-to-the-teams-app)。  | 公開キーと秘密キーの証明書を作成し、Epic にアップロードします。 | EHR コネクタ構成ポータルで構成手順を完了します。  | Epic の技術スペシャリストと協力して、Epic で FDI レコードを構成します。| テスト環境でテストを完了します。 |
| **結果**| テストのために組織を承認します。 | Epic は公開キー証明書を同期します。 | Epic 構成の FDI レコードを受け取ります。 | 構成が完了しました。 テストする準備ができました。 | フローの完全な検証と運用への移行の決定。 |


### <a name="request-access-to-the-teams-app"></a>Teams アプリへのアクセスを要求する

Teams アプリへのアクセスを要求する必要があります。

1. [Epic App Marketplace](https://apporchard.epic.com/Gallery?id=16793) で Teams アプリのダウンロードを要求します。 これを行うと、Epic から Microsoft EHR コネクタ チームへの要求がトリガーされます。
1. 要求を行った後、組織名、テナント ID、および Epic 技術連絡先の電子メール アドレスを含む電子メールを [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) に送信します。
1. Microsoft EHR コネクタ チームがメールに返信し、有効化の確認を行います。

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Epic-Microsoft Teams Telehealth 統合ガイドを確認する

「[Epic-Microsoft Teams Telehealth Integration ガイド](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)」を Epic の技術専門家と一緒にご確認ください。 前提条件が満たされていることを確認する

## <a name="prerequisites"></a>前提条件

- Microsoft Cloud for Healthcare へのアクティブなサブスクリプション、または Microsoft Teams EHR コネクタ スタンドアロン オファーのサブスクリプション (運用環境の EHR 環境でテストする場合にのみ適用されます)。
- Epic バージョン 2018 年 11 月以降
- ユーザーは、Teams 会議を含む適切な Microsoft 365 またはOffice 365 ライセンスを持っています。
- Teams が採用され、医療組織で使用されます。
- [Teams 管理センター](https://admin.teams.microsoft.com)にアクセスできる Microsoft 365 グローバル管理者である組織内のユーザーを特定しました。
- システムは、Teams のすべての[ソフトウェアとブラウザーの要件](/microsoftteams/hardware-requirements-for-the-teams-app)を満たしています。

> [!IMPORTANT]
> 統合を進める前に、統合前の手順を完了し、すべての前提条件が満たされていることを確認してください。

統合手順は、組織内の次のユーザーによって実行されます。

- **Microsoft 365 グローバル管理者**: 統合を担当する主な担当者。 管理者はコネクタを構成し、SMS (必要に応じて) を有効にし、構成を承認する Epic カスタマー アナリストを追加します。
- **Epic の顧客アナリスト**: 組織内で、Epic へのログイン資格情報を持つユーザー。 管理者が入力した構成設定を承認し、構成レコードを Epic に提供します。

Microsoft 365 管理者と Epic の顧客アナリストは、同じユーザーにすることができます。

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR コネクタを設定する

コネクタの設定には、次のことが必要です。

- [EHR コネクタ構成ポータルを起動する](#launch-the-ehr-connector-configuration-portal)
- [構成情報を入力する](#enter-configuration-information)
- [SMS 通知を有効にする (省略可能)](#enable-sms-notifications-optional)
- [構成を承認または表示する](#approve-or-view-the-configuration)
- [構成を確認して終了する](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR コネクタ構成ポータルを起動する

まず、Microsoft 365 管理者が [EHR コネクタ構成ポータル](https://ehrconnector.teams.microsoft.com) を起動し、Microsoft 365 資格情報を使用してサインインします。

Microsoft 365 管理者は、統合をテストするために、1 つの部署または複数の部門を構成できます。 構成ポータルでテスト URL と本番 URL を構成します。 運用に移行する前に、Epic テスト環境から統合をテストしてください。

> [!NOTE]
> Microsoft 365 管理者と Epic カスタマー アナリストは、構成ポータルで統合手順を完了する必要があります。 Epic の構成手順については、組織に割り当てられている Epic 技術スペシャリストにお問い合わせください。

### <a name="enter-configuration-information"></a>構成情報を入力する

次に、統合を設定するために、Microsoft 365 管理者は次の操作を行います。

1. Epic 技術スペシャリストから Fast Health 相互運用性リソース (FHIR) ベース URL を追加し、環境を指定します。 組織のニーズとテストする環境に応じて、必要な数の FHIR ベース URL を構成します。

    - FHIR ベースの URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。 URL の例は An example URL is `https://lamnahealthcare.com/fhir/auth/connect-ocurprd-oauth/api/FHDST`.

    - テスト環境と運用環境の統合を設定できます。 初期セットアップでは、運用環境に移行する前に、テスト環境からコネクタを構成することをお勧めします。

1. 後の手順で構成を承認する Epic カスタマー アナリストのユーザー名を追加します。

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="追加する承認者を示す [構成] ページのスクリーンショット。" lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>SMS 通知を有効にする (省略可能)

> [!NOTE]
> SMS 通知は現在、米国でのみ使用できます。 Teams の今後のリリースでは、この機能を他のリージョンで使用できるように取り組んでおり、利用可能な場合は、この記事を更新します。

組織が患者の SMS 通知を Microsoft が管理することを望む場合は、この手順を完了します。 SMS 通知を有効にすると、患者はスケジュールされた予定の確認メッセージとリマインダー メッセージを受け取ります。

SMS 通知を有効にするには、Microsoft 365 管理者が次の操作を行います。

1. SMS 通知ページで、次の両方の同意チェック ボックスを選択します。

    - Microsoft が組織に代わって患者に SMS 通知を送信できるようにします。
    - 出席者が SMS メッセージの送受信に同意したことを確認します。
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="SMS 通知ページのスクリーンショット。同意チェック ボックスと電話番号を生成するオプションが表示されています。" lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. **[電話番号]** で **[新しい電話番号を生成する]** を選択して、組織の電話番号を生成します。 これにより、新しい電話番号を要求して生成するプロセスが開始されます。 このプロセスが完了するまでに最大 2 分かかる場合があります。

    電話番号が生成されると、画面に表示されます。 この番号は、SMS の確認とリマインダーを患者に送信するために使用されます。 この番号はプロビジョニングされていますが、FHIR ベース URL にリンクされていません。 これは、次の手順で行います。

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="生成される電話番号の例を示すスクリーンショット。" lightbox="media/ehr-connector-epic-phone-number.png":::

    **[完了]** を選択し、**[次へ]** を選択します。

1. 電話番号を FHIR ベース URL にリンクするには、**[SMS 構成]** セクションの **[電話番号]** で番号を選択します。 SMS 通知を有効にする FHIR ベース URL ごとにこれを行います。

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="電話番号を FHIR ベース URL にリンクする方法を示すスクリーンショット。" lightbox="media/ehr-connector-epic-link-phone-number.png":::

    コネクタを初めて構成する場合は、前の手順で入力した FHIR ベースの URL が表示されます。 同じ電話番号を複数の FHIR ベースの URL にリンクできます。つまり、患者は異なる組織や部署に対して同じ電話番号から SMS 通知を受け取ります。

1. 各 FHIR ベース URL の横にある **SMS セットアップ** を選択して、患者に送信する SMS 通知の種類を設定します。

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="SMS セットアップ設定を示すスクリーンショット。" lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **確認 SMS**: EHR システムで予定がスケジュール、更新、または取り消されたときに、患者に通知が送信されます。
    - **アラーム SMS**: 通知は、指定した時間間隔と予定のスケジュールされた時刻に従って患者に送信されます。

    **[保存]** を選択します。

1. [**証明書のアップロード**] を選択して公開キー証明書をアップロードします。 環境ごとに Base64 でエンコードされた (公開キーのみ) .cer 証明書をアップロードする必要があります。

    SMS 通知を送信するための予定情報を受信するには、公開キー証明書が必要です。 証明書は、受信情報が有効なソースからの情報であることを確認するために必要です。

    コネクタを使用して SMS アラームを送信すると、Epic で予定が作成されると、患者の電話番号が HL7v2 ペイロードで Epic によって送信されます。 これらの番号は、組織の地域の予定ごとに格納され、予定が行われるまで保持されます。 HL7v2 メッセージを構成する方法の詳細については、 [Epic -Microsoft Teams Telehealth 統合ガイド](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)を参照してください。

    **次へ** を選択します。

> [!NOTE]
> Microsoft 365 管理者はいつでも SMS 設定を更新できます。 設定を変更すると、SMS サービスが停止する可能性があることに注意してください。 SMS レポートを表示する方法の詳細については、「[Teams EHR コネクタ 仮想予定 レポート](ehr-connector-report.md)」を参照してください。

### <a name="approve-or-view-the-configuration"></a>構成を承認または表示する

承認者として追加された組織内の Epic カスタマー アナリストは [、EHR コネクタ構成ポータル](https://ehrconnector.teams.microsoft.com) を起動し、Microsoft 365 資格情報を使用してサインインします。 検証に成功すると、承認者はEpic の資格情報を使用して Epic 組織を検証するサインインを求められます。

> [!Note]
> Microsoft 365 管理者と Epic カスタマー アナリストが同じユーザーである場合でも、アクセスを検証するために Epic にサインインする必要があります。 Epic サインインは、FHIR ベース URL を検証するためにのみ使用されます。 Microsoft では、このサインインで資格情報を保存したり、EHR データにアクセスしたりすることはありません。

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="[ログインと承認] オプションを示す [構成の承認または表示] ページのスクリーンショット。" lightbox="media/ehr-connector-epic-login-approve.png":::

Epic へのサインインに成功した後、Epic の顧客アナリストは構成を承認する **必要があります**。 構成が正しくない場合、Microsoft 365 管理者は構成ポータルにサインインして設定を変更できます。

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="[承認] オプションを示す [構成の承認] ページまたは [構成の表示] ページのスクリーンショット。" lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>構成を確認して完了する

構成情報が Epic 管理者によって承認されると、患者とプロバイダーの立ち上げに関する統合レコードが表示されます。 統合レコードには、次のものが含まれます。

- 患者とプロバイダーのレコード
- ダイレクト SMS レコード
- SMS 構成レコード
- デバイス テスト構成レコード

デバイス テストのコンテキスト トークンは、患者統合レコードにあります。 Epic の顧客アナリストは、Epic で仮想予定の構成を完了するために、これらのレコードをEpic に提供する必要があります。 [詳細については、Epic-Microsoft Teams Telehealth 統合ガイドを参照してください。](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)

> [!Note]  
> Microsoft 365 管理者はいつでも、構成ポータルにサインインして統合レコードを表示し、必要に応じて構成設定を変更できます。

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="統合情報を示す [校閲と終了] ページのスクリーンショット。" lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> Epic の顧客アナリストは、Microsoft 365 管理者によって構成された各 FHIR ベース URL の承認プロセスを完了する必要があります。

## <a name="launch-teams-virtual-appointments"></a>Teams 仮想予定を起動する

EHR コネクタの手順と Epic の構成手順を完了すると、組織はチームとのビデオ アポイントメントをサポートする準備が整います。

### <a name="virtual-appointments-prerequisites"></a>仮想予定の前提条件

- システムは、Teams のすべての[ソフトウェアとブラウザーの要件](/microsoftteams/hardware-requirements-for-the-teams-app)を満たしている必要があります。

- Epic 組織と Microsoft 365 組織の間の統合セットアップが完了しました。

### <a name="provider-experience"></a>プロバイダー エクスペリエンス

組織の医療プロバイダーは、Epic プロバイダー アプリ (Hyperspace、Haiku、Canto) から Teams を使用して予定に参加できます。 **[仮想アクセスの開始]** ボタンは、プロバイダー フローに組み込まれています。

  ![患者との仮想予定のプロバイダー エクスペリエンス。](media/ehc-provider-experience-6.png)

プロバイダー エクスペリエンスの主な機能:

- プロバイダーは、サポートされているブラウザーまたは Teams アプリを使用して予定に参加できます。

- プロバイダーは、初めて予定に参加するときに、Microsoft 365 アカウントで 1 回限りのサインインを行う必要があります。

- 1 回限りのサインイン後、プロバイダーは Teams の仮想予定に直接移動します。 (プロバイダーは Teams にサインインする必要があります)。

- プロバイダーは、PowerChart で特定の予定の予定に接続している患者のリアルタイムの更新を確認できます。 プロバイダーは、患者がいつ予定に接続されているかを確認できます。

> [!NOTE]
> 医療記録の継続性または保有目的に必要な会議チャットに入力されたすべての情報は、医療提供者がダウンロード、コピー、および注意する必要があります。 チャットは、法的な医療記録や指定されたレコード セットを構成しません。 チャットからのメッセージは、Microsoft Teams 管理者によって作成された設定に基づいて保存されます。

### <a name="patient-experience"></a>患者エクスペリエンス

コネクタは、SMS テキスト メッセージ内のリンクを介して予約に参加する患者をサポートします。 予約の時点で、患者は **[仮想訪問の開始** ] ボタンを使用するか、SMS テキスト メッセージのリンクをタップして、MyChart から予定を開始できます。

  ![仮想予定の患者エクスペリエンス。](media/ehc-virtual-visit-5.png)

患者エクスペリエンスの主な機能:

- 患者は、 [Teams アプリをインストールしなくても、デスクトップとモバイルの最新の Web ブラウザー](browser-join.md)から予定に参加できます。
- 患者は、予定に参加する前にデバイスのハードウェアと接続をテストできます。

    :::image type="content" source="media/ehr-admin-epic-device-test.png" alt-text="デバイスのテスト機能を示すモバイル デバイスの画像。" lightbox="media/ehr-admin-epic-device-test.png":::
  
    デバイス テスト機能:

  - 患者は、話者、マイク、カメラ、接続をテストできます。
  - 患者はテスト呼び出しを完了して、構成を完全に検証できます。
  - デバイス テストの結果は、EHR システムに送り返すことができます。

- 患者はワンクリックで予定に参加でき、他のアカウントやサインインは必要ありません。

- 患者は、Microsoft アカウントを作成したり、アクセスを開始するためにサインインしたりする必要はありません。

- 患者は、プロバイダーが参加して入院するまでロビーに配置されます。

- 患者は、予定に参加する前にロビーでビデオとマイクをテストできます。

> [!Note]
> Epic、MyChart、Haiku、および Canto は、Epic Systems Corporation の商標です。

## <a name="get-insight-into-virtual-appointments-usage"></a>仮想予定の使用状況に関する分析情報を取得する

Microsoft Teams 管理センターの [[Virtual Visits 使用状況レポート]](virtual-visits-usage-report.md) では、組織内の Teams 仮想予定アクティビティの概要が管理者に表示されます。 レポートには、EHR システムから行われる Teams EHR 統合会議を含む、仮想予定の詳細な分析が表示されます。

ロビーの待機時間や予定の期間などの主要なメトリックを表示できます。 この情報を使用して使用状況の傾向を把握し、仮想予定を最適化してビジネス成果を向上させるために役立ちます。

### <a name="privacy-and-location-of-data"></a>データのプライバシーと場所

Teams を EHR システムに統合すると、統合および仮想予定フロー中に使用および保存されるデータの量が最適化されます。 このソリューションは、Teams のプライバシーとデータ管理の原則、および Teams のプライバシーで概説されているガイドラインに従います。

Teams EHR コネクタは、EHR システムから識別可能な個人データや患者または医療提供者の健康記録を保存または転送しません。 EHR コネクタによって保存される唯一のデータは、EHR ユーザーの一意の ID であり、Teams 会議のセットアップ中に使用されます。

EHR ユーザーの一意の ID は、「[Microsoft 365 の顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」で説明されている 3 つの地理的地域のいずれかに保存されます。 会議参加者が Teams で共有するすべてのチャット、レコーディング、その他のデータは、既存のストレージ ポリシーに従って保存されます。 Teams のデータの場所の詳細については、「[Teams のデータの場所](/microsoftteams/location-of-data-in-teams)」を参照してください。

## <a name="related-articles"></a>関連記事

- [Teams 仮想訪問の使用状況レポート](virtual-visits-usage-report.md)
- [Teams EHR コネクタ仮想予定レポート](ehr-connector-report.md)
- [医療関係組織のための Teams の使用を開始する](teams-in-hc.md)
