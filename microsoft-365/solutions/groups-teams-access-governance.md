---
title: Microsoft 365 グループ、Teams、およびSharePointでのアクセスの管理
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
description: Microsoft 365 グループ、Teams、SharePointでのアクセスの管理について説明します。
ms.openlocfilehash: 3f4304a54cd1eae86c98d530e5a4ec4db5f6dc66
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716170"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、およびSharePointでのアクセスの管理

ユーザーがグループ、チーム、およびSharePointのリソースにアクセスする方法を制御できる多くの制御があります。 これらのオプションを確認し、ビジネス ニーズに対応する方法、データの機密性、ユーザーが共同作業する必要があるユーザーの範囲を検討します。

次の表に、Microsoft 365で使用できるアクセス制御のクイック リファレンスを示します。 詳細については、次のセクションで説明します。

|カテゴリ|説明|参照|
|:-------|:----------|:--------|
|メンバーシップ|||
||プライベート チームの検出|[Microsoft Teamsでプライベート チームの検出を管理する](/microsoftteams/manage-discovery-of-private-teams)|
||ルールに基づく動的グループ メンバーシップ|[Azure Active Directoryで動的グループを作成または更新する](/azure/active-directory/users-groups-roles/groups-create-rule)|
||ファイル、フォルダー、サイトを共有できるユーザーを制御します。|[アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件付きアクセス|||
||多要素認証|[Azure AD多要素認証](/azure/active-directory/authentication/concept-mfa-howitworks)|
||グループ、チーム、またはサイトの秘密度に基づいてデバイス アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||管理されていないデバイスのサイト アクセスを制限します。|[管理されていないデバイスからのSharePointアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)|
||場所に基づいてサイト アクセスを制御する|[ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](/sharepoint/control-access-based-on-network-location)|
|ゲスト アクセス|||
||指定したドメインからのSharePoint共有を許可またはブロックします。|[ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](/sharepoint/restricted-domains-sharing)|
||指定したドメインからチームまたはグループのメンバーシップを許可またはブロックします。|[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)|
||匿名共有を禁止します。|[[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||匿名アクセス リンクのアクセス許可を制御します。|[すべてのリンクのリンクアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)|
||匿名共有リンクの有効期限を制御します。|[[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||既定では、ユーザーに表示される共有リンクの種類を制御します。|[サイトの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)|
||外部共有を特定のユーザーに制限します。|[外部共有を指定されたセキュリティ グループに制限する](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||情報の機密性に基づいて、グループ、チーム、またはサイトへのゲスト アクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)|
||共有オプションを無効にします。|[Microsoft 365 の共有を制限する](./microsoft-365-limit-sharing.md)|
|ユーザーの管理|||
||定期的にチームとグループのメンバーシップを確認します。|[Azure ADアクセス レビューとは何ですか?](/azure/active-directory/governance/access-reviews-overview)|
||グループとチームへのアクセス管理を自動化します。|[エンタイトルメント管理Azure ADとは](/azure/active-directory/governance/entitlement-management-overview)|

## <a name="membership"></a>メンバーシップ

チームとグループのメンバーシップは、所有者によって制御されます。 メンバーは他のユーザーを招待できますが、招待は承認のために所有者に送信されます。 パブリック チームとグループは組織内のだれでも検出できますが、プライベート チームとグループが検出可能かどうかを制御できます。

- [Microsoft Teamsでプライベート チームの検出を管理する](/microsoftteams/manage-discovery-of-private-teams)

部門などの一部の条件に基づいて、グループまたはチームのメンバーシップを動的に管理できます。 この場合、メンバーと所有者はチームにユーザーを招待できません。 動的グループでは、Azure Active Directoryで定義したメタデータを使用して、グループのメンバーを制御します。 不適切なメタデータによってユーザーがグループから除外されたり、間違ったユーザーが追加されたりする可能性があるため、使用しているメタデータが完全で最新であることを確認してください。

- [Azure Active Directoryで動的グループを作成または更新する](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint サイトでは、グループメンバーシップまたはチーム メンバーシップとは別に、所有者、メンバー、および訪問者を追加できます。 要件に応じて、サイトにユーザーを招待できるユーザーを制限することもできます。 また、特定のサイトの情報の機密性によっては、ファイルとフォルダーを共有できるユーザーを制限することもできます。 これらの制限は、チーム、グループ、またはサイト所有者によって構成されます。

- [アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件付きアクセス

Microsoft 365を使用すると、組織内外のユーザーの両方に多要素認証を要求できます。 2 つ目の認証要素を求められる状況には、多くのオプションがあります。 組織に多要素認証を展開することを非常に推奨します。

- [多要素認証のAzure AD](/azure/active-directory/authentication/concept-mfa-howitworks)

一部のグループとチームに機密情報がある場合は、グループまたはチームの秘密度ラベルに基づいてデバイス管理ポリシーを適用できます。 管理されていないデバイスからのアクセスを完全にブロックすることも、制限付きの Web のみのアクセスを許可することもできます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

SharePointでは、指定したネットワークの場所からのサイトへのアクセスを制限できます。

- [ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](/sharepoint/control-access-based-on-network-location)


追加情報:

- [条件付きアクセスのデプロイを計画する](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune の概要](/mem/intune/fundamentals/what-is-intune)

- [管理されていないデバイスからのSharePointアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>ゲスト アクセス

ゲストは、その電子メール アドレスのドメインに基づいて制限できます。 SharePointでは、組織全体およびサイト固有のドメイン制限設定が提供されます。 グループとTeamsは、Azure ADのドメイン 許可リストまたはブロックリストを使用します。 不要な共有を回避し、一貫したユーザー エクスペリエンスを確保するために、両方の設定を必ず構成してください。

- [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](/sharepoint/restricted-domains-sharing)

- [B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365では、*すべての* ユーザー共有リンクを使用して、ファイルとフォルダーを匿名で共有できます。 *すべての* リンクを転送でき、リンクを持つすべてのユーザーが共有アイテムにアクセスできます。 データの機密性に応じて、 *すべてのユーザー* のリンクの使用方法を管理することを検討してください。たとえば、リンクのアクセス許可を読み取り専用に制限したり、有効期限を設定したりします。

- [[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [すべてのリンクのリンクアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)

- [[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

ファイルまたはフォルダーを共有する場合、ユーザーには選択できるリンクの種類がいくつかあります。 不適切な共有を誤って行うリスクを軽減するために、共有時にユーザーに表示される既定のリンクの種類を変更できます。 たとえば、*組織内のユーザー* への匿名アクセスを許可する *[すべての* ユーザー] リンクから既定のリンクを変更すると、機密情報の不要な外部共有のリスクを軽減できます。

- [サイトの既定のリンクの種類を変更する](/sharepoint/change-default-sharing-link)

組織にゲストと共有する必要がある機密データがあるが、不適切な共有が懸念される場合は、ファイルとフォルダーの外部共有を指定されたセキュリティ グループのメンバーに制限できます。 この方法で、特定のユーザー グループへの外部共有を制限したり、ユーザーをセキュリティ グループに追加する前に、適切な外部共有に関するトレーニングを受ける必要があります。

- [外部共有を指定されたセキュリティ グループに制限する](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

グループとTeamsには、ゲスト アクセスを許可または拒否する組織レベルの設定があります。 [Microsoft PowerShell を使用して特定のチームまたはグループへのゲスト アクセスを制限](per-group-guest-access.md)できますが、秘密度ラベルを使用してこれを行うことをお勧めします。 秘密度ラベルを使用すると、適用されたラベルに基づいてゲスト アクセスを自動的に許可または拒否できます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)

グループやチームにゲストを頻繁に招待する環境では、定期的にスケジュールされたゲスト アクセス レビューを設定することを検討してください。 所有者は、グループとチームのゲストを確認し、アクセスを承認または拒否するように求めることができます。

- [ゲスト アクセス レビューを設定する](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365には、さまざまな情報共有方法が用意されています。 機密情報があり、共有方法を制限する場合は、共有を制限するオプションを確認します。

- [Microsoft 365 の共有を制限する](./microsoft-365-limit-sharing.md)

追加情報:

- [Microsoft 365 を使用してセキュリティで保護された共同作業を設定する](./setup-secure-collaboration-with-teams.md)

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](./best-practices-anonymous-sharing.md)

- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](./share-limit-accidental-exposure.md)

- [セキュリティで保護されたゲスト共有環境を作成する](./create-secure-guest-sharing-environment.md)

- [B2B の外部コラボレーションを有効にしてゲストを招待できるユーザーを管理する](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>ユーザーの管理

組織でグループとチームが進化するにつれて、チームとグループのメンバーシップを定期的に確認することをお勧めします。 これは、メンバーシップが変更されているチームやグループ、機密情報を含むチームやグループ、またはゲストを含むチームやグループに特に役立つ場合があります。 これらのチームとグループのアクセス レビューを設定することを検討してください。

- [Azure ADアクセス レビューとは何ですか?](/azure/active-directory/governance/access-reviews-overview)

多くの組織は、他の組織や重要なベンダーとビジネス パートナーシップを結び、深く連携しています。 これらのシナリオでは、ユーザー管理とリソースへのアクセスを管理するのは困難な場合があります。 ユーザー管理タスクの一部を自動化し、一部をパートナー組織に移行することを検討してください。

- [エンタイトルメント管理Azure ADとは](/azure/active-directory/governance/entitlement-management-overview)

Teamsのプライベート チャネルでは、チーム メンバーのサブセット間でスコープを設定された会話とファイル共有を行うことができます。 特定のビジネス ニーズに応じて、この機能を許可またはブロックすることもできます。

- [Microsoft Teams のプライベート チャネル](/MicrosoftTeams/private-channels)

共有チャネルを使用すると、チーム外または組織外のユーザーを招待できます。 特定のビジネス ニーズと外部共有ポリシーに応じて、この機能を許可またはブロックすることができます。

- [共有チャネル](/MicrosoftTeams/shared-channels)

追加情報:

- [Azure Active Directory Identity Governance](/azure/active-directory/governance)

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[Microsoft Teams のセキュリティとコンプライアンス](/microsoftteams/security-compliance-overview)

[SharePointで共有設定を管理する](/sharepoint/turn-external-sharing-on-or-off)

[Yammer で外部ネットワークを作成して管理する](/yammer/work-with-external-users/create-and-manage-an-external-network)

[3 層の保護を使って Teams を構成する](./configure-teams-three-tiers-protection.md)