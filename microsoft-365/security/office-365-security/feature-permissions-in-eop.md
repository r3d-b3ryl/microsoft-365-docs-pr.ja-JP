---
title: EOP の機能アクセス許可
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: スタンドアロン アプリケーションのタスクに必要なアクセス許可についてExchange Online Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206985"
---
# <a name="permissions-in-standalone-eop"></a>スタンドアロン EOP のアクセス許可

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protectionスタンドアロン](exchange-online-protection-overview.md)

メールボックスExchange Online Protectionスタンドアロン Exchange Online (EOP) は、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用して、管理者に簡単にアクセス許可を付与します。 スタンドアロン EOP のアクセス許可機能を使用して、新しい組織を迅速に稼働できます。

ユーザーにアクセス許可を付与するには [、「EOP で管理者役割グループを管理する」を参照してください](manage-admin-role-group-permissions-in-eop.md)。

管理者全体のアクセス許可の詳細については、「Microsoft 365役割について[」を参照してください](../../admin/add-users/about-admin-roles.md)。

## <a name="role-based-permissions"></a>役割に基づくアクセス許可

ユーザーに付与する管理者のアクセス許可は、管理役割に基づいて行います。 管理役割は、特定のタスクのセットで使用できるコマンドレットを定義します。 Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell は両方ともコマンドレットを使用します。コマンドレットへのアクセスを許可すると、EAC またはスタンドアロン EOP PowerShell で関連するタスクを実行するアクセス許可がユーザーに付与されます。 たとえば、メール受信者の役割は、メール ユーザーの変更に必要なコマンドレットを定義します。

スタンドアロン EOP では、管理役割は使用可能な管理役割の唯一の種類です (エンド ユーザーの役割や役割の割り当てポリシーはありません)。

## <a name="role-groups"></a>役割グループ

ユーザーに役割を割り当てやすくするために、スタンドアロン EOP では役割グループが使用されます。 管理役割は役割グループに割り当て、役割グループのメンバーは役割に関連付けられたアクセス許可を取得します。 つまり、管理役割はユーザーに直接割り当てられていない。役割グループに割り当てられている。 このモデルを使用すると、多数の役割グループ メンバーに一度に多数の役割を割り当てることができます。 役割グループのメンバーには、メール ユーザー、メールが有効なセキュリティ グループ、管理者センターのユーザー Microsoft 365、その他の役割グループを指定できます。

次の図はユーザー、役割グループ、および役割の間の関係を示しています。

