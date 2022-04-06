---
title: ポータル Microsoft 365 Lighthouseの構成
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseのセキュリティを構成する方法について説明します。
ms.openlocfilehash: 4d12755ca1b02988dff3f5ba6be6dd0d8da172ad
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2022
ms.locfileid: "64594754"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>ポータル Microsoft 365 Lighthouseの構成

Managed Service Provider (MSP) がテナントにアクセス許可を委任した場合の顧客データへのアクセスの保護は、サイバーセキュリティの優先事項です。 Microsoft 365 Lighthouse、ライトハウス ポータルのセキュリティを構成するのに役立つ必須機能とオプション機能の両方が付属しています。 ライトハウスにアクセスするには、多要素認証 (MFA) を有効にした特定の役割を設定する必要があります。 必要に応じて、Azure AD Privileged Identity Management (PIM) と条件付きアクセスを設定できます。

## <a name="set-up-multifactor-authentication-mfa"></a>多要素認証 (MFA) のセットアップ

ブログ投稿で説明したように [、Pa$$wordは関係ありません](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)。

> 「パスワードは関係ありませんが、MFA は重要です。 弊社の調査に基づいて、MFA を使用するとアカウントが侵害される可能性が 99.9% を超えています。

ユーザーが初めてライトハウスにアクセスすると、ユーザーのアカウントにまだ構成されていない場合Microsoft 365 MFA の設定を求めるメッセージが表示されます。 必要な MFA セットアップ 手順が完了するまで、ユーザーはライトハウスにアクセスできます。 認証方法の詳細については、「多要素認証用にMicrosoft 365をセットアップする[」を参照してください](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-role-based-access-control"></a>役割ベースのアクセス制御を設定する

役割ベースのアクセス制御 (RBAC) は、ユーザー の役割に基づいてリソースまたは情報へのアクセスを許可します。 ライトハウスの顧客テナントデータと設定へのアクセスは、CSP (クラウド ソリューション プロバイダー) プログラムからの特定の役割に制限されます。 ライトハウスで RBAC の役割を設定するには、ユーザーに対して詳細な割り当てを実装するために、詳細な委任管理者特権 (GDAP) を使用することをお勧めします。 テナントが正常にオンボードするには、引き続き委任された管理者特権 (DAP) が必要ですが、GDAP 専用のお客様は、DAP に依存せずにすぐにオンボードできます。 顧客に対して DAP と GDAP が共存する場合、GDAP アクセス許可が優先されます。 

GDAP の使用を開始するには、「[アクセス](m365-lighthouse-overview-of-permissions.md)許可の概要」を参照Microsoft 365 Lighthouse。

MSP 技術者は、代理管理者特権 (DAP) を介して管理者エージェントまたはヘルプデスク エージェントの役割を使用して、ライトハウスにアクセスすることもできます。

ライトハウスでの顧客以外のテナント関連のアクション (オンボーディング、顧客の非アクティブ化/再アクティブ化、タグの管理、ログの確認など) の場合、MSP 技術者はパートナー テナントに割り当てられた役割を持っている必要があります。 前の記事リンクでは、ライトハウスでこのような役割とそのアクセス許可の詳細を説明します。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>セットアップ Azure AD Privileged Identity Management (PIM)

MSP は、PIM を使用して、セキュリティで保護された情報またはリソースに対する特権の高い役割アクセス権を持つユーザーの数を最小限に抑えます。 PIM は、悪意のあるユーザーがリソースにアクセスしたり、承認されたユーザーが機密性の高いリソースに誤って影響を与える可能性を減らします。 また、MSP は、リソースにアクセスし、広範な変更を加え、指定されたユーザーが特権アクセスで何をしているのかを監視するために、ユーザーに対して一度に高い特権の役割を付与することもできます。 

> [!NOTE]
> PIM Azure AD使用するには、パートナー テナントAzure AD Premium P2ライセンスが必要です。

次の手順では、PIM を使用して、パートナー テナント ユーザーを時間範囲の高い特権ロールに昇格します。

1. 記事「グループに役割を割り当てるグループを作成する」の説明に従って、役割割り当[て可能なグループをAzure Active Directory](/azure/active-directory/roles/groups-create-eligible)。

2. [[Azure AD – すべての](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)グループ] に移動し、新しいグループを高特権ロールのセキュリティ グループのメンバーとして追加します (たとえば、DAP の Admin Agents セキュリティ グループ、または GDAP ロールの同様にそれぞれのセキュリティ グループ)。

3. 「特権アクセス グループの対象となる所有者とメンバーを割り当てる」の記事の説明に従って、新しいグループへの特権アクセス [を設定します](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)。

PIM の詳細については、「What [is is Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>条件付きアクセスのリスクベースAzure AD設定する

MSP は、リスクベースの条件付きアクセスを使用して、スタッフメンバーが MFA を使用して自分の ID を証明し、危険なユーザーとして検出された場合にパスワードを変更します (資格情報の漏洩または Azure AD 脅威インテリジェンスによる)。 ユーザーは、危険なサインインとして検出された場合、使い慣れた場所または登録済みのデバイスからサインインする必要があります。 その他の危険な動作には、悪意のある IP アドレスまたは匿名 IP アドレスからのサインイン、非一致または不可能な移動場所からのサインイン、異常なトークンの使用、パスワード スプレーからのパスワードの使用、その他の異常なサインイン動作の表示が含まれます。 ユーザーのリスク レベルに応じて、MSP はサインイン時にアクセスをブロックする場合があります。 リスクの詳細については、「リスクとは [」を参照してください。](/azure/active-directory/identity-protection/concept-identity-protection-risks) 

> [!NOTE]
> 条件付きアクセスには、パートナー テナントAzure AD Premium P2ライセンスが必要です。 条件付きアクセスを設定するには、「[条件付きアクセスの構成Azure Active Directory参照してください](/appcenter/general/configuring-aad-conditional-access)。

## <a name="related-content"></a>関連コンテンツ

[パスワードのリセットのアクセス許可](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (記事)\
[ユーザーのMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)\
[ページのMicrosoft 365 Lighthouse](m365-lighthouse-overview.md) (記事)\
[アカウントにサインアップMicrosoft 365 Lighthouse](m365-lighthouse-sign-up.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)