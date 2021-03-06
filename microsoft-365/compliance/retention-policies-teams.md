---
title: Teams の保持の詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft Teams に適用されるアイテム保持ポリシーについて説明します。
ms.openlocfilehash: 137fcdad514e8272b99ab735a0cf1ed6f6e3e00e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461798"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Microsoft Teams の保持の詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> チャットまたはメッセージが保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。
> 
> このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。

この記事の情報は[保持の詳細](retention.md)に関する記事を補足するもので、Microsoft Teams メッセージに固有の情報が含まれています。

その他のワークロードについては、以下を参照してください。

- [SharePoint と OneDrive の保持の詳細](retention-policies-sharepoint.md)
- [Yammerの保持の詳細](retention-policies-yammer.md)
- [Exchange の保持の詳細](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保持と削除の対象となる機能

次の Teams アイテムは、Teams のアイテム保持ポリシーを使用して保持および削除できます: 埋め込みの画像、テーブル、ハイパーテキスト リンク、および他の Teams メッセージ、ファイル、[カード コンテンツ](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)へのリンクを含む、チャット メッセージとチャネル メッセージ。 チャット メッセージには、チャット内のすべてのユーザーの名前が含まれ、チャネル メッセージにはチーム名とメッセージの件名 (提供されている場合) が含まれます。 

> [!NOTE]
> カード コンテンツに関する機能は最近追加され、現在はテナントにロール アウトされています。 詳細については、「[Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available (Teams 内のアプリケーションを使用したアダプティブ カード コンテンツのコンプライアンスに関する Microsoft 365 の機能が利用可能になりました)](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)」を参照してください。

プライベート チャネルの Teams メッセージは、現在、保持ポリシーではサポートされていません。 Teams のアイテム保持ポリシーを使用する場合、コード スニペット、Teams モバイル クライアントからの録音されたボイスメモ、サムネイル、お知らせ画像、および絵文字の形式での他のユーザーからの反応は含まれません。

Teams で使用するメールとファイルは、Teams のアイテム保持ポリシーに含まれていません。 これらのアイテムには、独自のアイテム保持ポリシーがあります。

## <a name="how-retention-works-with-microsoft-teams"></a>Microsoft Teams での保持のしくみ

アイテム保持ポリシーを使用して、Teams 内のチャットとチャネル メッセージからデータを保持および削除できます。 バックグラウンドでは、Exchange メールボックスを使用してこれらのメッセージを保存します。 Teams チャットのデータは、チャットに含まれる各ユーザーのメールボックスの隠しフォルダーに保存され、グループ メールボックスの同様の隠しフォルダーが Teams チャネル メッセージに使用されます。

これらのメールボックスは、RecipientTypeDetails 属性で一覧表示されます。

- **UserMailbox**: これらのメールボックスには、Exchange Online メールボックスを持つ Teams ユーザーへのメッセージが格納されます。
- **MailUser**: これらのメールボックスには、Exchange Online ではなくオンプレミスの Exchange サーバー用のメールボックスを持つ Teams ユーザーへのメッセージが格納されます。
- **GroupMailbox**: これらのメールボックスは Teams チャネルのメッセージを保存します。

Teams 会議室に使用される RoomMailbox などの他のメールボックスの種類は、Teams 保持ポリシーではサポートされていません。

Azure を利用したチャット サービスでもこのデータが保存されますが、Teams でもこのサービスを使用していることを理解することが重要です。既定では、このサービスはデータを無期限に保存します。 このため、コンプライアンス上の理由で Teams メッセージを削除する必要がある場合は、Exchange メールボックスと基盤となる Azure ベースのチャット サービスの両方からこのデータを完全に削除できる Teams の保持ポリシーを使用することをお勧めします。 基盤となるアーキテクチャの詳細については、「[Microsoft Teams のセキュリティとコンプライアンス](https://go.microsoft.com/fwlink/?linkid=871258)」、特に「[情報保護アーキテクチャ](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)」セクションを参照してください。

Teams のチャットとチャネル メッセージはメールボックスに保存されますが、この Teams のデータは、**Teams のチャネル メッセージ** と **Teams のチャット** の場所に対して構成されているアイテム保持ポリシーによってのみ含まれます。 Teams のチャットとチャネル メッセージは、Exchange ユーザーまたはグループのメールボックスに対して構成されているアイテム保持ポリシーの影響を受けません。

> [!NOTE]
> ユーザーが Teams データを保持するアクティブなアイテム保持ポリシーに含まれている場合、このポリシーに含まれるユーザーのメールボックスを削除すると、Teams のデータを保持するためにメールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)に変換されます。 ユーザーのこの Teams のデータを保持する必要がない場合は、メールボックスを削除する前に、アイテム保持ポリシーからそのユーザー アカウントを除外します。

チャット メッセージとチャネル メッセージのアイテム保持ポリシーが構成されると、Exchange サービスのタイマー ジョブが、これらの Teams メッセージが保存されている隠しフォルダ内のアイテムを定期的に評価します。 このタイマー ジョブを実行するには、最大 7 日間かかります。 アイテムの保持期間が満了すると、これらのアイテムは SubstrateHolds フォルダに移動されます。これは、すべてのユーザーまたはグループのメールボックスにある別の隠しフォルダで、「論理的に削除済み」アイテムが完全に削除される前に保存するためのものです。

アイテム保持ポリシーがチャット メッセージとチャネル メッセージに対して構成された後のコンテンツのパスは、アイテム保持ポリシーの保持後に削除、保持のみ、あるいは削除のみのどれであるかによって異なります。

アイテム保持ポリシーが保持されてから削除される場合

![Teams チャットとチャネル メッセージの保持フローの図](../media/teamsretentionlifecycle.png)

図内の 2 つのパスの場合:

1. **保持期間中にチャット メッセージまたはチャネル メッセージがユーザーによって編集または削除された場合**、元のメッセージは 21 日以内に SubstrateHolds フォルダーにコピー (編集の場合) または移動 (削除の場合) されてます。 メッセージは保存期間が終了するまで保存され、その後 24 時間以内に完全に削除されます。

2. **チャット メッセージまたはチャネル メッセージが削除されない場合**、および編集した後の現在のメッセージの場合は、保持期間満了後にメッセージは SubstructateHolds フォルダに移動されます。 このアクションを実行するには、有効期限の最大で 7 日かかります。 メッセージが SubstrateHolds フォルダにある場合は、24 時間以内に完全に削除されます。 

> [!NOTE]
> SubstrateHolds フォルダー内のメッセージは、電子情報開示ツールで検索できます。 メッセージは SubstituteHolds フォルダ内から完全に削除されるまで、メッセージは電子情報開示ツールで検索できます。

アイテム保持ポリシーが保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。

### <a name="content-paths-for-retain-only-retention-policy"></a>アイテム保持ポリシーが保持のみのコンテンツ パス

1. **チャット メッセージまたはチャネルのメッセージが編集または削除された場合**、元のメッセージのコピーは 21 日以内に SubstrateHolds フォルダに作成され、保持期間が満了するまでそこに保持されます。 メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。

2. **アイテムが変更または削除されていない場合**、および保持期間中に編集した後の現在のメッセージの場合は、保持期間の前後には何も起こらず、メッセージは元の場所に残ります。

### <a name="content-paths-for-delete-only-retention-policy"></a>アイテム保持ポリシーが削除のみのコンテンツ パス

1. 保持期間中に **メッセージが削除されない場合**、保持期間の終了時にメッセージは SubstrateHolds フォルダーに移動されます。 このアクションを実行するには、有効期限の最大で 7 日かかります。 メッセージは、SubstrateHolds フォルダから 24 時間以内に完全に削除されます。

2. 期間中にユーザーがアイテムを **削除した場合**、アイテムは 21 日以内に SubstrateHolds フォルダーに移動され、24 時間以内に完全に削除されます。


## <a name="skype-for-business-and-teams-interop-chats"></a>Skype for Business および Teams の相互運用チャット

Skype for Business のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。 Teams のアイテム保持ポリシーは、これらのメッセージに Teams のスレッドから適用されます。 

ただし、Skype for Business に対して会話履歴がオンになっていて、Skype for Business のクライアント側からその履歴がメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。 このコンテンツには、Skype for Business に構成されているアイテム保持ポリシーを使用します。

## <a name="meetings-and-external-users"></a>会議と外部ユーザー

チャネル会議メッセージはチャネル メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャネル メッセージ** の場所を選択します。

緊急会議のメッセージも予定された会議のメッセージもグループ チャット メッセージと同じ方法で保存されるため、このデータについては、アイテム保持ポリシーを構成するときに、**Teams チャット** の場所を選択します。

組織が主催する会議に外部ユーザーが含まれる場合:

- 外部ユーザーがテナントのゲスト アカウントを使用して参加する場合、このユーザーには、組織の Teams のアイテム保持ポリシーの対象となるシャドウ メールボックスがあります。 会議からのメッセージはすべて、ユーザーのメールボックスとシャドウ メールボックスの両方に保存されます。 

- 外部ユーザーが別の Microsoft 365 組織のアカウントを使用して参加した場合、そのユーザーのメッセージは別のテナントのメールボックスに保存されるため、削除できません。 ただし、同じ会議の場合、アイテム保持ポリシーによりユーザーのメッセージが削除される可能性があります。

## <a name="when-a-user-leaves-the-organization"></a>ユーザーが組織を離れる場合 

Exchange Online のメールボックスを持っているユーザーが組織を離れ、そのユーザーの Microsoft 365 アカウントが削除された場合、保持の対象となるチャット メッセージは、非アクティブなメールボックスに保存されます。 チャット メッセージは、引き続きメールボックスが非アクティブになる前にユーザーに配置されたアイテム保持ポリシーの適用対象となり、電子情報開示の検索が可能です。 詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。 

ユーザーが Teams にファイルを保存している場合は、SharePoint と OneDrive の[同等のセクション](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)を参照してください。

## <a name="limitations"></a>制限事項

Teams の保持機能の最適化に継続的に取り組んでいます。 それまでの間、Teams のチャネル メッセージとチャットで保持を使用する場合は、次の制限事項に注意する必要があります。

- **Outlook での誤った表示の問題**。 Skype または Teams の場所用にアイテム保持ポリシーを作成する場合、ユーザーが Outlook デスクトップ クライアントでメールボックス フォルダーのプロパティを表示すると、これらのポリシーの 1 つが既定のフォルダーポリシーとして表示されます。 これは、Outlook の誤表示の問題であり、[既知の問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)です。 既定のフォルダー ポリシーとして表示されるのは、フォルダーに適用されるメールボックス保持ポリシーです。 Skype または Teams の保持ポリシーは、ユーザーのメールボックスには適用されません。

- **構成の問題**: 
    - **[Teams のチャネル メッセージ]** の場所にある **[チームの選択]** を選択した場合、チームではない Microsoft 365 グループが表示される場合があります。 これらのグループは選択しないでください。
    
    - **[Teams のチャット]** の場所にある **[ユーザーの選択]** を選択した場合、ゲストや、メールボックスのユーザーではないユーザーが表示される場合があります。 アイテム保持ポリシーはこれらのユーザー向けに設計されていないため、選択しないでください。

## <a name="configuration-guidance"></a>構成ガイダンス

Microsoft 365 で保持を構成するのが初めての場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。

Teams 用のアイテム保持ポリシーを構成する準備ができた場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。