![役割、役割グループ、およびメンバー関係](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

スタンドアロン EOP で使用可能な役割グループについては、次の表で説明します。

****

|役割グループ|説明|割り当てられた既定の役割|
|---|---|---|
|ComplianceManagement|サブスクリプションに DLP 機能がある場合は、データ損失防止 (DLP) を含む、組織内のコンプライアンス設定を構成および管理します。 <p> Azure のコンプライアンス [管理者ロールの](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) メンバーはADグループのアクセス許可を自動的に取得します。|監査ログ <p> コンプライアンス管理 <p> Information Rights Management <p> アイテム保持の管理 <p> 表示専用の監査ログ <p> "View-Only Configuration/表示専用構成" <p> "View-Only Recipients/表示専用受信者"|
|ContentExplorerContentViewer|不使用。|データ分類コンテンツ ビューアー|
|ContentExplorerListViewer|不使用。|データ分類リスト ビューアー|
|HelpDesk|メール ユーザーを表示および管理します。|パスワードのリセット <p> ユーザー オプション <p> "View-Only Recipients/表示専用受信者"|
|HygieneManagement|保護機能 (スパム対策、マルウェア対策など) を管理します。|トランスポートの衛生 <p> "View-Only Configuration/表示専用構成" <p> "View-Only Recipients/表示専用受信者"|
|MailFlowAdministrator|受け入れ可能なドメインとコネクタの表示と管理|リモートドメインと受け入れドメイン <p> "View-Only Recipients/表示専用受信者"|
|OrganizationManagement|組織全体への管理者アクセスと、ほとんどすべてのタスクを実行する機能。 <p> Azure のグローバル [管理者ロールの](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) メンバーはADグループのアクセス許可を自動的に取得します。 <p> **重要**: OrganizationManagement 役割グループは強力な役割なので、組織レベルの管理タスクを実行するユーザーだけがこの役割グループのメンバーである必要があります。|マルウェア対策 <p> AntiSpam <p> 監査ログ <p> コンプライアンス管理者 <p> 動的配布グループ <p> Information Rights Management <p> "Mail Recipient Creation/メール受信者の作成" <p> Mail Recipients <p> "Message Tracking/メッセージ追跡" <p> "Migration/移行" <p> 組織のクライアント アクセス <p> 組織の構成 <p> 組織トランスポート 設定 <p> 検疫する <p> "Recipient Policies/受信者ポリシー" <p> リモートドメインと受け入れドメイン <p> パスワードのリセット <p> アイテム保持の管理 <p> 役割の管理 <p> セキュリティ管理者 <p> セキュリティ グループの作成とメンバーシップ <p> セキュリティ閲覧者 <p> Sensitivity Label Administrator <p> 監督 <p> トランスポートの衛生 <p> トランスポート ルール <p> ユーザー オプション <p> View-Onlyマルウェア対策 <p> View-Only スパム対策 <p> 表示専用の監査ログ <p> "View-Only Configuration/表示専用構成" <p> View-Only検疫 <p> "View-Only Recipients/表示専用受信者" <p> View-Only脅威インテリジェンス|
|QuarantineAdministrator|すべての受信者の検疫済みメッセージを管理します。|検疫する|
|RecipientManagement|組織内の受信者オブジェクトを作成、管理、および削除します。|動的配布グループ <p> "Mail Recipient Creation/メール受信者の作成" <p> Mail Recipients <p> "Message Tracking/メッセージ追跡" <p> "Migration/移行" <p> "Recipient Policies/受信者ポリシー" <p> パスワードのリセット|
|RecordsManagement|保持ポリシー タグ、メッセージ分類、メール フロー ルール (トランスポート ルールとも呼ばれる) などのコンプライアンス機能を構成します。|"Message Tracking/メッセージ追跡" <p> アイテム保持の管理 <p> トランスポート ルール|
|SecurityAdministrator|組織内の保護のすべての側面 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) を構成します。 <p> Azure のセキュリティ [管理者ロールの](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) メンバーはADグループのアクセス許可を自動的に取得します。|マルウェア対策 <p> AntiSpam <p> 監査ログ <p> 検疫する <p> セキュリティ管理者 <p> Sensitivity Label Administrator <p> View-Onlyマルウェア対策 <p> View-Only スパム対策 <p> 表示専用の監査ログ <p> View-Only検疫 <p> View-Only脅威インテリジェンス|
|SecurityReader|組織内のすべての保護 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) へのビュー専用アクセス。 <p> Azure のセキュリティ [リーダー ロール](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) のメンバー ADこの役割グループのアクセス許可を自動的に取得します。|セキュリティ閲覧者 <p> View-Onlyマルウェア対策 <p> View-Only スパム対策 <p> View-Only検疫 <p> View-Only脅威インテリジェンス|
|TenantAdmins|この役割グループのメンバーシップは、サービス間で同期され、一般に管理されます。 既定では、この役割グループには役割は割り当てられていない。 ただし、組織の管理役割グループのメンバーであり、これらのアクセス許可を継承します。|none|
|ViewOnlyOrganizationManagement|組織内の受信者、保護、および構成オブジェクトとそのプロパティを表示します。|コンプライアンス管理者 <p> セキュリティ管理者 <p> セキュリティ閲覧者 <p> Sensitivity Label Administrator <p> "View-Only Configuration/表示専用構成" <p> "View-Only Recipients/表示専用受信者"|
|

少数の管理者しか所属しない小規模な組織で作業する場合は、それらのユーザーを組織の管理役割グループにのみ追加する必要がある場合があります。また、他の役割グループを使用する必要が生じない場合があります。 大規模な組織で作業する場合は、受信者の構成など、特定のタスクを実行する管理者が必要になる場合があります。 このような場合は、受信者管理役割グループに 1 人の管理者を追加し、別の管理者を [組織の管理] 役割グループに追加できます。 その後、管理者は特定の領域を管理できますが、自分が責任を負う領域を管理するためのアクセス許可を持つ必要があります。

Exchange Online の組み込みの役割グループが管理者のジョブ機能と適合しない場合は、役割グループを作成して管理者に役割を追加できます。 詳細については、「スタンドアロン [EOP で役割グループを管理する」を参照してください](manage-admin-role-group-permissions-in-eop.md)。

## <a name="roles"></a>Roles

スタンドアロン EOP で使用できる組み込みの役割について、次の表で説明します。

****

