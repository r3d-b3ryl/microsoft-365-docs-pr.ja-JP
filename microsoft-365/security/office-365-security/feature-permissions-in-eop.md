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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: スタンドアロン Exchange Online Protection のタスクに必要なアクセス許可について学習する
ms.openlocfilehash: f9c0f0549ba5a0a65fa3bbe3af1afbfddc6e735c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826627"
---
# <a name="permissions-in-standalone-eop"></a>スタンドアロン EOP のアクセス許可

Exchange Online メールボックスを持たないスタンドアロン Exchange Online Protection (EOP) では、役割ベースのアクセス制御 (RBAC) のアクセス許可モデルを使用して、管理者に簡単にアクセス許可を与えられて行います。 スタンドアロン EOP のアクセス許可機能を使用して、新しい組織の動作を迅速に開始できます。

ユーザーにアクセス許可を付与するには [、「EOP で管理役割グループの管理」を参照してください](manage-admin-role-group-permissions-in-eop.md)。

Microsoft 365 のアクセス許可の詳細については、「管理者ロールについて [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="role-based-permissions"></a>役割に基づくアクセス許可

ユーザーに付与する管理者アクセス許可は、管理役割に基づき持されます。 管理役割は、特定のタスク セットに使用できるコマンドレットを定義します。 Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell はコマンドレットのどちらも使用しているため、コマンドレットへのアクセスを許可すると、ユーザーに EAC またはスタンドアロン EOP PowerShell で関連タスクを実行するアクセス許可が付与されます。 たとえば、"Mail Recipients/メール受信者" 役割は、メール ユーザーの変更に必要なコマンドレットを定義します。

スタンドアロン EOP では、使用できる管理役割の種類は管理役割だけです (エンド ユーザー役割や役割割り当てポリシーはない)。

## <a name="role-groups"></a>役割グループ

ユーザーへの役割の割り当てを容易にするために、スタンドアロン EOP では役割グループを使用します。 管理役割が役割グループに割り当てられ、役割グループのメンバーは、その役割に関連付けられているアクセス許可を取得します。 つまり、管理役割は直接ユーザーに割り当てられていないといいます。役割グループに割り当てられます。 このモデルでは、多数のロールを多くの役割グループのメンバーに一度に割り当てることができます。 役割グループのメンバーには、メール ユーザー、メールが有効なセキュリティ グループ、Microsoft 365 管理センターのユーザー、およびその他の役割グループがあります。

次の図はユーザー、役割グループ、および役割の間の関係を示しています。

![役割、役割グループ、およびメンバー関係](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

スタンドアロン EOP で使用可能な役割グループについて、次の表で説明します。

****

|役割グループ|説明|既定のロールが割り当てられている|
|---|---|---|
|ComplianceManagement|サブスクリプションに DLP 機能が含まれる場合は、データ損失防止 (DLP) を含む組織内のコンプライアンス設定を構成して管理します。 <br/><br/> Azure の [コンプライアンス管理者ロールの](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) メンバーはADがこの役割グループのアクセス許可を自動的に取得します。|監査ログ <br/><br/> コンプライアンス管理 <br/><br/> Information Rights Management <br/><br/> 保持管理 <br/><br/> 表示専用の監査ログ <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|ContentExplorerContentViewer|不使用。|データ分類コンテンツ ビューアー|
|ContentExplorerListViewer|不使用。|データ分類リスト ビューアー|
|HelpDesk|メール ユーザーの表示と管理。|パスワードのリセット <br/><br/> ユーザー オプション <br/><br/> "View-Only Recipients/表示専用受信者"|
|HygieneManagement|保護機能 (スパム対策、マルウェア対策など) を管理します。|Transport Hygiene <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|MailFlowAdministrator|承認済みドメインとコネクタを表示および管理する|リモートおよび承認済みドメイン <br/><br/> "View-Only Recipients/表示専用受信者"|
|OrganizationManagement|組織全体への管理者アクセスと、ほぼすべてのタスクを実行する機能。 <br/><br/> Azure の [グローバル管理者ロールのメンバー](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) は、自動的にこの役割 ADグループのアクセス許可を取得します。 <br/><br/> **重要**: 組織の管理 役割グループは強力な役割であるため、組織レベルの管理タスクを実行するユーザーのみをこの役割グループのメンバーにする必要があります。|マルウェア対策 <br/><br/> AntiSpam <br/><br/> 監査ログ <br/><br/> コンプライアンス管理者 <br/><br/> 動的配布グループ <br/><br/> Information Rights Management <br/><br/> "Mail Recipient Creation/メール受信者の作成" <br/><br/> Mail Recipients <br/><br/> "Message Tracking/メッセージ追跡" <br/><br/> "Migration/移行" <br/><br/> 組織クライアント アクセス <br/><br/> 組織の構成 <br/><br/> 組織のトランスポート設定 <br/><br/> Quarantine <br/><br/> "Recipient Policies/受信者ポリシー" <br/><br/> リモートおよび承認済みドメイン <br/><br/> パスワードのリセット <br/><br/> 保持管理 <br/><br/> 役割管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティ グループの作成とメンバーシップ <br/><br/> セキュリティ閲覧者 <br/><br/> 機密ラベル管理者 <br/><br/> 監督 <br/><br/> Transport Hygiene <br/><br/> トランスポート ルール <br/><br/> ユーザー オプション <br/><br/> 表示のみのマルウェア対策 <br/><br/> 表示のみのスパム対策 <br/><br/> 表示専用の監査ログ <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> 表示専用の検疫 <br/><br/> "View-Only Recipients/表示専用受信者" <br/><br/> 表示専用脅威インテリジェンス|
|QuarantineAdministrator|すべての受信者の検疫済みメッセージを管理します。|Quarantine|
|RecipientManagement|組織内の受信者オブジェクトを作成、管理、削除します。|動的配布グループ <br/><br/> "Mail Recipient Creation/メール受信者の作成" <br/><br/> Mail Recipients <br/><br/> "Message Tracking/メッセージ追跡" <br/><br/> "Migration/移行" <br/><br/> "Recipient Policies/受信者ポリシー" <br/><br/> パスワードのリセット|
|RecordsManagement|アイテム保持ポリシー タグ、メッセージの分類、メール フロー ルール (トランスポート ルールとも呼ばれる) などのコンプライアンス機能を構成します。|"Message Tracking/メッセージ追跡" <br/><br/> 保持管理 <br/><br/> トランスポート ルール|
|SecurityAdministrator|組織内の保護のすべての側面 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) を構成します。 <br/><br/> Azure AD の [セキュリティ管理者ロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) のメンバーはADがこの役割グループのアクセス許可を自動的に取得します。|マルウェア対策 <br/><br/> AntiSpam <br/><br/> 監査ログ <br/><br/> Quarantine <br/><br/> セキュリティ管理者 <br/><br/> 機密ラベル管理者 <br/><br/> 表示のみのマルウェア対策 <br/><br/> 表示のみのスパム対策 <br/><br/> 表示専用の監査ログ <br/><br/> 表示専用の検疫 <br/><br/> 表示専用脅威インテリジェンス|
|SecurityReader|組織の保護のすべての側面 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) に対する表示専用アクセス。 <br/><br/> この役割グループ [のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) を自動的に取得ADAzure AD のセキュリティ閲覧者ロールのメンバー。|セキュリティ閲覧者 <br/><br/> 表示のみのマルウェア対策 <br/><br/> 表示のみのスパム対策 <br/><br/> 表示専用の検疫 <br/><br/> 表示専用脅威インテリジェンス|
|TenantAdmins|この役割グループのメンバーシップは、複数のサービス間で同期され、一元的に管理されます。 既定では、この役割グループには役割は割り当てられていません。 ただし、これは Organization Management 役割グループのメンバーとなら、それらのアクセス許可を継承します。|なし|
|ViewOnlyOrganizationManagement|組織内の受信者、保護、構成オブジェクトとそのプロパティを表示します。|コンプライアンス管理者 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティ閲覧者 <br/><br/> 機密ラベル管理者 <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|

