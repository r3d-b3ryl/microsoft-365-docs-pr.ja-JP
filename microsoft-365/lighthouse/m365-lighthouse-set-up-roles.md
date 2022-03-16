---
title: 顧客テナントを管理するための役割の設定
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseを使用する場合は、顧客テナントを管理するための役割を設定する方法について説明します。
ms.openlocfilehash: 948e6909f0fc8d743c84662de6c8a2d9c0bc88e3
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512242"
---
# <a name="set-up-roles-to-manage-customer-tenants"></a>顧客テナントを管理するための役割の設定

マネージ サービス プロバイダー (MSP) は、パートナー センターで詳細な代理管理者特権 (GDAP) を構成することで、Microsoft 365 Lighthouse で顧客テナントへの詳細で時間的なアクセスを有効にできます。 GDAP は、組み込みロール (Azure Active Directory) を介してAzure ADアクセスを提供することで、MSP に高いレベル[の制御と柔軟性を提供します](/azure/active-directory/roles/permissions-reference)。 GDAP [を介してタスク別に](/azure/active-directory/roles/delegate-by-task) 最小特権ロールを MSP 技術者に割り当てると、MSP と顧客の両方のセキュリティ リスクが軽減されます。 GDAP を有効にして、ライトハウスを使用する技術者により詳細な役割を割り当て、顧客テナント全体のセキュリティに最も特権の少ないアプローチを採用します。

