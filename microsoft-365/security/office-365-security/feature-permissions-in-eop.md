---
title: EOP の機能アクセス許可
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: スタンドアロンの Exchange Online Protection のタスクに必要なアクセス許可について説明します。
ms.openlocfilehash: 0138bd4716d831a33fa4b5a0fbdce0f154d62776
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208881"
---
# <a name="permissions-in-standalone-eop"></a>スタンドアロン EOP のアクセス許可

スタンドアロン Exchange Online Protection (EOP) Exchange Online のメールボックスがない場合は、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用して、管理者に簡単にアクセス許可を付与します。 スタンドアロン EOP のアクセス許可機能を使用して、新しい組織をすばやく稼働させることができます。

ユーザーにアクセス許可を付与するには、「 [Manage admin role groups IN EOP](manage-admin-role-group-permissions-in-eop.md)」を参照してください。

Microsoft 365 全体のアクセス許可の詳細については、「[管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)て」を参照してください。

## <a name="role-based-permissions"></a>役割に基づくアクセス許可

ユーザーに付与する管理者のアクセス許可は、管理役割に基づいています。 管理役割は、特定のタスクのセットに使用できるコマンドレットを定義します。 Exchange 管理センター (EAC) とスタンドアロン EOP PowerShell はどちらもコマンドレットを使用するため、コマンドレットへのアクセスを許可すると、EAC またはスタンドアロンの EOP PowerShell で関連するタスクを実行するためのアクセス許可がユーザーに与えられます。 たとえば、メール受信者の役割では、メールユーザーの変更に必要なコマンドレットが定義されています。

スタンドアロン EOP では、管理役割は、使用できる唯一の種類の管理役割です (エンドユーザーの役割または役割の割り当てポリシーはありません)。

## <a name="role-groups"></a>役割グループ

ユーザーへの役割の割り当てが容易になるように、スタンドアロン EOP は役割グループを使用します。 管理役割は役割グループに割り当てられ、役割グループのメンバーは役割に関連付けられているアクセス許可を取得します。 言い換えると、管理役割はユーザーに直接割り当てられません。役割グループに割り当てられている。 このモデルでは、一度に多数の役割グループのメンバーに多数の役割を割り当てることができます。 役割グループのメンバーには、メールユーザー、メールが有効なセキュリティグループ、Microsoft 365 管理センターのユーザー、およびその他の役割グループを指定できます。

次の図はユーザー、役割グループ、および役割の間の関係を示しています。

