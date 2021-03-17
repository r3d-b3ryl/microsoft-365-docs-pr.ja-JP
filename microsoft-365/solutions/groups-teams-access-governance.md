---
title: Microsoft 365 グループ、Teams、および SharePoint でのアクセスの管理
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、および SharePoint でのアクセスの管理について説明します。
ms.openlocfilehash: 24a8a43f05206c9f1c0cd07aef480b330d968935
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838711"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、および SharePoint でのアクセスの管理

ユーザーがグループ、チーム、および SharePoint のリソースにアクセスする方法を管理できる多くのコントロールがあります。 これらのオプションを確認し、ビジネス ニーズ、データの感度、ユーザーが共同作業に必要なユーザーの範囲にマップする方法を検討します。

次の表に、Microsoft 365 で使用できるアクセス制御のクイック リファレンスを示します。 詳細については、次のセクションで説明します。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|メンバーシップ|||
||プライベート チームの検出|[Microsoft Teams でプライベート チームの検出を管理する](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||ルールに基づく動的グループ メンバーシップ|[Azure Active Directory で動的グループを作成または更新する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||ファイル、フォルダー、サイトを共有できるユーザーを制御します。|[アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件付きアクセス|||
||多要素認証|[Azure AD 多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||グループ、チーム、またはサイトの感度に基づいてデバイス アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||管理されていないデバイスのサイト アクセスを制限します。|[管理されていないデバイスからの SharePoint アクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||場所に基づいてサイト アクセスを制御する|[ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|ゲスト アクセス|||
||指定したドメインからの SharePoint 共有を許可またはブロックします。|[ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||指定したドメインからチームまたはグループのメンバーシップを許可またはブロックします。|[特定の組織からの B2B ユーザーへの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||匿名共有を防止します。|[[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||匿名アクセス リンクのアクセス許可を制御します。|[[ユーザー] リンクのリンクのアクセス許可を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||匿名共有リンクの有効期限を制御します。|[[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||既定では、ユーザーに表示される共有リンクの種類を制御します。|[サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||外部共有を特定のユーザーに制限します。|[外部共有を指定したセキュリティ グループに制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||情報の感度に基づいて、グループ、チーム、またはサイトへのゲスト アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||共有オプションをオフにします。|[Microsoft 365 の共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|ユーザーの管理|||
||チームとグループのメンバーシップを定期的に確認します。|[Azure ADレビューとは?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||グループとチームへのアクセス管理を自動化します。|[Azure のライセンスADとは?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Teams でプライベート チャネルを作成するユーザーを許可またはブロックします。|[Microsoft Teams のプライベート チャネルのライフ サイクルを管理する](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>メンバーシップ

チームとグループのメンバーシップは、所有者によって制御されます。 メンバーは他のユーザーを招待できますが、招待は承認のために所有者に送信されます。 パブリック チームとグループは組織内の誰でも見つけられますが、プライベート チームとグループを検出できるかどうかを制御できます。

- [Microsoft Teams でプライベート チームの検出を管理する](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

グループまたはチームのメンバーシップは、部署などの一部の条件に基づいて動的に管理できます。 この場合、メンバーと所有者はチームにユーザーを招待できません。 動的グループは、Azure Active Directory で定義したメタデータを使用して、グループのメンバーを制御します。 使用しているメタデータが完全で、メタデータが正しくないと、ユーザーがグループから抜け出したり、正しくないユーザーが追加される可能性があります。

- [Azure Active Directory で動的グループを作成または更新する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint サイトは、グループまたはチーム のメンバーシップとは別に、所有者、メンバー、および訪問者を追加する機能を提供します。 要件に応じて、ユーザーをサイトに招待できるユーザーを制限できます。 また、特定のサイト内の情報の感度に応じて、ファイルとフォルダーを共有できるユーザーを制限することもできます。 これらの制限は、チーム、グループ、またはサイトの所有者によって構成されます。

- [アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件付きアクセス

Microsoft 365 では、組織内外の両方のユーザーに多要素認証を要求できます。 ユーザーに認証の第 2 の要素を求めるメッセージが表示される状況には、多くのオプションがあります。 組織に多要素認証を展開することを強くお勧めします。

- [Azure AD 多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

一部のグループやチームに機密情報がある場合は、グループまたはチームの機密ラベルに基づいてデバイス管理ポリシーを適用できます。 管理されていないデバイスからのアクセスを完全にブロックするか、制限付き Web アクセスのみを許可できます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

SharePoint では、指定したネットワークの場所からサイトへのアクセスを制限できます。

- [ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


追加情報:

- [条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune の概要](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [管理されていないデバイスからの SharePoint アクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>ゲスト アクセス

電子メール アドレスのドメインに基づいてゲストを制限できます。 SharePoint は、組織全体およびサイト固有のドメイン制限設定を提供します。 グループと Teams は、Azure のドメイン許可リストと拒否リストを使用AD。 望ましくない共有を避け、一貫性のあるユーザー エクスペリエンスを確保するために、両方の設定を必ず構成してください。

- [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [特定の組織からの B2B ユーザーへの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 では、すべての共有リンクを使用してファイルとフォルダーを匿名 *で* 共有できます。 *リンク* は誰でも転送可能で、リンクを持つユーザーは共有アイテムにアクセスできます。 データの感度に応じて、リンクを完全にオフにしたり、リンクのアクセス許可を読み取り専用に制限したり、そのリンクの有効期限を設定したりなど、すべてのユーザーのリンクの使用方法を管理する方法を検討してください。

- [[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [[ユーザー] リンクのリンクのアクセス許可を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

ファイルまたはフォルダーを共有する場合、ユーザーは複数のリンクの種類から選択できます。 不適切な共有が誤って発生するリスクを軽減するために、ユーザーが共有するときに表示される既定のリンクの種類を変更できます。 たとえば、匿名アクセスを許可する[すべてのユーザー] リンクから[組織内のユーザー] リンクに既定値を変更すると、機密情報の望ましくない外部共有のリスクが軽減されます。

- [サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

組織にゲストと共有する必要がある機密データがあるが、不適切な共有が懸念されている場合は、ファイルとフォルダーの外部共有を指定したセキュリティ グループのメンバーに制限できます。 この方法で、外部での共有を特定のユーザー グループに制限したり、セキュリティ グループに追加する前に、適切な外部共有に関するトレーニングをユーザーに要求することができます。

- [外部共有を指定したセキュリティ グループに制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

グループと Teams には、ゲスト アクセスを許可または拒否する組織レベルの設定があります。 [Microsoft PowerShell を使用](per-group-guest-access.md)して、特定のチームまたはグループへのゲスト アクセスを制限することができますが、これを行う際には、感度ラベルを使用することをお勧めします。 感度ラベルを使用すると、適用されたラベルに基づいてゲスト アクセスを自動的に許可または拒否できます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

グループやチームにゲストを頻繁に招待する環境では、定期的にスケジュールされたゲスト アクセス レビューの設定を検討してください。 所有者は、グループとチームのゲストを確認し、アクセスを承認または拒否するように求めるメッセージを表示できます。

- [ゲスト アクセス レビューを設定する](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 は、情報を共有するさまざまな方法を提供しています。 機密情報を持ち、共有方法を制限する場合は、共有を制限するためのオプションを確認します。

- [Microsoft 365 の共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

追加情報:

- [Microsoft 365 とセキュリティで保護された共同作業を設定する](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [セキュリティで保護されたゲスト共有環境を作成する](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [B2B の外部コラボレーションを有効にしてゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>ユーザーの管理

グループとチームが組織内で進化するにつれて、チームとグループのメンバーシップを定期的に確認する方法をお試しください。 これは、メンバーシップが変更されたチームやグループ、機密情報を含むチーム、またはゲストを含むグループに特に役立ちます。 これらのチームとグループのアクセス レビューを設定する方法を検討してください。

- [Azure ADレビューとは?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

多くの組織は、他の組織や主要ベンダーとビジネス パートナーシップを結び、詳細に共同作業を行っています。 これらのシナリオでは、ユーザー管理とリソースへのアクセスを管理するには困難な場合があります。 ユーザー管理タスクの一部を自動化し、一部をパートナー組織に移行する場合も検討してください。

- [Azure のライセンスADとは?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Teams のプライベート チャネルを使用すると、チーム メンバーのサブセット間でスコープ設定された会話とファイル共有が可能になります。 特定のビジネス ニーズに応じて、この機能を許可またはブロックできます。

- [Microsoft Teams のプライベート チャネル](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Microsoft Teams のプライベート チャネルのライフ サイクルを管理する](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

追加情報:

- [Azure Active Directory ID ガバナンス](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[Microsoft Teams のセキュリティとコンプライアンス](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[SharePoint で共有設定を管理する](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Yammer で外部ネットワークを作成して管理する](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[3 層の保護を使って Teams を構成する](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