MSP 技術者が代理管理者特権 (DAP) を通じて付与されたヘルプデスク エージェントまたは管理エージェントの役割を使用して顧客環境に引き続きアクセスする場合は、この記事の「ライトハウスの [DAP](#dap-in-lighthouse) 」を参照してください。 GDAP と DAP の両方が共存する場合、GDAP を介してユーザーに付与される役割は、GDAP 関係が確立されている顧客に優先されます。

## <a name="set-up-gdap-in-lighthouse"></a>ライトハウスで GDAP を設定する

> [!NOTE]
> GDAP は現在 [テクニカル プレビュー (](/partner-center/announcements/2022-february#6) パブリック プレビュー) で、パートナーが GDAP を一般に利用できる前に、詳細なアクセス許可を割り当て可能です。

顧客との GDAP 関係を作成するには、以下の高レベルの手順が必要です。 GDAP の詳細については、「 [詳細な委任管理者特権 (GDAP) の概要」を参照してください。](/partner-center/gdap-introduction)

1. [パートナー テナント内のセキュリティ](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) グループにユーザーを分類Azure AD。

2. [GDAP リレーションシップ要求を作成し、顧客](/partner-center/gdap-obtain-admin-permissions-to-manage-customer) に送信します。

3. 顧客が [GDAP リレーションシップ 要求を承認するようにします](/partner-center/gdap-customer-approval)。

4. [関連するセキュリティ グループを](/partner-center/gdap-assign-azure-ad-roles#grant-permissions-to-security-groups) GDAP リレーションシップに割り当てる。

5. 組み込Azure Active Directory[適切な役割を、](/azure/active-directory/roles/permissions-reference)顧客管理に合わせて揃えたライトハウス セキュリティ グループに割り当てます。

MSP 技術者がライトハウスで処理するタスクに基づいてセキュリティ グループに名前を付けすることをお勧めします。 たとえば、ヘルプデスク技術者、システム管理者、エスカレーション エンジニアのセキュリティ グループを作成できます。 次の表に示す役割を使用して、ライトハウスを管理することをお勧めします。

### <a name="example-security-groups"></a>セキュリティ グループの例

||ヘルプデスク技術者 |システム管理者 |エスカレーション エンジニア|
|--------------------|-------------|-------------|------------|
|**推奨される GDAP ロール** |<ul><li>ヘルプデスク管理者</li><li>セキュリティ閲覧者</li></ul>   |<ul><li>ユーザー管理者</li><li>認証管理者</li><li>グローバル閲覧者</li><li>Intune 管理者</li><li>セキュリティ管理者</li></ul>   |グローバル管理者  |
|**タスク** |ライトハウスで顧客情報を読み取り、制限付きアクションを実行する (ユーザー パスワードのリセットや連絡先情報の更新など)   |ライトハウス (デバイスの再起動など) で修正アクションを実行して、顧客のセキュリティを維持します。   |顧客テナントを保護するために必要な特権アクションを実行します (たとえば、侵害された管理者のサインインをブロックする)。  |

特定のアクセス許可の説明については、「組み込[Azure ADの役割」を参照してください](/azure/active-directory/roles/permissions-reference)。 パートナー固有の役割とタスクについては、「最小特権 [の役割」を参照してください](/partner-center/gdap-least-privileged-roles-by-task)。

## <a name="dap-in-lighthouse"></a>ライトハウスの DAP

DAP は、管理エージェントとヘルプデスク エージェントの 2 つの役割を持つライトハウスの顧客へのアクセスを制限します。 パートナー テナント内のユーザーが管理エージェントまたはヘルプデスク エージェントの役割を持っているか確認するには、[Azure AD - すべてのグループ] ページ[でセキュリティ グループのメンバーシップを確認](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)します。 まだ DAP が設定されている顧客を確認するには、「管理上の関係の監視とセルフサービス [の DAP の削除」を参照してください](/partner-center/dap-monitor-self-serve-removal)。

DAP と GDAP を持つお客様の場合、管理者エージェントの役割は、すべてのテナント情報を表示し、ライトハウスで任意のアクションを実行するためのアクセス許可を付与します (パートナー テナントの役割も必要とするその他のアクションについては、以下を参照してください)。 

Helpdesk Agent の役割は、すべてのテナント情報を表示し、ライトハウスで限定的なアクションを実行するアクセス許可を付与します (ユーザー パスワードのリセット、ユーザー サインインのブロック、顧客の連絡先情報と Web サイトの更新など)。

DAP とパートナー ユーザーに付与される広範なアクセス許可を考えると、できるだけ早く GDAP を採用することをお勧めします。 どちらのモデルも共存しますが、GDAP は最終的に DAP を置き換え、移行期間中は GDAP アクセス許可が DAP アクセス許可よりも優先されます。 詳細については、「GDAP に関する [よく寄せられる質問」を参照してください](/partner-center/gdap-faq)。

## <a name="other-roles-and-permissions"></a>その他の役割とアクセス許可

ライトハウスの特定のアクションでは、パートナー テナントでの役割の割り当てが必要です。 次の表に、パートナー テナントの役割と関連するアクセス許可を示します。<br><br>

| パートナーテナントの役割 | アクセス許可 |
|--|--|
| パートナー テナントのグローバル管理者 | <ul><li>[ライトハウス] にサインアップMicrosoft 365 管理センター。</li><li>初回実行時にパートナー契約の変更を受け入れる。</li><li>テナントをアクティブ化して非アクティブ化します。</li><li>タグを作成、更新、および削除します。</li><li>顧客テナントにタグを割り当て、削除します。</li></ul> |
| **microsoft.office365.supportTickets/allEntities/allTasks** というプロパティ セットが割り当てられた 1 つ以上の Azure AD ロールを持つパートナー テナント メンバー<br>(すべての役割の完全な一覧Azure AD組み込[Azure ADを参照してください](/azure/active-directory/roles/permissions-reference)。 | ライトハウス サービス要求を作成します。 |
| 次の両方の要件を *満たす* パートナー テナント メンバー。 <ul><li>**microsoft.office365.serviceHealth/allEntities/allTasks** というプロパティ セットAzure AD少なくとも 1 つの役割が割り当てられている<br>(すべての役割の完全なリストAzure AD組み込Azure AD[を参照してください。](/azure/active-directory/roles/permissions-reference)</li><li>少なくとも 1 つの DAP 委任された役割が割り当てられている (管理者エージェントまたはヘルプデスク エージェント)</li></ul> | サービス正常性情報を表示します。 |

## <a name="next-steps"></a>次の手順

役割を作成した後、追加のライトハウス ポータル セキュリティ、特に多要素認証 (MFA) を設定し、必要にAzure AD ID 管理 (PIM) を設定する必要があります。 詳細については、「Configure [Microsoft 365 Lighthouse ポータル セキュリティ」を参照してください](m365-lighthouse-configure-portal-security.md)。

## <a name="related-content"></a>関連コンテンツ

[タスク別の最小特権ロール](/partner-center/gdap-least-privileged-roles-by-task?branch=pr-en-us-2577) (記事)  
[委任された管理特権 (DAP) FAQ](/partner-center/dap-faq) (記事)  
[ユーザーに役割とアクセス許可を割り当てる](/partner-center/permissions-overview) (記事)  
[ユーザー設定のMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)  
[データのMicrosoft 365 Lighthouse](m365-lighthouse-overview.md) (記事)  
[アカウントにサインアップMicrosoft 365 Lighthouse](m365-lighthouse-sign-up.md) (記事)  
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
