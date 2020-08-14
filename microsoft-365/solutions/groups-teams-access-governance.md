---
title: Microsoft 365 グループ、Teams、SharePoint でのアクセスの管理
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、SharePoint でのアクセス管理について説明します。
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662723"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 グループ、Teams、SharePoint でのアクセスの管理

ユーザーがグループ、teams、および SharePoint でリソースにアクセスする方法を制御できるようになるコントロールは多数あります。 これらのオプションを確認し、ビジネスニーズへの対応方法、データの機密性、およびユーザーが共同作業する必要のあるユーザーの範囲を検討してください。

次の表に、Microsoft 365 で利用可能なアクセス制御のクイックリファレンスを示します。 詳細については、以下のセクションを参照してください。

|カテゴリ|説明|リファレンス|
|:-------|:----------|:--------|
|メンバーシップ|||
||プライベートチームの検出|[Microsoft Teams でプライベートチームの検出を管理する](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||ルールに基づく動的なグループメンバーシップ|[Azure Active Directory で動的グループを作成または更新する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||ファイル、フォルダー、サイトを共有できるユーザーを制御します。|[アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件付きアクセス|||
||多要素認証|[Azure 多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||グループ、チーム、またはサイトの秘密度に基づいてデバイスアクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||管理されていないデバイスのサイトアクセスを制限します。|[非管理対象デバイスから SharePoint へのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||場所に基づいてサイトアクセスを制御する|[ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|ゲスト アクセス|||
||指定したドメインからの SharePoint の共有を許可または禁止します。|[ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||指定したドメインからのチームまたはグループメンバーシップを許可または禁止します。|[特定の組織からの B2B ユーザーへの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||匿名での共有を禁止します。|[[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||匿名アクセスリンクのアクセス許可を制御します。|[すべてのリンクのリンクのアクセス許可を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||匿名の共有リンクの有効期限を制御します。|[[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||既定でユーザーに表示される共有リンクの種類を制御します。|[サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||特定のユーザーに対する外部共有を制限します。|[指定したセキュリティグループへの外部共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||情報の秘密度に基づいて、グループ、チーム、またはサイトへのゲストアクセスを制御します。|[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||共有オプションをオフにします。|[Microsoft 365 の共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|ユーザーの管理|||
||チームおよびグループのメンバーシップを定期的に確認します。|[Azure AD のアクセスレビューとは](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||グループとチームへのアクセス管理を自動化します。|[Azure AD 受給管理とは](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||ユーザーが Teams でプライベートチャネルを作成することを許可または禁止します。|[Microsoft Teams のプライベートチャネルのライフサイクルを管理する](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>メンバーシップ

Teams およびグループのメンバーシップは、所有者によって制御されます。 メンバーは他のユーザーを招待できますが、承認のために招待状が所有者に送信されます。 パブリックチームとグループは、組織内のすべてのユーザーが検出できますが、プライベートチームとグループを検出可能にするかどうかを制御できます。

- [Microsoft Teams でプライベートチームの検出を管理する](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

部署などの条件に基づいて、グループまたはチームのメンバーシップを動的に管理することができます。 この場合、メンバーと所有者はチームに人を招待できません。

- [Azure Active Directory で動的グループを作成または更新する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint サイトには、グループまたはチームメンバーシップとの間で所有者、メンバー、および訪問者を追加する機能が用意されています。 要件に応じて、ユーザーをサイトに招待できるユーザーを制限することができます。 また、特定のサイトの情報の機密性に応じて、ファイルとフォルダーを共有できるユーザーを制限することもできます。 これらの制限は、チーム、グループ、またはサイトの所有者によって構成されます。

- [アクセス要求の設定と管理](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件付きアクセス

Microsoft 365 では、組織の内部および外部の両方のユーザーに多要素認証を要求できます。 2番目の認証のためにユーザーにメッセージが表示される場合、さまざまな状況に対応するオプションがあります。 組織には、多要素認証を展開することを強くお勧めします。

- [Azure 多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

一部のグループとチームに機密情報がある場合は、グループまたはチームの機密ラベルに基づいてデバイス管理ポリシーを適用できます。 管理されていないデバイスからのアクセスを完全にブロックしたり、制限された web のみのアクセスを許可したりすることができます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

SharePoint では、指定したネットワークの場所からサイトへのアクセスを制限できます。

- [ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


追加情報:

- [条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune の概要](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [非管理対象デバイスから SharePoint へのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>ゲスト アクセス

電子メールアドレスのドメインに基づいてゲストを制限することができます。 SharePoint では、組織全体およびサイト固有のドメイン制限の設定を行うことができます。 グループとチームは、Azure AD のドメインの許可リストと拒否リストを使用します。 不要な共有を回避し、一貫したユーザー環境を確保するために、両方の設定を構成してください。

- [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [特定の組織からの B2B ユーザーへの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 では、 *すべて* の共有リンクを使用して、ファイルとフォルダーを匿名で共有できます。 *すべて* のリンクを転送でき、リンクを持つすべてのユーザーが共有アイテムにアクセスできます。 データの機密性に応じて、 *すべて* のリンクの使用方法を制御します。これには、完全にオフにしたり、リンクのアクセス許可を読み取り専用に制限したり、有効期限を設定したりすることも含まれます。

- [[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [すべてのリンクのリンクのアクセス許可を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

ファイルまたはフォルダーを共有する場合、ユーザーはさまざまなリンクの種類を選択できます。 偶発的な適切でない共有の危険性を軽減するために、ユーザーが共有するときに表示される既定のリンクの種類を変更することができます。 たとえば、*組織リンク内のユーザー*に匿名アクセスを許可する、[*すべて*のユーザー] リンクから既定の設定を変更すると、機密情報の不必要な外部共有のリスクを軽減できます。

- [サイトの既定のリンクの種類を変更する](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

組織に機密データがあり、ゲストと共有する必要があるが、不適切な共有について懸念している場合は、ファイルとフォルダーの外部共有を、指定したセキュリティグループのメンバーに制限できます。 この方法では、特定のユーザーグループに対して外部共有を制限したり、ユーザーをセキュリティグループに追加する前に、適切な外部共有についてトレーニングを受ける必要があります。

- [指定したセキュリティグループへの外部共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

グループとチームには、ゲストアクセスを許可または拒否する組織レベルの設定があります。 [Microsoft PowerShell を使用して特定のチームまたはグループへのゲストアクセスを制限](per-group-guest-access.md)することができますが、これは機密ラベルを使用して行うことをお勧めします。 機密ラベルを使用すると、適用されたラベルに基づいてゲストアクセスを自動的に許可または拒否することができます。

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 では、さまざまな方法で情報を共有できます。 機密情報があり、その共有方法を制限する場合は、共有を制限するためのオプションを確認します。

- [Microsoft 365 の共有を制限する](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

追加情報:

- [Microsoft 365 とセキュリティで保護された共同作業を設定する](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [セキュリティで保護されたゲスト共有環境を作成する](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [B2B 外部コラボレーションを有効にし、ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>ユーザーの管理

組織でのグループとチームの発展と同様に、チームとグループのメンバーシップを定期的に確認することをお勧めします。 これは、変更されたメンバーシップを持つ teams やグループに対して、機密情報を含む、またはゲストを含むグループに対して特に役立ちます。 これらのチームおよびグループのアクセスレビューを設定することを検討してください。

- [Azure AD のアクセスレビューとは](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

多くの組織では、他の組織または重要なベンダーとのビジネスパートナーシップがあります。 ユーザー管理とリソースへのアクセスは、これらのシナリオで管理するのが困難な場合があります。 一部のユーザー管理タスクを自動化し、一部のユーザー管理タスクをパートナー組織に移行することを検討してください。

- [Azure AD 受給管理とは](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Teams のプライベートチャネルでは、チームメンバーのサブセット間でのスレッドの範囲指定とファイル共有が許可されます。 特定のビジネスニーズに応じて、この機能を許可またはブロックすることができます。

- [Microsoft Teams のプライベート チャネル](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Microsoft Teams のプライベートチャネルのライフサイクルを管理する](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

追加情報:

- [Azure Active Directory Id ガバナンス](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>関連項目

[Microsoft Teams のセキュリティとコンプライアンス](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[SharePoint で共有設定を管理する](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Yammer で外部ネットワークを作成して管理する](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[3 層の保護を使ってチームを構成する](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
