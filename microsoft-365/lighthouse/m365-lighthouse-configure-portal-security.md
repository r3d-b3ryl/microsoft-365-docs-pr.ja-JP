---
title: ポータル Microsoft 365 Lighthouseの構成
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseセキュリティを構成する方法について説明します。
ms.openlocfilehash: 9701ecc002144f791be6caad1e93230be5a83bf0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191150"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>ポータル Microsoft 365 Lighthouseの構成

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Managed Service Provider (MSP) がテナントにアクセス許可を委任した場合の顧客データへのアクセスの保護は、サイバーセキュリティの優先事項です。 Microsoft 365 Lighthouse、ライトハウス ポータルのセキュリティを構成するのに役立つ必須機能とオプション機能の両方が付属しています。

## <a name="set-up-multifactor-authentication-mfa"></a>多要素認証 (MFA) のセットアップ

ブログの投稿で説明したように [、Pa$$wordは重要ではありません](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)。

> 「パスワードは関係ありませんが、MFA は重要です。 弊社の調査に基づいて、MFA を使用するとアカウントが侵害される可能性が 99.9% を超えています。

ユーザーが初めてライトハウスにアクセスすると、ユーザーのアカウントにまだ構成されていない場合Microsoft 365 MFA の設定を求めるメッセージが表示されます。 必要な MFA セットアップ 手順が完了するまで、ユーザーはライトハウスにアクセスできます。 認証方法の詳細については、「多要素認証用にサインイン[Microsoft 365を設定する」を参照してください](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-roles-to-manage-customer-tenants"></a>顧客テナントを管理するための役割の設定

ライトハウスの顧客テナント データと設定へのアクセスは、クラウド ソリューション プロバイダー (CSP) プログラムの管理エージェントとヘルプデスク エージェントの役割に制限されます。

パートナー テナント内のユーザーが管理エージェントとヘルプデスク エージェントの役割を持っているか確認するには、[Azure AD – すべてのグループ] ページでセキュリティ [グループのメンバーシップを確認](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) します。 CSP プログラムの役割と他のアクセス許可をユーザーに割り当てる方法については、「Assign roles and permissions to users」 [を参照してください](/partner-center/permissions-overview)。 MSP として、顧客テナントへのアクセス権限をまだ委任していない場合は、「顧客のサービスまたはサブスクリプションを管理するためのアクセス許可を取得する」の記事でそれらを取得する方法について [学習](/partner-center/customers-revoke-admin-privileges)します。

次の表に、管理エージェントとヘルプデスク エージェントの役割の顧客テナント データと設定を表示および操作するために必要な、さまざまなライトハウス ページとアクセス許可を示します。<br><br>

| [ライトハウス] ページ | 管理者エージェントのアクセス許可 | ヘルプデスク エージェントのアクセス許可 |
|--|--|--|
| ホーム | <ul><li>すべて表示する</li></ul> | <ul><li>すべて表示する</li></ul> |
| テナント | <ul><li>すべて表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示と適用</li></ul> | <ul><li>すべて表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示</li></ul> |
| ユーザー | <ul><li>すべて表示する</li><li>パスワードのリセット</li><li>サインインをブロックする</li><li>MFA を有効にする</li></ul> | <ul><li>すべて表示する</li><li>パスワードのリセット</li><li>サインインをブロックする</li></ul> |
| デバイス | <ul><li>すべて表示する</li></ul> | <ul><li>すべて表示する</li></ul> |
| Threats | <ul><li>すべて表示する</li><li>クイック スキャンの実行</li><li>フル スキャンの実行</li><li>デバイスを再起動する</li><li>ウイルス対策の更新</li></ul> | <ul><li>すべて表示する</li></ul> |
| 基準計画 | <ul><li>すべて表示する</li></ul> | <ul><li>すべて表示する</li></ul> |
| サービス正常性 | <ul><li>すべて表示*</li></ul> | <ul><li>すべて表示*</li></ul> |

> [!NOTE]
> 現在、表に * とマークされたアクションを実行するには、次のプロパティ セットを持つパートナー テナントで Azure AD ロールを持つ必要があります **。microsoft.office365.serviceHealth/allEntities/allTasks**。 Azure ADロールの一覧については、「Azure AD [組み込みロール」を参照してください](/azure/active-directory/roles/permissions-reference)。

管理エージェントの役割に関連する広範なアクセス許可を考えると、パートナー テナント ユーザー[](/azure/active-directory/develop/secure-least-privileged-access)を管理エージェントとヘルプデスク エージェントとして指定する場合は、最小特権アクセスの原則に従う必要があります。 これを行う 1 つの方法は、必要なパートナー テナント ユーザーにヘルプデスク エージェントの役割を割り当てる方法です。 これにより、顧客のデータと設定を表示できますが、大まかな変更は行う必要はありません。 次に、必要に応じて、Azure AD Privileged Identity Management (PIM) の just-in-time アクセス承認機能を使用して、ユーザーに時間範囲の管理エージェントの役割を付与します。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Azure AD Privileged Identity Managementのセットアップ (PIM)

MSP は、Azure AD Privileged Identity Management (PIM) を使用して、セキュリティで保護された情報またはリソースにアクセスできるユーザー AD Privileged Identity Managementできます。 PIM は、悪意のあるユーザーがリソースにアクセスしたり、承認されたユーザーが機密性の高いリソースに誤って影響を与える可能性を減らします。 また、MSP は、ユーザーにリソースへの特権アクセス権を与え、指定されたユーザーが特権アクセスで何をしているのかを監視できます。

> [!NOTE]
> Azure AD PIM を使用するには、パートナー テナントAzure AD Premium P2ライセンスが必要です。

次の手順では、Azure テナント PIM を使用して、パートナー テナント ユーザーを時間範囲の管理エージェント の役割ADします。

1. 「グループに役割を割り当てるグループを作成する」の記事の説明に従って、役割割り当[て可能なグループをAzure Active Directory。](/azure/active-directory/roles/groups-create-eligible)

2. [Azure [AD – すべてのグループ]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) に移動し、新しいグループを管理者エージェント グループのメンバーとして追加します。

3. 「特権アクセス グループの対象となる所有者とメンバーを割り当てる」の記事の説明に従って、新しいグループへの特権アクセス [を設定します](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)。

詳細については、「What [is is Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>その他の役割とアクセス許可

次の表に、パートナー テナントの役割と関連するアクセス許可を示します。<br><br>

| パートナーテナントの役割 | パートナー テナント内のアクセス許可 |
|--|--|
| パートナー テナントのグローバル管理者 | <ul><li>[ライトハウス] にサインアップMicrosoft 365 管理センター。</li><li>初回実行時にパートナー契約の変更を受け入れる。</li><li>[テナント] ページで顧客テナントを表示します。\*</li><li>テナントをアクティブ化して非アクティブ化します。\*</li><li>顧客の連絡先と Web サイトを更新します。\*</li><li>タグを作成、更新、および削除します。\*</li><li>顧客テナントにタグを割り当て、削除します。\*</li></ul> |
| 少なくとも 1 つのパートナー テナントの管理者<br> Azure ADのプロパティ セットに割り当てられている役割を指定します。<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> (Azure ADロールの一覧については、「Azure AD [組み込みロール」を参照](/azure/active-directory/roles/permissions-reference)してください。 | <ul><li>ライトハウス サービス要求を作成します。</li></ul> |

> [!NOTE]
> 現在、表に * とマークされたアクションを実行するには、グローバル管理者が管理エージェントの役割を引き受けなければならない。

## <a name="related-content"></a>関連コンテンツ

[サービスのMicrosoft 365 Lighthouse](m365-lighthouse-overview.md) (記事)\
[アカウントにサインアップMicrosoft 365 Lighthouse](m365-lighthouse-sign-up.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)