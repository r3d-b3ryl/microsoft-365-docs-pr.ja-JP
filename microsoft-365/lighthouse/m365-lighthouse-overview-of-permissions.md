---
title: Microsoft 365 Lighthouseのアクセス許可の概要
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、Lighthouse のアクセス許可の要件について詳しく説明します。
ms.openlocfilehash: e03ae77f6997d3d34f926285cf7aab5cdd682c9c
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188312"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseのアクセス許可の概要

マネージド サービス プロバイダー (MSP) がMicrosoft 365 Lighthouseを使用するには、顧客テナントへの委任されたアクセスが必要です。 きめ細かな委任管理者特権 (GDAP) を使用すると、AZURE ACTIVE DIRECTORY [(Azure AD) の組み込みロール](/azure/active-directory/roles/permissions-reference)を通じて顧客にアクセスできるようにすることで、MSP に高いレベルの制御と柔軟性が提供されます。 MSP 技術者に GDAP を介してタスクごとに最も特権の少ないロールを割り当てることで、MSP と顧客の両方のセキュリティ リスクが軽減されます。 タスクごとの最小特権ロールの詳細については、「[最小特権ロール - パートナー センター](/partner-center/gdap-least-privileged-roles-by-task)」と「[Azure Active Directoryのタスクごとの最小特権ロール](/azure/active-directory/roles/delegate-by-task)」を参照してください。 顧客テナントとの GDAP リレーションシップを設定する方法の詳細については、「顧客[のサービスを管理するための詳細な管理者アクセス許可の取得 - パートナー センター](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)」を参照してください。

各グループが顧客に代わって実行する必要があるタスクに基づいて、MSP 技術者のグループにロールを割り当てることをお勧めします。 たとえば、Service Desk 技術者は、顧客テナント データを読み取るか、ユーザー パスワードをリセットするだけで済む場合があります。 これに対し、エスカレーション エンジニアは、顧客テナントのセキュリティ設定を更新するために、より修正措置を講じる必要がある場合があります。 顧客とパートナーのデータがセキュリティで保護されるように、タスクを完了するために必要な最小許容ロールを割り当てることをお勧めします。 必要に応じて、Privileged Identity Management (PIM) を使用して、グローバル管理者ロールへの時間範囲アクセスを有効にすることをお勧めします。 ユーザーにグローバル アクセスを許可しすぎる場合は、セキュリティ 上のリスクが伴います。可能な限り制限することをお勧めします。 PIM を有効にする方法の詳細については、「AZURE AD [PIM のセットアップ](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)」を参照してください。

