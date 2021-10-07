---
title: チームでゲストと共同作業する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkTEAMS
ms.localizationpriority: high
f1.keywords: NOCSH
recommendations: false
description: Teams のゲストとのタスク、会話、ドキュメントの共同作業を行うためチームをセットアップするのに必要な Microsoft 365 の構成手順について説明します。
ms.openlocfilehash: 3c5d5689f676e6fecc6c0251df6ee90f54398238
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169385"
---
# <a name="collaborate-with-guests-in-a-team"></a>チームでゲストと共同作業する

ドキュメント、タスク、会話全体でゲストと共同作業する必要がある場合は、Microsoft Teams の使用をお勧めします。 Teams は、Office と SharePoint で利用可能なすべての共同作業の機能を、常設チャットと、カスタマイズ可能で拡張可能な共同作業のツールのセットを使用して、統合されたユーザー操作環境で提供します。

この記事では、ゲストとの共同作業のためチームをセットアップするのに必要な Microsoft 365 の構成手順について説明します。 ゲスト アクセスを構成したら、「[Teams でゲストをチームに追加する](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)」の手順で、ゲストをチームに招待できます。

## <a name="video-demonstration"></a>ビデオ デモンストレーション

このビデオは、このドキュメントで説明されている構成手順を示しています。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部コラボレーションの設定

Microsoft 365 での共有は、[Azure Active Directory における B2B 外部コラボレーションの設定](/azure/active-directory/external-identities/delegate-invitations) によって最高レベルで管理されます。 Azure AD でゲストの共有が無効になっているか、制限されている場合、この設定により、Microsoft 365 で構成した共有設定が上書きされます。

B2B 外部コラボレーションの設定をチェックして、ゲストとの共有がブロックされていないことを確認します。

![Azure Active Directory における組織関係の設定ページのスクリーンショット。](../media/azure-ad-organizational-relationships-settings.png)

外部コラボレーションを設定するには

