---
title: Microsoft 365の外部コラボレーション オプションの概要
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- SPO_Content
ms.localizationpriority: medium
description: 組織外のユーザーが、会議、ゲスト共有、チャット、コラボレーションのためにMicrosoft 365 サブスクリプションにアクセスする方法について説明します。
ms.openlocfilehash: 988a1ecae8a060cae2334f97ef19bc90ba2be6bc
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64836448"
---
# <a name="overview-of-external-collaboration-options-in-microsoft-365"></a>Microsoft 365の外部コラボレーション オプションの概要

Microsoft 365を使用すると、ユーザーはさまざまな方法で組織外のユーザーと共同作業できます。 ユーザーは、ファイルの共有、チームへのゲストの招待、外部参加者との会議の開催、他の組織のユーザーとのチャットを行うことができます。 この記事では、使用可能な外部コラボレーション オプションと、それぞれを構成するために必要なコンテンツへのリンクについて説明します。

次の表は、組織外のユーザーがMicrosoft 365 リソースにアクセスする主な方法を示しています。

|アクティビティ|アカウントの種類|既定の設定|
|:-------|:-----------|:--------------|
|認証されたファイルとフォルダーの共有|ゲスト アカウント|Enabled|
|サイトの共有|ゲスト アカウント|Enabled|
|チーム共有|ゲスト アカウント|Enabled|
|Teamsの共有チャネル|既存のMicrosoft 365外部アカウント|無効|
|外部チャットと会議|既存のMicrosoft 365外部アカウント|Enabled|
|匿名会議への参加|なし|Enabled|
|認証されていないファイルとフォルダーの共有|なし|Enabled|

組織外のユーザーは、組織内のユーザーがこれらのアクティビティのいずれかを開始しない限り、アクセス権を持ちません。 組織内でそのアクティビティを許可しない場合は、これらの設定のいずれかを無効にできます。

## <a name="document-site-and-team-sharing-with-guest-accounts"></a>ゲスト アカウントを使用したドキュメント、サイト、チーム共有

ドキュメント、サイト、チームを組織外のユーザーと共有すると、 *ゲスト アカウントが使用されます*。 ゲスト アカウントは、[Azure AD B2B コラボレーション](/azure/active-directory/external-identities/what-is-b2b)によって管理されるAzure Active Directoryのアカウントの一種です。 電子メール アドレスを持つすべてのユーザーと組織内のリソースを共有するために使用できます。 ゲスト アカウントは、組織内のユーザーを管理するのと同じ方法で管理できます。 ゲストは、コラボレーションのほとんどの機能に対してライセンスを必要としません。 

ゲストは、特定のリソースと共有するリソースにのみアクセスできます。

ゲストが別の組織の職場または学校アカウント、または Microsoft アカウントを持っている場合は、通常のユーザー名とパスワードを使用してログインできます。 Gmail アカウントなど、別の種類のアカウントを持っている場合は、メール アドレスに送信されるワンタイム パスコードを使用してログインできます。

ゲストの場合は、次のことができます。

- グループ、チーム、または組織内のユーザーと共同作業できるSharePoint サイトに Microsoft 365招待します。
- 1 つのファイルまたはフォルダーを共有し、与えたアクセス許可に応じて表示または編集できます。

Microsoft 365のゲストとのコラボレーションを計画する方法については、次の参考資料を参照してください。

