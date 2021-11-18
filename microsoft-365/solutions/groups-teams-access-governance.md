---
title: グループ、グループ、Microsoft 365、およびTeamsのアクセスを管理SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: グループ、グループ、グループ、Microsoft 365、およびTeamsアクセスの管理SharePoint。
ms.openlocfilehash: e01326093476f341c6c4c75448efbdf8c745779f
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064333"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>グループ、グループ、Microsoft 365、およびTeamsのアクセスを管理SharePoint

ユーザーがグループ、チーム、およびグループ内のリソースにアクセスする方法を管理できる多くのコントロールSharePoint。 これらのオプションを確認し、ビジネス ニーズ、データの感度、ユーザーが共同作業に必要なユーザーの範囲にマップする方法を検討します。

次の表は、次の表で使用できるアクセス制御のクイック リファレンスを示Microsoft 365。 詳細については、次のセクションで説明します。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|メンバーシップ|||
||プライベート チームの検出|[プライベート チームの検出を管理Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||ルールに基づく動的グループ メンバーシップ|[グループ内で動的グループを作成または更新Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||ファイル、フォルダー、サイトを共有できるユーザーを制御します。|[アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件付きアクセス|||
||多要素認証|[Azure AD多要素認証](/azure/active-directory/authentication/concept-mfa-howitworks)|
||グループ、チーム、またはサイトの感度に基づいてデバイス アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||管理されていないデバイスのサイト アクセスを制限します。|[管理SharePointデバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)|
||場所に基づいてサイト アクセスを制御する|[ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](/sharepoint/control-access-based-on-network-location)|
|ゲスト アクセス|||
||指定したドメインSharePoint共有を許可またはブロックします。|[ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](/sharepoint/restricted-domains-sharing)|
||指定したドメインからチームまたはグループのメンバーシップを許可またはブロックします。|[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)|
||匿名共有を防止します。|[[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||匿名アクセス リンクのアクセス許可を制御します。|[[ユーザー] リンクのリンクのアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)|
||匿名共有リンクの有効期限を制御します。|[[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||既定では、ユーザーに表示される共有リンクの種類を制御します。|[サイトの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)|
||外部共有を特定のユーザーに制限します。|[外部共有を指定したセキュリティ グループに制限する](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||情報の感度に基づいて、グループ、チーム、またはサイトへのゲスト アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||共有オプションをオフにします。|[Microsoft 365 の共有を制限する](./microsoft-365-limit-sharing.md)|
|ユーザーの管理|||
||チームとグループのメンバーシップを定期的に確認します。|[アクセス レビュー Azure ADは何ですか?](/azure/active-directory/governance/access-reviews-overview)|
||グループとチームへのアクセス管理を自動化します。|[エンタイトルメントAzure ADとは?](/azure/active-directory/governance/entitlement-management-overview)|
||ユーザーによるプライベート チャネルの作成を許可またはブロックTeams。|[プライベート チャネルのライフ サイクルを管理Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>メンバーシップ

チームとグループのメンバーシップは、所有者によって制御されます。 メンバーは他のユーザーを招待できますが、招待は承認のために所有者に送信されます。 パブリック チームとグループは組織内の誰でも見つけられますが、プライベート チームとグループを検出できるかどうかを制御できます。

- [プライベート チームの検出を管理Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

グループまたはチームのメンバーシップは、部署などの一部の条件に基づいて動的に管理できます。 この場合、メンバーと所有者はチームにユーザーを招待できません。 動的グループは、グループ内で定義したメタデータAzure Active Directoryグループのメンバーを制御します。 使用しているメタデータが完全で、メタデータが正しくないと、ユーザーがグループから抜け出したり、正しくないユーザーが追加される可能性があります。

- [グループ内で動的グループを作成または更新Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePointサイトでは、グループまたはチームのメンバーシップとは別に、所有者、メンバー、および訪問者を追加できます。 要件に応じて、ユーザーをサイトに招待できるユーザーを制限できます。 また、特定のサイト内の情報の感度に応じて、ファイルとフォルダーを共有できるユーザーを制限することもできます。 これらの制限は、チーム、グループ、またはサイトの所有者によって構成されます。

- [アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件付きアクセス

このMicrosoft 365、組織内外の両方のユーザーに対して多要素認証を要求できます。 ユーザーに認証の第 2 の要素を求めるメッセージが表示される状況には、多くのオプションがあります。 組織に多要素認証を展開することを強くお勧めします。

- [Azure AD多要素認証](/azure/active-directory/authentication/concept-mfa-howitworks)

一部のグループやチームに機密情報がある場合は、グループまたはチームの機密ラベルに基づいてデバイス管理ポリシーを適用できます。 管理されていないデバイスからのアクセスを完全にブロックするか、制限付き Web アクセスのみを許可できます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

このSharePoint、指定したネットワークの場所からのサイトへのアクセスを制限できます。

- [ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](/sharepoint/control-access-based-on-network-location)


追加情報:

- [条件付きアクセスの展開を計画する](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune の概要](/mem/intune/fundamentals/what-is-intune)

- [管理SharePointデバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>ゲスト アクセス

電子メール アドレスのドメインに基づいてゲストを制限できます。 SharePointは、組織全体およびサイト固有のドメイン制限設定を提供します。 グループとグループTeams、ドメインの許可リストまたはブロックリストを使用Azure AD。 望ましくない共有を避け、一貫性のあるユーザー エクスペリエンスを確保するために、両方の設定を必ず構成してください。

- [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](/sharepoint/restricted-domains-sharing)

- [B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365リンクを使用して、ファイルとフォルダーの匿名共有 *を* 許可します。 *リンク* は誰でも転送可能で、リンクを持つユーザーは共有アイテムにアクセスできます。 データの感度に応じて、リンクを完全にオフにしたり、リンクのアクセス許可を読み取り専用に制限したり、そのリンクの有効期限を設定したりなど、すべてのユーザーのリンクの使用方法を管理する方法を検討してください。

- [[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [[ユーザー] リンクのリンクのアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)

- [[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

ファイルまたはフォルダーを共有する場合、ユーザーは複数のリンクの種類から選択できます。 不適切な共有が誤って発生するリスクを軽減するために、ユーザーが共有するときに表示される既定のリンクの種類を変更できます。 たとえば、匿名アクセスを許可する[すべてのユーザー] リンクから[組織内のユーザー] リンクに既定値を変更すると、機密情報の望ましくない外部共有のリスクが軽減されます。

- [サイトの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)

組織にゲストと共有する必要がある機密データがあるが、不適切な共有が懸念されている場合は、ファイルとフォルダーの外部共有を指定したセキュリティ グループのメンバーに制限できます。 この方法で、外部での共有を特定のユーザー グループに制限したり、セキュリティ グループに追加する前に、適切な外部共有に関するトレーニングをユーザーに要求することができます。

- [外部共有を指定したセキュリティ グループに制限する](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

グループとグループTeams、ゲスト アクセスを許可または拒否する組織レベルの設定があります。 [Microsoft PowerShell を使用](per-group-guest-access.md)して、特定のチームまたはグループへのゲスト アクセスを制限することができますが、これを行う際には、感度ラベルを使用することをお勧めします。 感度ラベルを使用すると、適用されたラベルに基づいてゲスト アクセスを自動的に許可または拒否できます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

グループやチームにゲストを頻繁に招待する環境では、定期的にスケジュールされたゲスト アクセス レビューの設定を検討してください。 所有者は、グループとチームのゲストを確認し、アクセスを承認または拒否するように求めるメッセージを表示できます。

- [ゲスト アクセス レビューを設定する](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365は、情報を共有するさまざまな方法を提供します。 機密情報を持ち、共有方法を制限する場合は、共有を制限するためのオプションを確認します。

- [Microsoft 365 の共有を制限する](./microsoft-365-limit-sharing.md)

追加情報:

- [Microsoft 365 を使用してセキュリティで保護された共同作業を設定する](./setup-secure-collaboration-with-teams.md)

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](./best-practices-anonymous-sharing.md)

- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](./share-limit-accidental-exposure.md)

- [セキュリティで保護されたゲスト共有環境を作成する](./create-secure-guest-sharing-environment.md)

- [B2B の外部コラボレーションを有効にしてゲストを招待できるユーザーを管理する](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>ユーザーの管理

グループとチームが組織内で進化するにつれて、チームとグループのメンバーシップを定期的に確認する方法をお試しください。 これは、メンバーシップが変更されたチームやグループ、機密情報を含むチーム、またはゲストを含むグループに特に役立ちます。 これらのチームとグループのアクセス レビューを設定する方法を検討してください。

- [アクセス レビュー Azure ADは何ですか?](/azure/active-directory/governance/access-reviews-overview)

多くの組織は、他の組織や主要ベンダーとビジネス パートナーシップを結び、詳細に共同作業を行っています。 これらのシナリオでは、ユーザー管理とリソースへのアクセスを管理するには困難な場合があります。 ユーザー管理タスクの一部を自動化し、一部をパートナー組織に移行する場合も検討してください。

- [エンタイトルメントAzure ADとは?](/azure/active-directory/governance/entitlement-management-overview)

プライベート チャネルは、Teamsメンバーのサブセット間のスコープ付き会話とファイル共有を可能にします。 特定のビジネス ニーズに応じて、この機能を許可またはブロックできます。

- [Microsoft Teams のプライベート チャネル](/MicrosoftTeams/private-channels)

- [プライベート チャネルのライフ サイクルを管理Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

追加情報:

- [Azure Active Directory ID ガバナンス](/azure/active-directory/governance)

## <a name="related-topics"></a>関連トピック

[コラボレーション ガバナンス計画の推奨事項](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[Microsoft Teams のセキュリティとコンプライアンス](/microsoftteams/security-compliance-overview)

[[共有設定の管理] SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Yammer で外部ネットワークを作成して管理する](/yammer/work-with-external-users/create-and-manage-an-external-network)

[3 層の保護を使って Teams を構成する](./configure-teams-three-tiers-protection.md)