2 名の管理者しかいない小規模な組織の場合は、それらのユーザーを組織の管理 役割グループにのみ追加し、他の役割グループの使用は不要である可能性があります。 大規模な組織では、受信者構成などの特定のタスクを実行する管理者がいつものである可能性があります。 このような場合は、1 名の管理者を Recipient Management 役割グループに、もう 1 つの管理者を組織の管理 役割グループに追加できます。 これにより、そうした管理者は、特定の領域を管理できますが、各メンバーが対応する必要のない領域を管理するアクセス許可は持つわけでもません。

Exchange Online の組み込みの役割グループが管理者のジョブ機能と適合しない場合は、役割グループを作成して管理者に役割を追加できます。 詳細については、「スタンドアロン [EOP の役割グループの管理」を参照してください](manage-admin-role-group-permissions-in-eop.md)。

## <a name="roles"></a>ロール

スタンドアロン EOP で使用できる組み込みの役割を次の表に示します。

****

|ロール**|説明|既定の役割グループの割り当て|
|---|---|---|
|マルウェア対策|マルウェア対策機能の構成とレポートを表示および変更します。|OrganizationManagement <br/><br/> SecurityAdministrator|
|AntiSpam|スパム対策機能の構成およびレポートを表示および変更します。|OrganizationManagement <br/><br/> SecurityAdministrator|
|監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|コンプライアンス管理者<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|データ分類コンテンツ ビューアー<sup>\*</sup>||ContentExplorerContentViewer|
|データ分類リスト ビューアー<sup>\*</sup>||
|動的配布グループ|すべての配布グループ、メールが有効なセキュリティ グループ、およびメンバーを作成して管理します。|OrganizationManagement <br/><br/> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|"Mail Recipient Creation/メール受信者の作成"|メール ユーザーの作成と削除。|OrganizationManagement <br/><br/> RecipientManagement|
|Mail Recipients|既存のメール ユーザーを変更する。|OrganizationManagement <br/><br/> RecipientManagement|
|メッセージ追跡<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> レコード管理|
|移行<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|ユーザーが自分の検疫済みメッセージを表示できます。 <br/><br/> この役割は、ユーザーに自動的に割り当てられ、手動で割り当てられるものはできません。|なし|
|組織クライアント アクセス<sup>\*</sup>||OrganizationManagement|
|組織の構成|レポートの表示。|OrganizationManagement|
|組織のトランスポート設定<sup>\*</sup>||OrganizationManagement|
|Quarantine|すべての受信者の検疫済みメッセージのすべての種類を管理します。|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|受信者ポリシー<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|リモートおよび承認済みドメイン|リモート ドメイン、承認済みドメイン、コネクタを管理します。|MailFlowAdministrator <br/><br/> OrganizationManagement|
|パスワードのリセット<sup>\*</sup>||HelpDesk <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|保持管理<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> RecordsManagement|
|役割管理|役割グループの作成と管理。|OrganizationManagement|
|セキュリティ管理者|すべてのセキュリティ機能と保護機能の構成およびレポートを管理します。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|セキュリティ グループの作成とメンバーシップ|メールが有効なセキュリティ グループの作成と管理。|OrganizationManagement|
|セキュリティ閲覧者|セキュリティおよび保護機能の構成およびレポートを表示する。|組織管理 <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|機密ラベル管理者<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|監督<sup>\*</sup>||OrganizationManagement|
|Transport Hygiene|マルウェア対策、スパム対策機能、およびスプーフィング対策機能を管理します。|HygieneManagement <br/><br/> OrganizationManagement|
|トランスポート ルール|メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して管理します。|OrganizationManagement <br/><br/> RecordsManagement|
|ユーザー オプション|既存のメール ユーザーを変更する。|HelpDesk <br/><br/> OrganizationManagement|
|表示のみのマルウェア対策|マルウェア対策機能の構成とレポートを表示します。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|表示のみのスパム対策|スパム対策機能の構成とレポートを表示する。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|表示専用の監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|"View-Only Configuration/表示専用構成"|組織内のすべての組織およびメール フロー (受信者以外の) 設定を表示します。|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|表示専用の検疫|すべての受信者のすべての検疫済みメッセージを表示する。|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|"View-Only Recipients/表示専用受信者"|受信者のプロパティを表示し、メッセージの追跡を実行します。|ComplianceManagement <br/><br/> HelpDesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|表示専用脅威インテリジェンス<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> この役割は利用可能ですが、基本的にスタンドアロン EOP では役立つ機能を何もありません。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>スタンドアロン EOP での Microsoft 365 のアクセス許可