![役割、役割グループ、およびメンバー関係](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

次の表では、スタンドアロン EOP で使用可能な役割グループについて説明します。

||||
|---|---|---|
|**役割グループ**|**説明**|**割り当てられた既定の役割**|
|ComplianceManagement|サブスクリプションに DLP 機能がある場合は、データ損失防止 (DLP) を含む、組織内のコンプライアンス設定を構成および管理します。 <br/><br/> Azure AD の[コンプライアンス管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator)ロールのメンバーは、この役割グループのアクセス許可を自動的に取得します。|監査ログ <br/><br/> コンプライアンス管理 <br/><br/> Information Rights Management <br/><br/> 保持管理 <br/><br/> 表示のみの監査ログ <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|ContentExplorerContentViewer|不使用。|データ分類コンテンツビューアー|
|ContentExplorerListViewer|不使用。|データ分類リストビューアー|
|問い合わせ|メールユーザーを表示および管理します。|パスワードのリセット <br/><br/> ユーザーオプション <br/><br/> "View-Only Recipients/表示専用受信者"|
|HygieneManagement|保護機能 (スパム対策、マルウェア対策など) を管理します。|トランスポートの検疫 <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|MailFlowAdministrator|承認済みドメインおよびコネクタの表示と管理|リモートドメインと承認済みドメイン <br/><br/> "View-Only Recipients/表示専用受信者"|
|組織|組織全体への管理者アクセスと、ほぼすべてのタスクを実行する機能。 <br/><br/> Azure AD の[グローバル管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)ロールのメンバーは、この役割グループのアクセス許可を自動的に取得します。 <br/><br/> **重要**: "組織" 管理役割グループは強力な役割であるため、組織レベルの管理タスクを実行するユーザーのみがこの役割グループのメンバーになる必要があります。|マルウェア対策 <br/><br/> スパム対策 <br/><br/> 監査ログ <br/><br/> コンプライアンス管理者 <br/><br/> 動的配布グループ <br/><br/> Information Rights Management <br/><br/> "Mail Recipient Creation/メール受信者の作成" <br/><br/> Mail Recipients <br/><br/> "Message Tracking/メッセージ追跡" <br/><br/> "Migration/移行" <br/><br/> 組織のクライアントアクセス <br/><br/> 組織の構成 <br/><br/> 組織のトランスポート設定 <br/><br/> Quarantine <br/><br/> "Recipient Policies/受信者ポリシー" <br/><br/> リモートドメインと承認済みドメイン <br/><br/> パスワードのリセット <br/><br/> 保持管理 <br/><br/> 役割管理 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティグループの作成とメンバーシップ <br/><br/> セキュリティ閲覧者 <br/><br/> 機密ラベル管理者 <br/><br/> 監督 <br/><br/> トランスポートの検疫 <br/><br/> トランスポート ルール <br/><br/> ユーザーオプション <br/><br/> 表示専用のマルウェア対策 <br/><br/> 表示専用スパム対策 <br/><br/> 表示のみの監査ログ <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> 表示のみの検疫 <br/><br/> "View-Only Recipients/表示専用受信者" <br/><br/> 表示のみの脅威インテリジェンス|
|QuarantineAdministrator|すべての受信者の検疫済みメッセージを管理します。|Quarantine|
|受信者管理|組織内の受信者オブジェクトを作成、管理、および削除します。|動的配布グループ <br/><br/> "Mail Recipient Creation/メール受信者の作成" <br/><br/> Mail Recipients <br/><br/> "Message Tracking/メッセージ追跡" <br/><br/> "Migration/移行" <br/><br/> "Recipient Policies/受信者ポリシー" <br/><br/> パスワードのリセット|
|Ecm.recordsmanagement|アイテム保持ポリシータグ、メッセージ分類、メールフロールール (トランスポートルールとも呼ばれる) などのコンプライアンス機能を構成します。|"Message Tracking/メッセージ追跡" <br/><br/> 保持管理 <br/><br/> トランスポート ルール|
|SecurityAdministrator|組織内の保護のすべての側面 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) を構成します。 <br/><br/> Azure AD の[セキュリティ管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)ロールのメンバーは、この役割グループのアクセス許可を自動的に取得します。|マルウェア対策 <br/><br/> スパム対策 <br/><br/> 監査ログ <br/><br/> Quarantine <br/><br/> セキュリティ管理者 <br/><br/> 機密ラベル管理者 <br/><br/> 表示専用のマルウェア対策 <br/><br/> 表示専用スパム対策 <br/><br/> 表示のみの監査ログ <br/><br/> 表示のみの検疫 <br/><br/> 表示のみの脅威インテリジェンス|
|SecurityReader|組織内の保護のすべての側面 (スパム対策、マルウェア対策、スプーフィング対策、検疫など) へのアクセスを表示のみ許可します。 <br/><br/> Azure AD の[セキュリティリーダー](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader)ロールのメンバーは、この役割グループのアクセス許可を自動的に取得します。|セキュリティ閲覧者 <br/><br/> 表示専用のマルウェア対策 <br/><br/> 表示専用スパム対策 <br/><br/> 表示のみの検疫 <br/><br/> 表示のみの脅威インテリジェンス|
|TenantAdmins|この役割グループのメンバーシップは、複数のサービス間で同期され、一元管理されます。 既定では、この役割グループには役割が割り当てられていません。 ただし、組織の管理役割グループのメンバーであり、アクセス許可が継承されます。|なし|
|Viewonly組織管理|組織内の受信者、保護、および構成オブジェクトとそのプロパティを表示します。|コンプライアンス管理者 <br/><br/> セキュリティ管理者 <br/><br/> セキュリティ閲覧者 <br/><br/> 機密ラベル管理者 <br/><br/> "View-Only Configuration/表示専用構成" <br/><br/> "View-Only Recipients/表示専用受信者"|
|