|Role**|説明|既定の役割グループの割り当て|
|---|---|---|
|マルウェア対策|マルウェア対策機能の構成とレポートを表示および変更します。|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|スパム対策機能の構成とレポートを表示および変更します。|OrganizationManagement <p> SecurityAdministrator|
|監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|コンプライアンス管理者<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|データ分類コンテンツ ビューアー<sup>\*</sup>||ContentExplorerContentViewer|
|データ分類リスト ビューアー<sup>\*</sup>||
|動的配布グループ|すべての配布グループ、メールが有効なセキュリティ グループ、およびメンバーを作成および管理します。|OrganizationManagement <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|"Mail Recipient Creation/メール受信者の作成"|メール ユーザーを作成および削除します。|OrganizationManagement <p> RecipientManagement|
|Mail Recipients|既存のメール ユーザーを変更します。|OrganizationManagement <p> RecipientManagement|
|メッセージ追跡<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> レコード管理|
|移行<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|ユーザーが独自の検疫済みメッセージを表示できます。 <p> この役割はユーザーに自動的に割り当てられるので、手動で割り当てすることはできません。|none|
|組織のクライアント アクセス<sup>\*</sup>||OrganizationManagement|
|組織の構成|レポートの表示。|OrganizationManagement|
|組織トランスポート 設定<sup>\*</sup>||OrganizationManagement|
|検疫する|すべての受信者の検疫済みメッセージのすべての種類を管理します。|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|受信者ポリシー<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|リモートドメインと受け入れドメイン|リモート ドメイン、受け入れドメイン、およびコネクタを管理します。|MailFlowAdministrator <p> OrganizationManagement|
|パスワードのリセット<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|アイテム保持の管理<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|役割の管理|役割グループを作成および管理します。|OrganizationManagement|
|セキュリティ管理者|すべてのセキュリティ機能と保護機能の構成とレポートを管理します。|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|セキュリティ グループの作成とメンバーシップ|メールが有効なセキュリティ グループを作成および管理します。|OrganizationManagement|
|セキュリティ閲覧者|セキュリティ機能と保護機能の構成とレポートを表示します。|組織の管理 <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Sensitivity Label Administrator<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|監督<sup>\*</sup>||OrganizationManagement|
|トランスポートの衛生|マルウェア対策、スパム対策機能、スプーフィング対策機能を管理します。|HygieneManagement <p> OrganizationManagement|
|トランスポート ルール|メール フロー ルール (トランスポート ルールとも呼ばれる) を作成および管理します。|OrganizationManagement <p> RecordsManagement|
|ユーザー オプション|既存のメール ユーザーを変更します。|HelpDesk <p> OrganizationManagement|
|View-Onlyマルウェア対策|マルウェア対策機能の構成とレポートを表示します。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only スパム対策|スパム対策機能の構成とレポートを表示します。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|表示専用の監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|"View-Only Configuration/表示専用構成"|組織内のすべての組織とメール フロー (受信者以外) の設定を表示します。|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only検疫|すべての受信者の検疫済みメッセージを表示します。|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|"View-Only Recipients/表示専用受信者"|受信者のプロパティを表示し、メッセージ トレースを実行します。|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only脅威インテリジェンス<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> この役割は使用可能ですが、基本的にスタンドアロン EOP では何も役に立たしません。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365 EOP でのアクセス許可の設定

Microsoft 365 管理センターでユーザーを作成する場合は、グローバル管理者、サービス管理者、パスワード管理者など、さまざまな管理役割をユーザーに割り当てるかどうかを選択できます。 一部のロールは、EOP Microsoft 365管理者権限を付与しますが、すべてではありません。

> [!NOTE]
> スタンドアロン EOP 組織の作成に使用したアカウントは、グローバル管理者ロールに自動的に割り当てられます。

次の表に、Microsoft 365ロールと、対応するスタンドアロン EOP 役割グループの一覧を示します。 これらの役割の詳細については、「管理者ロールについて [」を参照してください](../../admin/add-users/about-admin-roles.md)。

****

|Microsoft 365ロール|EOP 役割グループ|
|---|---|
|Exchange 管理者|OrganizationManagement|
|グローバル管理者|OrganizationManagement <p> **注**: グローバル管理者役割と OrganizationManagement 役割グループは、特別な会社管理者役割グループを使用して関連付けされます。 会社の管理者役割グループは内部的に管理され、直接変更することはできません。|
|パスワード管理者|HelpDesk|
|グローバルリーダー|ViewOnlyOrganizationManagement|
|セキュリティ管理者|SecurityAdministrator|
|セキュリティ閲覧者|SecurityReader|
|

その他Microsoft 365役割には、対応する EOP 役割グループが存在し、EOP の管理アクセス許可を付与しない場合があります。 ユーザーにロールを割り当てるMicrosoft 365詳細については、「管理者ロールの割り当て[」を参照してください](../../admin/add-users/assign-admin-roles.md)。

ユーザーは、EOP で管理者の権限を付与できます。ユーザーは、ユーザーの役割にMicrosoft 365できます。 これを行うには、ユーザーを EOP 役割グループのメンバーとして追加します。 ユーザーは EOP でアクセス許可を取得しますが、他のワークロードではアクセス許可Microsoft 365取得します。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。

- EAC で、[アクセス許可] **[管理者** の役割] に移動し、役割グループが一覧表示 (または一 \> 覧に表示されていない) を確認します。 役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] アイコンをクリックして設定 ![ ](../../media/ITPro-EAC-EditIcon.png) を確認します。

- PowerShell Exchange Online、役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) か確認し、設定を \<Role Group Name\> 確認します。

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```