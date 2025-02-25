---
title: 機密データに対する保護機能を使用してチームを構成する
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
- admindeeplinkSPO
recommendations: false
description: 機密データに対する保護機能を使用してチームを展開する方法について説明します。
ms.openlocfilehash: 2ea13fbf8a677ba4a04efbd0b2a6fdfed7d80644
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941283"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>機密データに対する保護機能を使用してチームを構成する

この記事では、機密レベルの保護機能を使用してチームをセットアップする方法について説明します。 この記事の手順を実行する前に、「[基本保護機能を使用してチームを展開する](configure-teams-baseline-protection.md)」の手順を完了していることを確認してください。 機密層は、基本層の上に次のような追加保護機能を実現します。

- ゲスト共有を有効または無効にし、管理されていないデバイスの SharePoint コンテンツへのアクセスを Web のみに制限するチームの秘密度ラベル。このラベルは、ファイルの分類にも使用できます。
- より制限の厳しい既定の共有リンクの種類
- チーム所有者のみがプライベート チャネルを作成できます。

## <a name="video-demonstration"></a>ビデオ デモンストレーション

この記事で説明されている手続きのチュートリアルに関するビデオを見ます。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a>ゲスト共有

会社の性質に応じて、機密データを含むチームのゲスト共有を有効または無効にする必要がある場合があります。 チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にすることをお勧めします。 Microsoft 365 には、セキュリティとコンプライアンスのためのさまざまな機能が含まれており、機密コンテンツを安全に共有できます。 通常、組織外のユーザーに直接コンテンツを電子メールで送信するよりも、セキュリティが強化されています。

ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。

- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](./share-limit-accidental-exposure.md)
- [セキュリティで保護されたゲスト共有環境を作成する](./create-secure-guest-sharing-environment.md)

ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。

## <a name="sensitivity-labels"></a>秘密度ラベル

機密保護レベルについては、秘密度ラベルを使用してチームを分類します。 このラベルは、このチームまたは他のチームの個別のファイル、または SharePoint や OneDrive などのその他の場所にあるファイルを分類するために使用することもできます。 

最初の手順では、Teams の秘密度ラベルを有効にする必要があります。 詳細は、「[秘密度ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」をご覧ください。

組織に既に秘密度ラベルを展開している場合は、ラベル戦略全体にこのラベルがどのように適合しているかを検討してください。 組織のニーズを満たす必要がある場合、名前または設定を変更できます。

Teams の秘密度ラベルを有効にしたら、次の手順ではラベルを作成します。

秘密度ラベルを作成する
1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com) を開きます。
2. **[ソリューション]** で、**[情報保護]** をクリックします。
3. **[ラベルの作成]** をクリックします。
4. ラベルに名前を付けます。**[Sensitive]** をお勧めしますが、それが既に使用されている場合は別の名前を選択することもできます。
5. 表示名と説明を追加し、**[次へ]** をクリックします。
6. **Define the scope for this label** (このラベルの範囲の定義) ページで、**[Files & emails]** (ファイルとメール) と **[Groups & sites]** (グループとサイト) を選択し、**[次へ]** をクリックします。
7. **[Choose protection settings for files and emails]** (ファイルやメールの保護の設定の選択) ページで、**[次へ]** をクリックします。
8. *[ファイルやメールの自動ラベル付け]* ページで、**[次へ]** をクリックします。
9. **[Define protection settings for groups and sites]** (グループやサイトの保護の設定の定義) ページで、**[プライバシーと外部ユーザー アクセス設定]** と **[デバイス アクセスと外部共有設定]** を選択し、**[次へ]** をクリックします。
10. **[Define privacy and external user access settings]** (プライバシーと外部ユーザー アクセス設定の定義) ページの **[プライバシー]** で、**[プライベート]** オプションを選択します。
11. ゲスト アクセスを許可する場合は、**[外部ユーザーのアクセス]** で、**[Let Microsoft 365 Group owners add people outside your organization to the group as guests]** (Microsoft 365 グループ所有者が組織外のユーザーをグループに追加できるようにする) を選択します。
12. **[次へ]** をクリックします。
13. **[Define external sharing and device access settings]** (外部共有とデバイス アクセス設定の定義) ページで、**[Control external sharing from labeled SharePoint sites]** (ラベル付き SharePoint サイトからの外部共有の制御) を選択します。
14. **[Content can be shared with]** (コンテンツの共有先) で、ゲスト アクセスを許可する場合には **[新規および既存のゲスト]** を選択し、許可しない場合には **[組織内のユーザーのみ]** を選択します。
15. **[非管理対象デバイスからのアクセス]** で、**[制限付きの、Web のみのアクセスを許可する]** を選びます。
16. **[次へ]** をクリックします。
17. **[Auto-labeling for database columns]** (データベースの列の自動ラベル付け) ページで、**[次へ]** をクリックします。
18. **[ラベルの作成]** をクリックし、**[完了]** をクリックします。