管理者が数が少ない小規模な組織で作業する場合は、それらのユーザーを組織の管理役割グループにのみ追加する必要があり、その他の役割グループを使用する必要がない場合があります。 大規模な組織で作業している場合は、受信者の構成など、特定のタスクを実行する管理者がいる可能性があります。 そのような場合は、1人の管理者を "Recipient Management/受信者管理" 役割グループに、もう1人の管理者を Organization Management 役割グループに追加することができます。 その後、管理者は特定の領域を管理できるようになりますが、担当していない領域を管理するためのアクセス許可はありません。

Exchange Online の組み込みの役割グループが管理者のジョブ機能と適合しない場合は、役割グループを作成して管理者に役割を追加できます。 詳細については、「 [Manage role groups in STANDALONE EOP](manage-admin-role-group-permissions-in-eop.md)」を参照してください。

## <a name="roles"></a>ロール

次の表では、スタンドアロン EOP で使用できる組み込みの役割について説明します。

||||
|---|---|---|
|**ロール**|**説明**|**既定の役割グループの割り当て**|
|マルウェア対策|マルウェア対策機能の構成とレポートを表示および変更します。|組織 <br/><br/> SecurityAdministrator|
|スパム対策|スパム対策機能の構成とレポートを表示および変更します。|組織 <br/><br/> SecurityAdministrator|
|監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <br/><br/> 組織 <br/><br/> SecurityAdministrator|
|コンプライアンス管理者<sup>\*</sup>||ComplianceManagement <br/><br/> 組織 <br/><br/> Viewonly組織管理|
|データ分類コンテンツビューアー<sup>\*</sup>||ContentExplorerContentViewer|
|データ分類リストビューアー<sup>\*</sup>||
|動的配布グループ|すべての配布グループ、メールが有効なセキュリティグループ、およびメンバーを作成して管理します。|組織 <br/><br/> 受信者管理|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <br/><br/> 組織|
|"Mail Recipient Creation/メール受信者の作成"|メールユーザーを作成および削除します。|組織 <br/><br/> 受信者管理|
|Mail Recipients|既存のメールユーザーを変更します。|組織 <br/><br/> 受信者管理|
|メッセージ追跡<sup>\*</sup>||組織 <br/><br/> 受信者管理 <br/><br/> レコード管理|
|転送<sup>\*</sup>||組織 <br/><br/> 受信者管理|
|MyBaseOptions|ユーザーが自分の検疫済みメッセージを表示できるようにします。 <br/><br/> この役割はユーザーに自動的に割り当てられるため、手動で割り当てることはできません。|なし|
|組織のクライアントアクセス<sup>\*</sup>||組織|
|組織の構成|レポートの表示。|組織|
|組織のトランスポート設定<sup>\*</sup>||組織|
|Quarantine|すべての受信者のすべての種類の検疫済みメッセージを管理します。|組織 <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|受信者ポリシー<sup>\*</sup>||組織 <br/><br/> 受信者管理|
|リモートドメインと承認済みドメイン|リモートドメイン、承認済みドメイン、およびコネクタを管理します。|MailFlowAdministrator <br/><br/> 組織|
|パスワードのリセット<sup>\*</sup>||問い合わせ <br/><br/> 組織 <br/><br/> 受信者管理|
|保持管理<sup>\*</sup>||ComplianceManagement <br/><br/> 組織 <br/><br/> Ecm.recordsmanagement|
|役割管理|役割グループを作成して管理します。|組織|
|セキュリティ管理者|すべてのセキュリティおよび保護機能の構成とレポートを管理します。|組織 <br/><br/> SecurityAdministrator <br/><br/> Viewonly組織管理|
|セキュリティグループの作成とメンバーシップ|メールが有効なセキュリティグループを作成して管理します。|組織|
|セキュリティ閲覧者|セキュリティおよび保護機能の構成とレポートを表示します。|組織の管理 <br/><br/> SecurityReader <br/><br/> Viewonly組織管理|
|機密ラベル管理者<sup>\*</sup>||組織 <br/><br/> SecurityAdministrator <br/><br/> Viewonly組織管理|
|マネージ<sup>\*</sup>||組織|
|トランスポートの検疫|マルウェア対策、スパム対策機能、およびスプーフィング対策機能を管理します。|HygieneManagement <br/><br/> 組織|
|トランスポート ルール|メールフロールールを作成および管理します (トランスポートルールとも呼ばれます)。|組織 <br/><br/> Ecm.recordsmanagement|
|ユーザーオプション|既存のメールユーザーを変更します。|問い合わせ <br/><br/> 組織|
|表示専用のマルウェア対策|マルウェア対策機能の構成とレポートを表示します。|組織 <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|表示専用スパム対策|スパム対策機能の構成とレポートを表示します。|組織 <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|表示のみの監査ログ|管理者監査ログを検索し、結果を表示します。|ComplianceManagement <br/><br/> 組織 <br/><br/> SecurityAdministrator|
|"View-Only Configuration/表示専用構成"|組織内のすべての組織およびメールフロー (受信者以外) の設定を表示します。|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> 組織 <br/><br/> Viewonly組織管理|
|表示のみの検疫|すべての受信者の検疫済みメッセージをすべて表示します。|組織 <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|"View-Only Recipients/表示専用受信者"|受信者のプロパティを表示し、メッセージの追跡を実行します。|ComplianceManagement <br/><br/> 問い合わせ <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  組織 <br/><br/> Viewonly組織管理|
|表示のみの脅威インテリジェンス<sup>\*</sup>||組織 <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup>この役割は使用できますが、基本的にスタンドアロン EOP では役に立ちません。

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365 のスタンドアロン EOP のアクセス許可

