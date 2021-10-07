---
title: 手順 5. ハイブリッド ワーカー生産性向上アプリとサービスを展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Teams、Exchange、SharePoint、その他の Microsoft 365 サービスを利用することで、ユーザーの生産性を向上できます。
ms.openlocfilehash: 36aa96b1355eec41060881da26f7e709a5058898
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190151"
---
# <a name="step-5-deploy-hybrid-worker-productivity-apps-and-services"></a>手順 5. ハイブリッド ワーカー生産性向上アプリとサービスを展開する

生産性を高めるには、リモートワーカー間のコミュニケーションとコラボレーションが重要です。 会議、音声やテキストでのチャット、新しいコンテンツの作成と情報やファイルの共有、メールのやりとり、予定表やタスクの管理を行う必要があります。 Microsoft 365 は、次の主要な機能すべてをクラウドベースのサービスで実現します。

| IT 関数 | Microsoft 365 コンポーネント | 説明 |
|:-------|:-----|:-------|
| メール サービス | Exchange Online | Outlook クライアントを使用した、メール交換、および予定表、連絡先、タスクの管理。 |
| 組織のチャット、ボイス オーバー IP (VOIP)、およびチーム ベースのコラボレーション | Microsoft Teams | 組織、部門、および小規模なチームや個人向けの会議、チャット、ファイル ストレージの共通のコミュニケーション ハブを使用して、離れて作業をしながら密接な連携を維持します。 |
| イントラネット サイト、ドキュメント コラボレーション | SharePoint および OneDrive | Web ブラウザ内または Teams 内のファイルを保存して共同作業します。 |
| デスクトップおよびモバイル デバイスの Office アプリケーション | Microsoft 365 Apps | ローカル コンピューターにインストールされ、継続的な機能とセキュリティの更新を受け取るバージョンの Word、PowerPoint、Excel、および Outlook を使用して、新しいコンテンツの作成や、既存のコンテンツに対しての共同作業を行います。 |
||||

![Teams、Outlook、SharePoint、OneDrive、Microsoft 365 Apps を使用して生産性を維持します。](../media/empower-people-to-work-remotely/remote-workers-productivity-grid.png)

## <a name="keep-people-connected-with-microsoft-teams"></a>Microsoft Teams を使用して密接な連携を維持する

Teams を使うことで、チャット、会議、通話、共同作業をすべて 1 つの場所で行えます。 何百万人ものユーザーが毎日 Teams で仕事をこなしています。Teams には、オンサイトまたはリモート ワークに必要なすべてのものが、チームワーク用のハブにまとめられているからです。 

詳細なガイドについては、「[Microsoft Teams を使用してリモート ワーカーをサポートする](/microsoftteams/support-remote-work-with-teams)」を参照してください。 

Teams をハイブリッド ワークに使用するためのガイダンスとデモについては、「[Microsoft Teams Web キャストによるハイブリッド ワークの有効化](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)」をご覧ください。

### <a name="chat-and-conversations"></a>チャットと会話

チャットとスレッド形式の会話は、Teams の中核的な機能で、1 対 1 のチャットに加え、グループでのチャットや会話もサポートしています。 リモート ワーカーは、グループ チャットや 1 対 1 のメッセージで、GIF、ステッカー、絵文字を使用して情報、意見、自分らしさを共有できます。

### <a name="meetings-and-conferencing"></a>ミーティングと会議 

Teams は、ハイブリッド ワーカーとのコミュニケーションや情報共有に非常に役立ちます。特に、Teams の会議は、最大 250 人が参加できます。 Teams 会議を使用すると、組織の内外の人との対話的な共同会議を行うことができます。 リモート ワーカーは、プロジェクトの定期チェックポイント、同僚との意見交換、ブレーンストーミング セッション、顧客との会話促進など、さまざまな日常業務で Teams 会議を利用できます。 

### <a name="calling"></a>通話

Teams では、フェデレーションを使用して、ユーザー間だけでなく、他の組織との間の直接の VoIP 通話もサポートします。 この機能では、会議と同じコーデックが使用されます。また、PSTN 課金なしで、世界中に高品質の音声を提供します。 ただし、オンサイトまたはリモートで作業している場合、ユーザーによっては外線通話を受けるために専用の電話番号が必要になる場合があります。 Teams は、外線通話が必要なユーザーが電話をかけたり受けたりするためのクラウド電話サービスを迅速に提供できます。

### <a name="apps-and-workflows"></a>アプリとワークフロー

Teams は、デスクトップ、Web、モバイル バージョンの Teams からアクセスできるアプリやワークフローのプラットフォームを提供します。 Teams には、Microsoft やサード パーティが公開しているアプリが何百個も用意されており、ユーザー参加の促進、生産性のサポート、よく使用されるビジネス サービスの Teams への統合に使用できます。 ユーザーと管理者は、ローコードの Power Apps および Power Automate 開発ツールを使用して、Teams 用のカスタム アプリや自動ワークフローを作成することもできます。