ラベルを作成したら、それを使用するユーザーに発行する必要があります。 機密保護のために、すべてのユーザーがラベルを使用できるようにします。 **[Information protection]** ページの **[ラベルポリシー]** タブで、ラベルを Microsoft Purview コンプライアンス ポリシーに発行します。 すべてのユーザーに適用する既存のポリシーがある場合は、そのポリシーにこのラベルを追加します。 新しいポリシーを作成する必要がある場合は、「[ラベル ポリシーを作成して秘密度ラベルを発行する](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)」をご覧ください。

## <a name="create-a-team"></a>チームを作成する

機密のシナリオの詳細な構成は、チームに関連付けられている SharePoint サイトで行います。次の手順では、チームを作成します。

機密情報のチームを作成するには
1. Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。
2. **[チームの作成]** (最初のカード、左上隅) をクリックします。
3. **[初めからチームを作成する]** を選びます。
4. **[秘密度]** リストで、作成した **秘密度** ラベルを選びます。
5. **[プライバシー]** で、**[プライベート]** をクリックします。
6. チームの名前を入力し、**[作成]** をクリックします。
7. チームにユーザーを追加し、**[閉じる]** をクリックします。

## <a name="private-channel-settings"></a>プライベート チャネルの設定

この層では、プライベート チャネルの作成権限をチームの所有者に制限します。

プライベート チャネルの作成を制限するには
1. チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。
2. **[設定]** タブで、**[メンバーのアクセス許可]** を展開します。
3. **[プライベート チャネルを作成する]** チェック ボックスをオフにします。

[チーム ポリシー](/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。

## <a name="shared-channel-settings"></a>共有チャネルの設定

[共有チャネル](/MicrosoftTeams/shared-channels) にはチーム レベルの設定がありません。Teams 管理センターと Azure AD で構成した共有チャネル設定は、秘密度に関係なくすべてのチームに適用されます。

## <a name="sharepoint-settings"></a>SharePoint の設定

秘密度ラベルを使用して新しいチームを作成するたびに、SharePoint で次の 2 つの手順を実行します。

- SharePoint 管理センターでサイトのゲスト共有設定を更新して、*特定のユーザー* に対して既定の共有リンクを更新します。
- サイト自体の共有設定を更新し、メンバーがサイトを共有できないようにします。

### <a name="site-default-sharing-link-settings"></a>サイトの既定の共有リンク設定

サイトの既定の共有リンクの種類を更新するには

1. SharePoint 管理センターを開き、**[サイト]** で、<a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**[アクティブなサイト]**</a> を選択します。
1. チームに関連付けられているサイトを選択します。
1. **[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。
1. [既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[特定のユーザー (ユーザーが指定したユーザー人物のみ)]** を選びます。
1. **[保存]** を選択します。

チーム作成プロセスの一環としてスクリプトを実行する場合は、`-DefaultSharingLinkType Direct` パラメーターで [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) を使用して、既定の共有リンクを *特定のユーザー* に変更することができます。

チームにプライベート チャネルまたは共有チャネルを追加する場合、それぞれ既定の共有設定を使用して新しい SharePoint サイトが作成されることに注意してください。 チームに関連付けられているサイトを選択すると、SharePoint 管理センターで更新できます。

### <a name="site-sharing-settings"></a>サイト共有設定

SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。 これは、チームで作成された SharePoint サイトに対してのみ必要です。 プライベート チャネルまたは共有チャネルの一部として作成された追加サイトは、チームまたはチャネルの外部で共有することはできません。

所有者のみのサイト共有を構成する
1. Teams で、更新するチームの **[全般]** タブに移動します。
2. チームのツール バーで、**[ファイル]** をクリックします。
3. 省略記号をクリックし、**[SharePoint で開く]** をクリックします。
4. 基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。
5. **[サイトの権限]** ウィンドウで、**[サイトの共有]** の **[メンバーが共有する方法を変更]** をクリックします。
6. [**共有アクセス許可**] で、[**サイトの所有者とメンバー、および編集権限を持つユーザーはファイルとフォルダを共有できますが、サイトを共有できるのはサイト所有者だけです**] を選択し、[**保存**] をクリックします。


## <a name="related-topics"></a>関連項目

[秘密度ラベルとそのポリシーを作成して構成する](../compliance/create-sensitivity-labels.md)
