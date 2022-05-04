---
title: ポータル セキュリティMicrosoft 365 Lighthouse構成する
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、ポータル セキュリティを構成する方法について説明します。
ms.openlocfilehash: 60e0d2f1ba61e5def3979358f338da0846914543
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188682"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>ポータル セキュリティMicrosoft 365 Lighthouse構成する

マネージド サービス プロバイダー (MSP) がテナントにアクセス許可を委任した場合の顧客データへのアクセスの保護は、サイバーセキュリティの優先順位です。 Microsoft 365 Lighthouseには、Lighthouse ポータルのセキュリティを構成するのに役立つ必須機能とオプション機能の両方が付属しています。 Lighthouse にアクセスするには、多要素認証 (MFA) が有効になっている特定のロールを設定する必要があります。 必要に応じて、Azure AD Privileged Identity Management (PIM) と条件付きアクセスを設定できます。

## <a name="set-up-multifactor-authentication-mfa"></a>多要素認証 (MFA) を設定する

ブログ記事「 [Pa$$wordは関係ありません](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)。

> "パスワードは関係ありませんが、MFA は重要です。 調査に基づくと、MFA を使用すると、アカウントが侵害される可能性が 99.9% を超える可能性が低くなります。

ユーザーが Lighthouse に初めてアクセスするときに、Microsoft 365 アカウントがまだ構成されていない場合は、MFA を設定するように求められます。 必要な MFA セットアップ手順が完了するまで、ユーザーは Lighthouse にアクセスできません。 認証方法の詳細については、「[多要素認証のMicrosoft 365 サインインを設定する](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)」を参照してください。

## <a name="set-up-role-based-access-control"></a>ロールベースのアクセス制御を設定する

ロールベースのアクセス制御 (RBAC) は、ユーザー ロールに基づいてリソースまたは情報へのアクセスを許可します。 Lighthouse の顧客テナント データと設定へのアクセスは、クラウド ソリューション プロバイダー (CSP) プログラムの特定のロールに制限されます。 Lighthouse で RBAC ロールを設定するには、詳細な委任管理特権 (GDAP) を使用して、ユーザーの詳細な割り当てを実装することをお勧めします。 テナントが正常にオンボードするには、委任された管理者特権 (DAP) が引き続き必要ですが、GDAP のみの顧客は、DAP に依存せずにすぐにオンボードできるようになります。 顧客に対して DAP と GDAP が共存する場合、GDAP のアクセス許可が優先されます。

GDAP リレーションシップを設定するには、「顧客の [サービスを管理するための詳細な管理者アクセス許可を取得する](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)」を参照してください。 Lighthouse を使用することをお勧めするロールの詳細については、「[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)」を参照してください。

MSP 技術者は、Admin Agent または Helpdesk Agent ロールを使用して、委任された管理者特権 (DAP) を使用して Lighthouse にアクセスすることもできます。

Lighthouse の非顧客テナント関連アクション (オンボード、顧客の非アクティブ化/再アクティブ化、タグの管理、ログの確認など) の場合、MSP 技術者はパートナー テナントに割り当てられたロールを持っている必要があります。 パートナー テナント ロールの詳細については、[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)に関するページを参照してください。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Azure AD Privileged Identity Managementの設定 (PIM)

MSP は、PIM を使用して、セキュリティで保護された情報またはリソースへの高い特権ロール アクセス権を持つユーザーの数を最小限に抑えることができます。 PIM を使用すると、悪意のあるユーザーがリソースにアクセスしたり、承認されたユーザーが機密リソースに誤って影響を与えたりする可能性が低くなります。 また、MSP は、リソースにアクセスし、広範な変更を加え、指定されたユーザーが特権アクセスで何を行っているかを監視するために、Just-In-Time 高い特権ロールをユーザーに付与することもできます。

> [!NOTE]
> Azure AD PIM を使用するには、パートナー テナントにAzure AD Premium P2 ライセンスが必要です。

次の手順では、PIM を使用して、パートナー テナント ユーザーを時間範囲の上位の特権ロールに昇格させます。

1. 「Azure Active Directoryでロールを割り[当てるためのグループを作成する」の説明に従って、ロール割り当て可能なグループを作成](/azure/active-directory/roles/groups-create-eligible)します。

2. [Azure AD – [すべてのグループ]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) に移動し、高い特権ロールのセキュリティ グループのメンバーとして新しいグループを追加します (たとえば、DAP の管理者エージェント セキュリティ グループ、GDAP ロールの同様のそれぞれのセキュリティ グループなど)。

3. 「特権アクセス グループの [対象となる所有者とメンバーを割り当てる](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)」の記事で説明されているように、新しいグループへの特権アクセスを設定します。

PIM の詳細については、「Privileged Identity Managementとは[」](/azure/active-directory/privileged-identity-management/pim-configure)を参照してください。

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>リスクベースのAzure AD条件付きアクセスを設定する

MSP は、リスクベースの条件付きアクセスを使用して、MFA を使用し、危険なユーザーとして検出された場合にパスワードを変更することで、スタッフメンバーが自分の ID を証明することを確認できます (資格情報が漏れた場合、または脅威インテリジェンスごとにAzure AD)。 ユーザーは、危険なサインインとして検出されたときに、使い慣れた場所または登録済みデバイスからサインインする必要もあります。 その他の危険な動作には、悪意のある IP アドレスまたは匿名 IP アドレスからのサインイン、非定型または不可能な移動場所からのサインイン、異常なトークンの使用、パスワード スプレーからのパスワードの使用、その他の異常なサインイン動作の表示などがあります。 ユーザーのリスク レベルに応じて、MSP はサインイン時にアクセスをブロックすることもできます。 リスクの詳細については、「[リスクとは何か](/azure/active-directory/identity-protection/concept-identity-protection-risks)」を参照してください。

> [!NOTE]
> 条件付きアクセスには、パートナー テナントにAzure AD Premium P2ライセンスが必要です。 条件付きアクセスを設定するには、「条件付きアクセス[Azure Active Directory構成する」を](/appcenter/general/configuring-aad-conditional-access)参照してください。

## <a name="related-content"></a>関連コンテンツ

[パスワード リセットのアクセス許可](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (記事)\
[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md) (記事)\
Microsoft 365 Lighthouse (記事)\ [でAzure Active Directoryロールを表示する](m365-lighthouse-view-your-roles.md)
[Microsoft 365 Lighthouseの要件](m365-lighthouse-requirements.md) (記事)\
[Microsoft 365 Lighthouseの概要](m365-lighthouse-overview.md) (記事)\
[Microsoft 365 Lighthouseにサインアップ](m365-lighthouse-sign-up.md)する (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)