- [外部コラボレーションを計画する](/microsoft-365/solutions/plan-external-collaboration)
- [Microsoft Teamsでセキュリティで保護されたファイル共有とコラボレーションを設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

ゲストとのコラボレーション用にMicrosoft 365を設定する方法については、次のリファレンスを参照してください。

- [ゲストと共同でドキュメントの作業をする](/microsoft-365/solutions/collaborate-on-documents)
- [サイトでゲストと共同で作業する](/microsoft-365/solutions/collaborate-in-site)
- [チームでゲストと共同で作業する](/microsoft-365/solutions/collaborate-as-team)
 
## <a name="shared-channels"></a>共有チャネル

共有チャネルは、他のMicrosoft 365組織のユーザーを含め、チーム外のユーザーと共有できるTeams チャネルの一種です。 Teamsでは共有チャネルが既定で有効になっていますが、共有チャネルとの外部コラボレーションは既定で無効になっています。 共有チャネルとの外部コラボレーションでは[、Azure AD B2B 直接接続](/azure/active-directory/external-identities/b2b-direct-connect-overview)を使用します。これにより、ゲスト アカウントを作成しなくても、他のMicrosoft 365組織のユーザーをTeams チャネルに追加できます。

共有チャネルは、外部参加者がTeams デスクトップ クライアントで組織を切り替えたり、組織にログインしたりする必要がないという点で、ゲスト アカウントよりも特に利点があります。 組織にログインしたまま、チャネルに直接アクセスできます。

組織外のユーザーとチャネルを共有するには、組織と外部組織の両方が[、Azure AD B2B Direct Connect](/azure/active-directory/external-identities/b2b-direct-connect-overview)で組織関係を構成する必要があります。

共有チャネルを使用して外部コラボレーションのMicrosoft 365を設定する方法については、次のリファレンスを参照してください。

- [外部コラボレーションを計画する](/microsoft-365/solutions/plan-external-collaboration)
- [Microsoft Teamsの共有チャネル](/MicrosoftTeams/shared-channels)
- [チャネルで外部の参加者と共同作業する](/microsoft-365/solutions/collaborate-teams-direct-connect)

## <a name="external-chat-and-meetings"></a>外部チャットと会議

組織内のユーザーは、チャット、会議へのユーザーの追加、および外部Microsoft 365組織のユーザーとのTeamsでの電話会議またはビデオ会議の使用を行うことができます。 既定では、組織内のユーザーは、このような方法で他のすべてのMicrosoft 365 ドメインと通信できます。 他の組織のユーザーは、ユーザーの電子メール アドレスを知っている場合、これらの方法でユーザーと通信できます。 機能を無効にする場合は、特定のドメインを許可またはブロックしたり、すべてのドメインをブロックしたりできます。

また、組織内のユーザーが、組織で管理されていないTeams アカウントを使用している組織外のユーザーや、Skype for Business (オンラインおよびオンプレミス)、Skype ユーザーとの通信を許可することもできます。

ゲスト アカウントは、外部チャットや会議の一部として使用されません。 外部参加者は組織またはSkypeにサインインしたままで、組織内のユーザーと直接通信できます。 チームやチャネルにはアクセスできません。

外部チャットと会議のMicrosoft 365を設定する方法については、次のリファレンスを参照してください。

- [ゲスト アクセスと外部アクセスを使用して、組織外のユーザーと共同作業する](/microsoftteams/communicate-with-users-from-other-organizations)
- [Microsoft Teamsで外部アクセスを管理します](/microsoftteams/manage-external-access)。

## <a name="anonymous-meeting-join"></a>匿名会議への参加 

組織外のユーザーは、次の方法で会議に参加できます。

- ゲスト アカウントを使用して組織にログインしている場合は、会議にゲストとして参加します。
- 職場または学校アカウントを使用して別の組織にログインしていて、組織が外部アクセスを有効にしている場合は、外部参加者として会議に参加します。
- ゲストまたは外部の参加者でない場合は、匿名で会議に参加する必要があります。

組織で匿名参加設定が有効になっている場合、匿名ユーザーは、自分と共有されている会議リンク (会議出席依頼のリンクなど) を使用してのみ会議に参加できます。 匿名で会議に参加するときに、選択した表示名を入力するように求められます。 ロビーの設定によっては、匿名ユーザーが会議に自動的に参加許可を受け入れるか、会議の開催者 (または発表者ロールを持つ会議参加者) が会議へのアクセスを許可または拒否できるロビーに追加される場合があります。 

会議の前、中、または後に匿名ユーザーの ID を確認することはできません。 

匿名ユーザーが組織レベルで会議に参加する機能を制御できます。 組織で有効になっている場合、会議の開催者は会議ポリシー設定を使用して匿名参加を制御できます。

会議の匿名参加を構成する方法については、「[Microsoft Teamsでの会議設定の管理](/microsoftteams/meeting-settings-in-teams)」を参照してください。

## <a name="unauthenticated-file-and-folder-access"></a>認証されていないファイルとフォルダーへのアクセス

Microsoft 365では、Teams、SharePoint、OneDrive内のファイルとフォルダーは、認証されていないリンクまたは *すべての* リンクを使用して共有できます。 すべてのリンクは、そのリンクを持つすべてのユーザーに共有アイテムへのアクセス権を付与します。 すべてのリンクを他のユーザーと共有して、それらのユーザーにファイルまたはフォルダーへのアクセス権を付与できます。

すべてのユーザー リンクを使用するユーザーは認証を受ける必要がなく、リンクを使用するユーザーのアクセスを監査することはできません。 ファイルとフォルダーの所有者は、リンクを削除することで、いつでもアクセスを取り消すことができます。

Teams共有チャネル サイト内のファイルでは、すべてのユーザーリンクは使用できません。

匿名ファイルとフォルダー共有の操作の詳細については、次のリファレンスを参照してください。

- [共有設定を管理する](/sharepoint/turn-external-sharing-on-or-off)
- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](/microsoft-365/solutions/best-practices-anonymous-sharing)

## <a name="related-topics"></a>関連項目

[SharePointを利用したMicrosoft 365でのファイル コラボレーションの概要](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 による SharePoint のファイルの共同作業](/sharepoint/deploy-file-collaboration)

[ゲスト アクセスと外部アクセスを使用して、組織外のユーザーと共同作業する](/microsoftteams/communicate-with-users-from-other-organizations)

[ゲスト共有を特定の組織に制限する](/microsoft-365/solutions/limit-guest-sharing-to-specific-organization)

[ユーザーがゲスト アカウントを持つ組織を制限する](/microsoft-365/solutions/limit-organizations-where-users-have-guest-accounts)