次のセクションの表では、顧客データを読み取り、Lighthouse の顧客テナントに対してアクションを実行するためのアクセス許可を付与する GDAP ロールについて説明します。 Lighthouse エンティティ (タグや Lighthouse サービス要求など) を管理するために必要なその他のロールについては、この記事の [パートナー テナントのアクセス許可](#permissions-in-the-partner-tenant) に関するページを参照してください。

> [!NOTE]
>GDAP は現在、GDAP が一般公開される前に、パートナーがきめ細かなアクセス許可を割り当てることができるように [、テクニカル プレビュー](/partner-center/announcements/2022-february#6) (パブリック プレビュー) に入っている。 Lighthouse でアクションにアクセスまたは実行する際に問題が発生した場合は、 [既知](m365-lighthouse-known-issues.md) の問題を確認します。

## <a name="example-msp-service-tiers-recommended-gdap-roles-and-permissions"></a>MSP サービス レベルの例、推奨される GDAP ロール、およびアクセス許可

次の表に、MSP サービス レベルの例に推奨される GDAP ロールを示します。 

|| アカウント マネージャー| Service Desk の技術者 | システム管理者 | エスカレーション エンジニア|
|---|---|---|---|---|
| **推奨される GDAP ロール** |<ul><li>ヘルプデスク管理者</li></ul> |<ul><li>セキュリティ閲覧者<br>+</li><li>ヘルプデスク管理者</li></ul> |<ul><li>グローバル閲覧者<br>+</li><li>ユーザー管理者<br>+</li><li>認証管理者</li></ul> |<ul><li>グローバル閲覧者<br>+</li><li>ユーザー管理者<br>+</li><li>Intune管理者<br>+</li><li>セキュリティ管理者</li></ul>|

次の表は、MSP サービス レベルの例が、割り当てられた GDAP ロール (前の表に示す) によって決定されるさまざまな Lighthouse ページで実行できるアクションの一覧です。

| [Lighthouse] ページ | アカウント マネージャーで許可されているアクション| Service Desk の技術者が許可するアクション |システム管理者が許可するアクション | エスカレーション エンジニアが許可するアクション|
|---|---|---|---|---|
| Home  | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | 
| テナント     | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画を表示する</li></ul>  | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画を表示する</li></ul>   |  <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画を表示する</li><li>Microsoft 365 サービスの使用状況を表示する</li></ul> | <ul><li>テナントの一覧を表示する</li><li>顧客の連絡先と Web サイトを更新する</li><li>展開計画を表示する</li><li>Microsoft 365 サービスの使用状況を表示する</li></ul>  |
| ユーザー   | <ul><li>テナント レベル (ユーザー固有ではない) データを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のユーザーのパスワードをリセットする*</li></ul>  | <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のユーザーのパスワードをリセットする*</li></ul>|  <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のユーザーのパスワードをリセットする*</i><li>サインインをブロックする</li></ul>  | <ul><li>すべてのユーザー固有のデータを表示する</li><li>テナント間でユーザー アカウントを検索する</li><li>管理者以外のユーザーのパスワードをリセットする*</li><li>サインインをブロックする</li><li>侵害されたユーザーを確認する</li><li>ユーザーのリスクを無視する</li></ul> |
| デバイス    | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li><li>同期デバイス</li><li>デバイスの再起動</li><li>診断の収集</li></ul>|
| 脅威の管理  | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li><li>フル スキャンを実行する</li><li>クイック スキャンを実行する</li><li>ウイルス対策の保護を更新する</li><li>デバイスを再起動する</li></ul>|
| 基準計画    | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul>  | <ul><li>すべてのデータを表示する</li></ul> |
| Windows 365 | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> | <ul><li>すべてのデータを表示する</li></ul> |
| サービス正常性**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |
| 監査ログ**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |

*顧客テナント管理者の [パスワードをリセット](/azure/active-directory/roles/permissions-reference#password-reset-permissions) するために必要なロールを示す表については、パスワード リセットのアクセス許可を参照してください。

**サービス正常性ログと監査ログを表示するには、さまざまなロールとアクセス許可が必要です。 詳細については、「 [パートナー テナントのアクセス許可」を参照してください](#permissions-in-the-partner-tenant)。

> [!NOTE]
> 情報を表示または編集する権限がないことを示すメッセージが Lighthouse に表示された場合、アクションを実行するための適切なアクセス許可を持たないロールが割り当てられます。 実行しようとしているアクションに適切なロールを割り当てることができるパートナー テナントの管理者に連絡する必要があります。

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Lighthouse の委任された管理者特権 (DAP)

GDAP は最終的に、顧客テナントの委任されたアクセスを構成する主な方法として DAP を置き換えます。 ただし、GDAP が設定されていない場合でも、MSP 技術者は DAP を通じて付与されたヘルプデスク エージェントまたは管理者エージェントのロールを使用して Lighthouse にアクセスできます。 GDAP と DAP が共存しているお客様の場合は、GDAP を通じて MSP 技術者に付与されるロールが優先されます。 GDAP または DAP の非推奨の詳細については、日付とタイムラインに関する [GDAP のよく寄せられる質問](/partner-center/gdap-faq) または [パートナー センターのお知らせ](/partner-center/announcements/2022-march#15) を参照してください。

DAP を持ち、GDAP を持たないお客様の場合、管理者エージェント ロールは、すべてのテナント データを表示し、Lighthouse でアクションを実行するアクセス許可を付与します (パートナー テナントのロールも必要なその他のアクションについては、以下を参照してください)。

Helpdesk Agent ロールは、すべてのテナント データを表示し、ユーザー パスワードのリセット、ユーザー サインインのブロック、顧客の連絡先情報と Web サイトの更新など、Lighthouse で制限付きアクションを実行するアクセス許可を付与します。

DAP ロールを持つパートナー ユーザーに付与される広範なアクセス許可を考慮して、できるだけ早く GDAP を採用することをお勧めします。 

## <a name="permissions-in-the-partner-tenant"></a>パートナー テナントのアクセス許可

Lighthouse の特定のアクションでは、パートナー テナントでのロールの割り当てが必要です。 次の表に、パートナー テナント ロールと、関連するアクセス許可を示します。

| パートナー テナント ロール | アクセス許可 |
|--|--|
| パートナー テナントのグローバル管理者 | <ul><li>Microsoft 365 管理センターで Lighthouse にサインアップします。</li><li>初回のエクスペリエンスでパートナー契約の変更を受け入れます。</li><li>テナントをアクティブ化して非アクティブ化します。</li><li>タグを作成、更新、削除します。</li><li>顧客テナントにタグを割り当てて削除します。</li><li>監査ログを確認する</li></ul> |
| 次のプロパティ セットで割り当てられた少なくとも 1 つのAzure AD ロールを持つパートナー テナント メンバー。<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br>(Azure AD ロールの完全な一覧については、[組み込みロールAzure AD](/azure/active-directory/roles/permissions-reference)参照してください)。 | Lighthouse サービス要求を作成します。 |
| 次の *要件の両方* を満たすパートナー テナント メンバー。 <ul><li>次のプロパティ セットで少なくとも 1 つのAzure ADロールが割り当てられています。<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br>(Azure AD ロールの完全な一覧については、[組み込みロールAzure AD](/azure/active-directory/roles/permissions-reference)参照してください)。</li><li>少なくとも 1 つの DAP 委任されたロールが割り当てられている (管理者エージェントまたはヘルプデスク エージェント)</li></ul> | サービスの正常性情報を表示します。 |

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseの要件](m365-lighthouse-requirements.md) (記事)  
[委任された管理特権 (DAP) に関する FAQ](/partner-center/dap-faq) (記事)  
[Microsoft 365 LighthouseでAzure Active Directory ロールを表示する](m365-lighthouse-view-your-roles.md) (記事)  
[ユーザーにロールとアクセス許可を割り当てる](/partner-center/permissions-overview) (記事)  
[Microsoft 365 Lighthouseの概要](m365-lighthouse-overview.md) (記事)  
[Microsoft 365 Lighthouseにサインアップ](m365-lighthouse-sign-up.md)する (記事)  
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