1. [https://aad.portal.azure.com](https://aad.portal.azure.com) で Azure Active Directory にログインします。
2. 左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。
3. **[外部 ID]** をクリックします。
4. **[開始]** 画面で、左側のナビゲーション ウィンドウで **[外部コラボレーション設定]** をクリックします。
5. **[メンバー ユーザーおよび特定の管理者の役割に割り当てられたユーザーが、メンバー権限を持つゲストを含むゲスト ユーザーを招待できる]** が選択されていることを確認します。
6. 変更を加えた場合は、**[保存]** をクリックします。

**[共同作業の制限]** セクションの設定に注意してください。 共同作業するゲストのドメインがブロックされていないことを確認します。

複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスするゲストの機能を制限することをお勧めします。 これにより、他に誰がディレクトリ内のゲストであるかを確認できなくなります。 これを行うには、**[ゲスト ユーザーのアクセス制限]** で、**[ゲスト ユーザーはディレクトリ オブジェクト設定のプロパティとメンバーシップに制限付きアクセス権が付与されている]** または **[ゲスト ユーザーのアクセスは自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限されている]** を選択します。

## <a name="teams-guest-access-settings"></a>Teams のゲスト アクセスの設定

Teams には、ゲスト アクセス用のマスター オン/オフ スイッチと、ゲストがチームで実行できる操作を制御するために利用できるさまざまな設定があります。 Teams でゲスト アクセスを機能させるには、マスター スイッチである **[Teams でゲスト アクセスを許可する]** を **[オン]** にする必要があります。

Teams でゲスト アクセスが有効になっていることを確認し、ビジネス ニーズに応じてゲスト設定を調整します。これらの設定はすべてのチームに影響することに注意してください。

![Teams ゲスト アクセスのトグルのスクリーンショット。](../media/teams-guest-access-toggle-on.png)

Teams ゲスト アクセスの設定を行うには

1. [https://admin.microsoft.com](https://admin.microsoft.com) で、Microsoft 365 管理センターにログインします。
2. 左側のナビゲーション ウィンドウで [**すべて表示**] をクリックします。
3. [**管理センター**] で、[**Teams**] をクリックします。
4. Teams 管理センターの左側のナビゲーション ウィンドウで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**[ゲスト アクセス]**</a> を選択します。
5. [**Teams でのゲスト アクセスを許可する**] が [**オン**] に設定されていることを確認します。
6. 追加のゲスト設定に必要な変更を加えて、[**保存**] をクリックします。

Teams のゲスト アクセスがオンになっている場合、機密度ラベルを使用して、個別のチームやそのチームに関連する SharePoint サイトへのゲスト アクセスを制御することができます。 詳細については、「[機密ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」 をご覧ください。

> [!NOTE]
> Teams のゲスト設定をオンにした後、有効になるまでには、最大で 24 時間かかる場合があります。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 グループのゲスト設定

Teams は、チームのメンバーシップに Microsoft 365 グループを使用します。Teams でゲスト アクセスを機能させるには、Microsoft 365 グループのゲスト設定をオンにする必要があります。

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット。](../media/office-365-groups-guest-settings.png)

Microsoft 365 グループのゲスト設定を行うには

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**[設定]** を展開します。
2. **[組織の設定]** をクリックします。
3. 一覧で、**[Microsoft 365 グループ]** をクリックします。
4. **[組織外のグループ所有者に Microsoft 365 グループへのアクセスを許可する]** と **[グループ メンバーにグループ コンテンツへのアクセスを許可する]** チェック ボックスが両方ともオンになっていることを確認します。
5. 変更を加えた場合は、**[変更の保存]** をクリックします。


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織レベルの共有設定

ファイル、フォルダー、リストなどの Teams コンテンツはすべて SharePoint に保存されます。 ゲストが Teams でこれらのアイテムにアクセスできるようにするには、SharePoint 組織レベルの共有設定でゲストとの共有が許可されている必要があります。

組織レベルの設定により、チームに関連付けられたサイトを含む、個々のサイトで使用できる設定が決まります。 サイトの設定は、組織レベルの設定よりも制限を緩和することはできません。

認証されていないユーザーとのファイルとフォルダーの共有を許可する場合は、**[全員]** を選択します。 すべてのゲストが認証する必要があることを確認する場合は、**[新規および既存のゲスト]** を選択します。 組織内の任意のサイトで必要となる最も制限が少ない設定を選択します。

![SharePoint 組織レベルの共有設定のスクリーンショット。](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 組織レベルの共有設定を設定するには

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の左側のナビゲーション ウィンドウの **[管理センター]** で、**[SharePoint]** をクリックします。
2. SharePoint 管理センターの左側のナビゲーション ウィンドウで、**[ポリシー]** を展開し、**[共有]** をクリックします。
3. SharePoint の外部共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。
4. 変更を加えた場合は、**[保存]** をクリックします。


## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織レベルの既定のリンク設定

既定のファイルとフォルダーのリンク設定により、ファイルまたはフォルダーを共有するときに既定でユーザーに表示されるリンク オプションが決まります。 ユーザーは、必要に応じて、共有する前に他のオプションのいずれかにリンクの種類を変更できます。

この設定は、組織内のすべてのチームおよび SharePoint サイトに影響することに注意してください。

ユーザーがファイルやフォルダーを共有する場合に既定で選択されるリンクの種類を次から 1 つ選択してください。

- **リンクを持つすべてのユーザー** - ファイルやフォルダの共有をあまり認証しないことが予想される場合は、このオプションを選択します。 *全員* リンクを許可したいが、誤って認証されない共有が心配な場合は、他のオプションのいずれかを既定として検討してください。 このリンクの種類は、**全員** 共有を有効にしている場合にのみ使用できます。
- **組織内のユーザーのみ** - ほとんどのファイルとフォルダーの共有が組織内のユーザーと行われることが予想される場合は、このオプションを選択します。
- **特定のユーザー** - ゲストと多くのファイルやフォルダーを共有することが予想される場合は、このオプションを検討してください。 この種類のリンクはゲストと連携し、ゲストに認証を要求します。
 
![SharePoint 組織レベルのファイルとフォルダーの共有設定のスクリーンショット。](../media/sharepoint-organization-files-folders-sharing-settings.png)


SharePoint 組織レベルの既定のリンク設定を設定するには

1. SharePoint 管理センターの共有ページに移動します。
2. **ファイルとフォルダーのリンク** で、使用する既定の共有リンクを選択します。
3. 変更を加えた場合は、**[保存]** をクリックします。

## <a name="create-a-team"></a>チームの作成

次の手順は、ゲストとの共同作業に使用する予定のチームを作成することです。

チームを作成するには
1. Teams の **[Teams]** タブで、左側のウィンドウの下部にある **[チームに参加またはチームを作成]** をクリックします。
2. **[チームを作成]** をクリックします。
3. **[初めからチームを作成する]** をクリックします。
4. **[プライベート]** または **[パブリック]** を選択します。
5. チームの名前と説明を入力し、**[作成]** をクリックします。
6. **[スキップ]** をクリックします。

後でユーザーを招待します。次に、チームに関連付けられている SharePoint サイトのサイトレベルの共有設定を確認することが重要です。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint のサイト レベル共有設定のスクリーンショット

サイトレベルの共有設定をチェックして、このチームに必要な種類のアクセスが許可されていることを確認します。 たとえば、組織レベルの設定を **全員** に設定したが、すべてのゲストにこのチームの認証を許可する場合は、サイトレベルの共有設定が **新規および既存のゲスト** に設定されていることを確認してください。

![SharePoint サイトの外部共有設定のスクリーンショット。](../media/sharepoint-site-external-sharing-settings.png)

サイトレベルの共有設定を設定するには
1. SharePoint 管理センターの左側のナビゲーション ウィンドウで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。
2. 作成したチームのサイトを選択します。
3. [...] をクリックして、**共有** を選択します。
4. 共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。
5. 変更を加えた場合は、**[保存]** をクリックします。

## <a name="invite-users"></a>ユーザーを招待する

ゲストの共有設定が構成されたので、チームへの内部ユーザーとゲストの追加を開始できます。 

内部ユーザーをチームに招待するには
1. チームで、**[その他のオプション]** （**\*\*\***） をクリックし、**[メンバーの追加]** をクリックします。
2. 招待したい人の名前を入力します。
3. **[追加]** をクリックして、**[閉じる]** をクリックします。

ゲストをチームに招待するには
1. チームで、**[その他のオプション]** （**\*\*\***） をクリックし、**[メンバーの追加]** をクリックします。
2. 招待したいゲストのメール アドレスを入力します。
3. **[ゲスト情報の編集]** をクリックします。
4. ゲストのフル ネームを入力し、チェック マークをクリックします。
5. **[追加]** をクリックして、**[閉じる]** をクリックします。

> [!NOTE]
> 職場または学校アカウントを持つゲストは、ユーザー プリンシパル名 (UPN) (adele@contoso.com など) を使用してのみ招待できます。 EAS ID またはその他のメール形式を使用したゲストの招待はサポートされていません。

## <a name="see-also"></a>関連項目

[認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)

[ゲストと共有するときにファイルの偶発的な公開を制限する](share-limit-accidental-exposure.md)

[セキュリティで保護されたゲスト共有の環境を作成する](create-secure-guest-sharing-environment.md)

[管理されたゲストで B2B エクストラネットを作成する](b2b-extranet.md)

[SharePoint および OneDrive の Azure AD B2B との統合](/sharepoint/sharepoint-azureb2b-integration-preview)

[共有オプションは、SharePoint または OneDrive から共有するときに淡色表示されます。](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