Microsoft 365 管理センターでユーザーを作成するときには、全体管理者、サービス管理者、パスワード管理者などのさまざまな管理役割をユーザーに割り当てるかどうかを選択できます。 すべてでも一部の Microsoft 365 役割は、ユーザーに EOP の管理アクセス許可を付与します。

> [!NOTE]
> スタンドアロン EOP 組織を作成するために使用したアカウントは、自動的にグローバル管理者ロールに割り当てられます。

次の表は、Microsoft 365 の役割と、その役割が対応するスタンドアロン EOP 役割グループを示しています。 これらの役割の詳細については、「管理者ロールについて [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

****

|Microsoft 365 の役割|EOP 役割グループ|
|---|---|
|Exchange 管理者|OrganizationManagement|
|グローバル管理者|OrganizationManagement <br/><br/> **注**: グローバル管理者役割と "OrganizationManagement/組織管理" 役割グループは、特殊な "Company Administrator/会社の管理者" 役割グループを使用して関連付けられます。 "Company Administrator/会社の管理者" 役割グループは内部管理下で、直接変更できません。|
|パスワード管理者|HelpDesk|
|グローバルリーダー|ViewOnlyOrganizationManagement|
|セキュリティ管理者|SecurityAdministrator|
|セキュリティ閲覧者|SecurityReader|
|

その他の Microsoft 365 役割には、対応する EOP 役割グループがなっており、EOP の管理アクセス許可は付与されません。 Microsoft 365 役割をユーザーに割り当てる方法の詳細については、「管理者ロールを割り [当てる」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)。

ユーザーを Microsoft 365 役割に追加しなくても、EOP の管理権限をユーザーに付与できます。 これを行うには、EOP 役割グループのメンバーとしてユーザーを追加します。 ユーザーは EOP でアクセス許可を取得しますが、他の Microsoft 365 ワークロードのアクセス許可を取得しません。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

役割グループが正常にコピーされたことを確認するには、次の手順のいずれかを実行します。

- EAC で、[アクセス許可の管理役割 **]** \> **に移動し**、役割グループが一覧に表示されている (または一覧にない) ことを確認します。 役割グループを選択し、[詳細] ウィンドウで設定を確認するか、[編集] **アイコンをクリック** ![ ](../../media/ITPro-EAC-EditIcon.png) して設定を確認します。

- Exchange Online PowerShell で、役割 \<Role Group Name\> グループの名前に置き換え、次のコマンドを実行して、役割グループが存在するかどうかを確認 (存在しない) ため、設定を確認します。

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
