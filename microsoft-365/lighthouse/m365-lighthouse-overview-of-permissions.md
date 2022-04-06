---
title: ユーザーのアクセス許可のMicrosoft 365 Lighthouse
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
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouse、ライトハウスのアクセス許可の要件について説明します。
ms.openlocfilehash: 25f38b8cbc0c6815139fd6afd3616cfaa7df48e1
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595415"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>ユーザーのアクセス許可のMicrosoft 365 Lighthouse

Managed Service Providers (MSP) が顧客テナントを使用するには、顧客テナントへの委任されたアクセスMicrosoft 365 Lighthouse。 詳細な委任管理者特権 (GDAP) は、Azure Active Directory (Azure AD) 組み込みロールを介して顧客アクセスを提供することで、MSP に高いレベルの制御と柔軟性[を与える](/azure/active-directory/roles/permissions-reference)。 GDAP を介してタスク別に最小特権ロールを MSP 技術者に割り当てると、MSP と顧客の両方のセキュリティ リスクが軽減されます。 タスク別の最小特権ロールの詳細については、「最小特権ロール [-](/partner-center/gdap-least-privileged-roles-by-task) パートナー センター」および「タスク別最小特権[ロール](/azure/active-directory/roles/delegate-by-task)」を参照Azure Active Directory。 顧客テナントとの GDAP リレーションシップの設定の詳細については、「顧客のサービスを管理するための詳細な管理者アクセス許可を取得する [- パートナー センター」を参照してください。](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

各グループが顧客に代わって実行する必要があるタスクに基づいて、MSP 技術者のグループに役割を割り当てすることをお勧めします。 たとえば、Service Desk 技術者は、お客様のテナント データの読み取りやユーザー パスワードのリセットが必要な場合があります。 これに対し、エスカレーション エンジニアは、顧客テナントのセキュリティ設定を更新するために、より修正的なアクションを実行する必要がある場合があります。 顧客とパートナーのデータを安全に保つには、タスクを完了するために必要な最小限の割り当てロールを割り当てるのがベスト プラクティスです。 必要に応じて、Privileged Identity Management (PIM) を使用してグローバル管理者ロールへの時間範囲のアクセスを有効にすることをお勧めします。 多くのユーザーにグローバル アクセスを与えることはセキュリティリスクであり、可能な限り制限することをお勧めします。 PIM を有効にする方法の詳細については、「PIM のセットアップ[」をAzure ADしてください。](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

次のセクションの表では、どの GDAP ロールが、顧客データを読み取り、ライトハウスの顧客テナントに対してアクションを実行するためのアクセス許可を付与するのかについて説明します。 ライト [ハウス エンティティの管理に](#permissions-in-the-partner-tenant) 必要な追加の役割 (タグやライトハウス サービス要求など) については、この記事の「パートナー テナントのアクセス許可」を参照してください。

> [!NOTE]
>GDAP は現在 [テクニカル プレビュー (](/partner-center/announcements/2022-february#6) パブリック プレビュー) で、パートナーが GDAP を一般に利用できる前に、詳細なアクセス許可を割り当て可能です。 ライト [ハウスで操作](m365-lighthouse-known-issues.md) にアクセスまたは実行する際に問題が発生している場合は、[既知の問題] を確認します。

## <a name="example-msp-service-tiers-and-recommended-gdap-roles"></a>MSP サービス層と推奨される GDAP ロールの例

次の表に、MSP サービス層の例として推奨される GDAP ロールと、それらの役割が異なるライトハウス ページで実行できるアクションを示します。

|| AccountManagers&nbsp;| ServiceDeskTechnician&nbsp;&nbsp; |SystemAdministrators&nbsp; | EscalationEngineers&nbsp;|
|---|---|---|---|---|
| **推奨される GDAP ロール** |<ul><li>ヘルプデスク管理者</li></ul> |<ul><li>セキュリティ閲覧者<br>+</li><li>ヘルプデスク管理者</li></ul> |<ul><li>グローバル閲覧者<br>+</li><li>ユーザー管理者<br>+</li><li>認証管理者</li></ul> |<ul><li>グローバル閲覧者<br>+</li><li>ユーザー管理者<br>+</li><li>Intune管理者<br>+</li><li>セキュリティ管理者</li></ul>|
|**ライト&nbsp;ハウスpageallowedactions&nbsp;+&nbsp;&nbsp;**  |
| **ホーム**  | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | 
| **Tenants**     | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示</li></ul>  | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示</li></ul>   |  <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示</li><li>サービスMicrosoft 365を表示する</li></ul> | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画の表示</li><li>サービスMicrosoft 365を表示する</li></ul>  |
| **Users**   | <ul><li>テナント レベル (ユーザー固有ではない) データの表示</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のパスワードのリセット*</li></ul>  | <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のパスワードのリセット*</li></ul>|  <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のパスワードのリセット*</i><li>サインインをブロックする</li></ul>  | <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のパスワードのリセット*</li><li>サインインをブロックする</li><li>侵害されたユーザーを確認する</li><li>ユーザーのリスクを却下する</li></ul> |
| **Devices**    | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li><li>同期デバイス</li><li>デバイスの再起動</li><li>診断の収集</li></ul>|
| **脅威の管理**  | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li><li>フル スキャンの実行</li><li>クイック スキャンの実行</li><li>ウイルス対策保護の更新</li><li>デバイスを再起動する</li></ul>|
| **基準計画**    | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul>  | <ul><li>すべてのデータを表示する</li></ul> |
| **Windows 365** | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> |
| **サービス正常性****|  
|**監査ログ****|

*顧客テナント [管理者のパスワード](/azure/active-directory/roles/permissions-reference#password-reset-permissions) のリセットに必要な役割を一覧表示する表については、「パスワードのリセットのアクセス許可」を参照してください。

**サービスの正常性と監査ログを表示するには、他の役割とアクセス許可が必要です。 詳細については、「パートナー テナント [のアクセス許可」を参照してください](#permissions-in-the-partner-tenant)。

> [!NOTE]
> 情報を表示または編集する権限が与えられていないというメッセージがライトハウスに表示された場合は、アクションを実行するための適切なアクセス許可を持つロールが割り当てられます。 実行しようとしているアクションに適切な役割を割り当てできるパートナー テナントの管理者にアクセスする必要があります。

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>ライトハウスの委任管理者特権 (DAP)

GDAP は、最終的に DAP をプライマリ メソッドとして置き換え、顧客テナントの委任アクセスを構成します。 ただし、GDAP が設定されていない場合でも、MSP 技術者は DAP を介して付与されたヘルプデスク エージェントまたは管理エージェントの役割を使用して、ライトハウスにアクセスできます。 GDAP と DAP が共存しているお客様の場合、GDAP を通じて MSP 技術者に付与される役割が優先されます。 GDAP または DAP 非推奨の詳細については、「[GDAP](/partner-center/gdap-faq) に関するよく寄せられる質問」または[](/partner-center/announcements/2022-march#15)「日付とタイムラインに関するパートナー センターのお知らせ」を参照してください。

DAP と GDAP を持つお客様の場合、Admin Agent ロールは、すべてのテナント データを表示し、ライトハウスで任意のアクションを実行するためのアクセス許可を付与します (パートナー テナントの役割も必要とするその他のアクションについては、以下を参照してください)。

Helpdesk Agent の役割は、すべてのテナント データを表示し、ユーザー パスワードのリセット、ユーザー サインインのブロック、顧客の連絡先情報と Web サイトの更新など、ライトハウスで限定的なアクションを実行するためのアクセス許可を付与します。

DAP ロールを持つパートナー ユーザーに付与される広範なアクセス許可を考えると、できるだけ早く GDAP を採用することをお勧めします。 

## <a name="permissions-in-the-partner-tenant"></a>パートナー テナントのアクセス許可

ライトハウスの特定のアクションでは、パートナー テナントでの役割の割り当てが必要です。 次の表に、パートナー テナントの役割と関連するアクセス許可を示します。

| パートナーテナントの役割 | アクセス許可 |
|--|--|
| パートナー テナントのグローバル管理者 | <ul><li>[ライトハウス] にサインアップMicrosoft 365 管理センター。</li><li>初回実行時にパートナー契約の変更を受け入れる。</li><li>テナントをアクティブ化して非アクティブ化します。</li><li>タグを作成、更新、および削除します。</li><li>顧客テナントにタグを割り当て、削除します。</li></ul> |
| 次のプロパティ セットに割り当てられているAzure AD 1 つ以上のパートナー テナント メンバー。<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br>(すべての役割の完全な一覧Azure AD組み込[Azure ADを参照](/azure/active-directory/roles/permissions-reference)してください)。 | ライトハウス サービス要求を作成します。 |
| 次の両方の要件を *満たす* パートナー テナント メンバー。 <ul><li>次のプロパティ セットにAzure ADロールが少なくとも 1 つ割り当てられている。<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br>(すべての役割の完全な一覧Azure AD組み込[Azure ADを参照](/azure/active-directory/roles/permissions-reference)してください)。</li><li>少なくとも 1 つの DAP 委任された役割が割り当てられている (管理者エージェントまたはヘルプデスク エージェント)</li></ul> | サービス正常性情報を表示します。 |

## <a name="related-content"></a>関連コンテンツ

[ユーザー設定のMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)  
[委任された管理特権 (DAP) FAQ](/partner-center/dap-faq) (記事)  
[ユーザーに役割とアクセス許可を割り当てる](/partner-center/permissions-overview) (記事)  
[データのMicrosoft 365 Lighthouse](m365-lighthouse-overview.md) (記事)  
[アカウントにサインアップMicrosoft 365 Lighthouse](m365-lighthouse-sign-up.md) (記事)  
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