Microsoft 365 管理センターでユーザーを作成する場合、グローバル管理者、サービス管理者、パスワード管理者など、さまざまな管理役割をユーザーに割り当てるかどうかを選択できます。 一部の Microsoft 365 の役割は、EOP でユーザーに管理アクセス許可を付与します。

> [!NOTE]
> スタンドアロンの EOP 組織の作成に使用したアカウントが、グローバル管理者の役割に自動的に割り当てられます。

次の表は、Microsoft 365 の役割と、それらが対応するスタンドアロンの EOP 役割グループを示しています。 これらの役割の詳細については、「[管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)て」を参照してください。

|||
|---|---|
|**Microsoft 365 の役割**|**EOP 役割グループ**|
|Exchange 管理者|組織|
|グローバル管理者|組織 <br/><br/> **注**: グローバル管理者の役割と組織の管理役割グループは、特別な会社の管理者役割グループを使用して関連付けられています。 会社の管理者の役割グループは内部で管理されており、直接変更することはできません。|
|パスワード管理者|問い合わせ|
|グローバル閲覧者|Viewonly組織管理|
|セキュリティ管理者|SecurityAdministrator|
|セキュリティ閲覧者|SecurityReader|
|

その他の Microsoft 365 の役割は、対応する EOP 役割グループを持たず、EOP で管理アクセス許可を付与しません。 Microsoft 365 の役割をユーザーに割り当てる方法については、「[管理者の役割を割り当てる](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles)」を参照してください。

EOP では、ユーザーに Microsoft 365 の役割を追加することなく、管理者権限を与えることができます。 これを行うには、ユーザーを EOP 役割グループのメンバーとして追加します。 ユーザーは EOP でアクセス許可を取得しますが、他の Microsoft 365 ワークロードでアクセス許可を取得することはありません。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

役割グループが正常にコピーされたことを確認するには、次のいずれかの手順を実行します。

- EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、役割グループが表示されている (または一覧に表示されていない) ことを確認します。 役割グループを選択して、詳細ウィンドウで設定を確認するか **、[編集** ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て設定を確認します。

- Exchange Online PowerShell で、役割 \< グループ名を \> 役割グループの名前に置き換え、次のコマンドを実行して役割グループが存在する (または存在しない) ことを確認し、設定を確認します。

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