アプリやワークフローを使用すると、重要な情報の収集と共有、繰り返し実行するタスクの自動化、対話型ボットとのチャットが可能になるため、ハイブリッド ワーカーの Teams での生産性をさらに高めることができます。 アプリをチャネルまたは Teams アプリ バーにピン留めすることは、ユーザーがこれらのアプリを関連性のある領域で簡単にアクセスできるようにするための優れた方法です。また、管理者はアプリをピン留めすることにより、すべてのユーザーが使用する必要のあるアプリの認知と採用を促進することができます。

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a>Exchange Online と Outlook を使用した、メール交換、および予定表、連絡先、タスクの管理

リモート ワーカーは、Outlook を使用することにより、メール、予定表、連絡先、タスクなどにいつでもアクセスでき、一元的に管理することができます。 Outlook は、ユーザーが自分に関連する内容を基に、予定どおり作業を遂行したり、1 日の作業に優先順位を付けたりするのに役立ちます。 Outlook を使用すると、添付ファイルを OneDrive から直接共有したり、Teams 会議を計画して参加したり、予定表を表示して共有したり、他のユーザーに代理アクセス権を提供したりできます。 ハイブリッド ワーカーは、仕事上の約束と個人的な約束の両方について、次の予定を知り、何に注意が必要かを把握することにより、重要な問題に注意を集中できるようになります。 Outlook は、ハイブリッド ワーカーが自分の時間を管理をしたり、ファイルや組織内の人物など、必要な情報を簡単に見つけたりするのに役立ちます。 

組織のメールと、先進認証と条件付きアクセスをサポートするメール クライアントを保護する、推奨される ID とデバイス アクセス ポリシーについては、[こちらの記事](../security/office-365-security/secure-email-recommended-policies.md)を参照してください。

## <a name="store-and-collaborate-on-files-with-sharepoint-and-onedrive"></a>SharePoint と OneDrive でファイルを格納して共同編集

ハイブリッド ワーカーは、コンテンツの共同作業のために SharePoint と OneDrive フォルダーをクラウド内の中心的な場所として使用して、ファイルの保存と共有、共同編集、コミュニケーション、共同作業を行うことができます。 リモート ワーカーは、Web ブラウザー、Teams、Office アプリのどこからでも安全に作業を行うことができます。

以下から SharePoint か OneDrive へドキュメントを移行しなければならない場合もあります。

- [SharePoint Server チームサイト](/sharepointmigration/sp-teams-sites-migration-guide)
- [個人用サイト](/sharepointmigration/mysites-to-onedrive-migration-guide)
- [ファイル共有](/sharepointmigration/fileshare-to-odsp-migration-guide)
- [ボックス](/sharepointmigration/box-to-onedrive-and-sharepoint-migration-guide)

SharePoint Online と OneDrive を保護するには、推奨される ID とデバイス アクセス ポリシーに関する[こちらの記事](../security/office-365-security/sharepoint-file-access-policies.md)を参照してください。

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a>Microsoft 365 アプリを使用した、コンテンツの作成と共同作業

Microsoft 365 アプリは、従業員がいつでもどこからでもシームレスに共同作業できる、エンタープライズ向けの生産的かつ安全な Office 環境です。 リモート ワーカーは、1 つのドキュメントに対して複数のユーザーと同時に共同作業したり、リアル タイムで編集や変更を確認したり、ノート PC、PC、モバイル デバイスで他のユーザーと共有編集したりできます。

詳細については、「[Microsoft 365 Apps の展開ガイド](/deployoffice/deployment-guide-microsoft-365-apps)」をご覧ください。

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a>生産性向上アプリとサービスに関する管理技術リソース

- [Microsoft Teams を使用してリモート ワーカーをサポートする](/microsoftteams/support-remote-work-with-teams)
- [Microsoft Teams Web キャストによるハイブリッド作業の有効化](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)
- [Teams Customer Success Kit のダウンロード](https://www.microsoft.com/download/details.aspx?id=54244)
- [導入を推進するためのツール](/microsoftteams/adopt-tools-and-downloads) 
- [Microsoft Teams の変更管理戦略を作成する](/MicrosoftTeams/change-management-strategy)
- [3 層の保護を使ってチームを構成する](configure-teams-three-tiers-protection.md)

## <a name="user-training-resources-for-productivity-apps-and-services"></a>生産性向上アプリとサービスに関するユーザー トレーニング リソース

- [Office と Microsoft 365 についてユーザーをトレーニングする](https://support.microsoft.com/office/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)
- [Web 用 Office を使用](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a>次の手順

[![手順 6: ユーザーを訓練し、その成功を監視します。](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)

[手順 6](empower-people-to-work-remotely-train-monitor-usage.md) に進んで、ユーザーをトレーニングし、その成功を監視します。