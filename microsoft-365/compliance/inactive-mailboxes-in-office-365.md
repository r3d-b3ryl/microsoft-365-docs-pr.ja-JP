---
title: 非アクティブなメールボックスの詳細情報
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: メールボックスを非アクティブなメールボックスにすることで、元従業員のメールボックス コンテンツを保持する方法について説明します。
ms.openlocfilehash: 9043c71118b00638d8671063c623ada7dcf25bcd
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359189"
---
# <a name="learn-about-inactive-mailboxes"></a>非アクティブなメールボックスの詳細情報

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

組織では、退職後も元従業員の電子メールを保持しなければならないことがあります。 組織が定める保存要件に応じて、メールボックスの内容を、雇用が終了してから数か月、数年、または無期限に保持しなければならないことがあります。 メールを保持する必要がある期間に関係なく、非アクティブなメールボックスを作成して、元従業員のメールボックスを保持できます。 

## <a name="what-are-inactive-mailboxes"></a>非アクティブなメールボックスとは

従業員が組織を離れる (または長期休暇に入る) 場合は、Microsoft 365 アカウントを削除できます。 従業員のメールボックス データは、アカウントが削除されてから 30 日間保持されます。 この期間中も、アカウントを削除してメールボックス データを回復できます。 30 日後、データは完全に削除されます。

ただし、Microsoft 365 アカウントを削除する前にメールボックスに保留が適用されている場合、メールボックスは非アクティブなメールボックスに変換されます。 次のセクションには、Microsoft 365 の保有期間と電子情報開示の保留に適用できる保留に関する情報が含まれています。

非アクティブなメールボックスは、組織が規制やその他の理由で元従業員のメールボックス コンテンツを保持する必要がある場合に役立ちます。 このドキュメントに記載されている任意の種類の保留は、ユーザー オブジェクトが削除されたときにメールボックスを強制的に非アクティブにしますが、Microsoft 365 アイテム保持ポリシーまたは保持ラベルを適用し、 [保留が適用されていることを確認](#confirming-a-hold-is-applied-to-a-mailbox)してから、対応する Microsoft 365 アカウントを削除することをお勧めします。 その時点で、非アクティブなメールボックスの内容は、ユーザー アカウントが削除される前に指定された保持期間にわたって保持されます。 対応するユーザー アカウントは引き続き 30 日間回復できますが、30 日後は、アイテム保持ポリシーまたはアイテム保持ラベルが削除されるまで、メールボックスは非アクティブなメールボックスとして Microsoft 365 に保持されます。

> [!IMPORTANT]
> 前述のように、Microsoft 365 リテンション期間を使用して非アクティブなメールボックスを作成することをお勧めします。
> - Exchange 管理センターのIn-Place保留は廃止されました。 2020 年 7 月 1 日の時点で、Exchange Onlineで新しいIn-Place保留を作成できませんでした。 2020 年 10 月 1 日以降、インプレース ホールドの保留期間は変更できませんでした。 In-Place保留が適用されている非アクティブなメールボックスは、In-Place保留を削除することによってのみ削除できます。 In-Place保留になっている既存の非アクティブなメールボックスは、保留が削除されるまで引き続き保持されます。 In-Place保留の詳細については、「 [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
> 
> - [訴訟ホールド](create-a-litigation-hold.md) は、メールボックス内のコンテンツを保持し、ユーザー アカウントが削除された後に非アクティブにする代替方法として引き続きサポートされます。 ただし、古いテクノロジとして、代わりに Microsoft 365 リテンション期間を使用することをお勧めします。

同じコンテンツに対して複数の保留がある場合、 [保持の原則が適用](retention.md#the-principles-of-retention-or-what-takes-precedence) され、コンテンツは最長期間保持されます。

### <a name="confirming-a-hold-is-applied-to-a-mailbox"></a>メールボックスに保留が適用されていることを確認する

Microsoft 365 アイテム保持ポリシー、アイテム保持ラベル、電子情報開示ホールド、訴訟ホールドを適用する場合でも、既存のIn-Placeホールドがある場合でも、PowerShell を使用してメールボックスにホールドが正常に適用されていることを確認できます。 ホールドを最近構成した場合は、メールボックスに適用されるまで待つ必要がある場合があります。

偶発的または意図しない削除を防ぐために、ユーザー アカウントを削除する前に保留を確認することをお勧めします。 保留が適用されていない場合、メールボックスは非アクティブなメールボックスに変換されません。

手順については、「[Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。

## <a name="inactive-mailboxes-and-microsoft-365-retention"></a>非アクティブなメールボックスと Microsoft 365 リテンション期間

Microsoft 365 アイテム保持ポリシーがメールボックスに適用されている場合、またはメールボックス内の 1 つ以上のメール アイテムに保持ラベルが適用され、Microsoft 365 ユーザー アカウントが削除された場合、メールボックスは非アクティブなメールボックスに変換されます。 非アクティブなメールボックスを作成する場合:

- 保持設定は、 [コンテンツを保持するか、コンテンツを保持して削除するように](retention-settings.md#settings-for-retaining-and-deleting-content)構成する必要があります。 アイテム保持アクションがコンテンツのみを削除するように構成されている場合、ユーザー アカウントが削除されてもメールボックスは非アクティブになりません。 非アクティブなメールボックスの場合は、保持してから削除するオプションを使用することをお勧めします。

- 保持設定は、Exchange メールボックスに関連付けられている [保持場所](retention-settings.md#locations) に適用する必要があります。
    - Exchange メール
    - Microsoft 365 グループ
    - Skype for Business
    - Exchange パブリック フォルダー
    - チームのチャネル メッセージ
    - Teams のチャット
    - Teams の非公開チャネル メッセージ
    - Yammer コミュニティのメッセージ
    - Yammer ユーザーのメッセージ

Microsoft リテンション期間の詳細については、「 [アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。

Microsoft 365 アイテム保持を使用して非アクティブなメールボックスを作成する場合、アイテム保持ポリシーまたはアイテム保持ラベルの保持設定は引き続き非アクティブなメールボックスに適用されます。 つまり、アイテム保持設定がコンテンツを保持して削除するように構成されている場合、アイテムは保持期間が経過すると回復可能なアイテム フォルダーに移動され、最終的に非アクティブなメールボックスから削除されます。 アイテム保持設定が削除済みアイテムに構成されていない場合、(メールボックスが非アクティブになる前に) ユーザーによって完全に削除されていないアイテムは回復可能なアイテム フォルダーに移動されず、メールボックスが非アクティブになった後も無期限に保持されます。

> [!TIP]
> *ComplianceTagHoldApplied* プロパティを使用して、1 つ以上のアイテム保持ラベルが適用されているアイテムをメールボックスに保持するか、保持してから削除するかを識別できます。 詳細については、「 [アイテム保持ラベルがフォルダーまたはアイテムに適用されているため、保留中のメールボックスを識別する」を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)。

### <a name="using-adaptive-policy-scopes-to-manage-retention-of-inactive-mailboxes"></a>アダプティブ ポリシー スコープを使用して非アクティブなメールボックスのリテンション期間を管理する

[アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)を使用すると、特に非アクティブなメールボックスに保持設定を適用できます。 この構成の利点は次のとおりです。

- アクティブな従業員と元従業員に対して異なる保有期間を必要とする組織の規制またはポリシーを満たすことができます。

- 元従業員に対する組織の要件を満たすために必要な限り、メールボックスのコンテンツを保持するように保持設定を構成できます。

- 組織内の非アクティブなメールボックスに割り当てられているリテンション期間のポリシーをすばやく特定できるため、必要に応じて保持設定を簡単に変更できます。 

- 非アクティブなメールボックスの属性またはプロパティに基づいて、除外する [アダプティブ スコープを構成](retention-settings.md#to-configure-an-adaptive-scope) することで、非アクティブなメールボックスをポリシーから削除できるため、非アクティブなメールボックスを完全に削除する方が簡単です。 それ以外の場合は、メールボックス[を削除する前Exchange Online PowerShell](delete-an-inactive-mailbox.md#remove-an-inactive-mailbox-from-a-retention-policy) [を使用する](delete-an-inactive-mailbox.md#before-you-delete-an-inactive-mailbox)必要があります。

> [!NOTE]
> アダプティブ ポリシー スコープの構成によっては、非アクティブなメールボックスが含まれる場合と含まれていない場合があります。  アダプティブ ポリシー スコープから非アクティブなメールボックスを具体的にターゲットにしたり、除外したりするには、 [Exchange 電子メールと Exchange パブリック フォルダーの構成情報](retention-settings.md#locations)を参照してください。

### <a name="using-static-policy-scopes-and-inactive-mailboxes"></a>静的ポリシー スコープと非アクティブなメールボックスの使用

Microsoft 365 リテンション期間で [アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention) を使用せず、代わりに [静的スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)を使用する場合は、次の点を考慮してください。

- 既定の **すべての受信者** 構成を使用する場合、静的ポリシー スコープには非アクティブなメールボックスが含まれますが、[特定の包含または除外](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions)ではサポートされていません。 ただし、ポリシーの適用時にアクティブなメールボックスを持つ受信者を含めたり除外したりして、後でメールボックスが非アクティブになった場合、保持設定は引き続き適用または除外されます。 このシナリオでは、 [特定の包含と除外の制限](retention-limits.md) が引き続き適用されます。
    
    > [!NOTE]
    > また、すべての **受信者** の既定の選択に適用される静的スコープを使用する新しい Microsoft 365 保持設定には、既存のすべての非アクティブなメールボックスが自動的に含まれます。

- **[すべての受信者]** の既定の選択を変更して特定の受信者を含める場合、ポリシーの保持設定は非アクティブなメールボックスには適用されなくなり、自動削除の対象になります。

- 非アクティブなメールボックスに適用されているアイテム保持ポリシーを解放する場合は、「 [アイテム保持用のポリシーを解放する](retention.md#releasing-a-policy-for-retention)」を参照してください。

> [!CAUTION]
> Microsoft 365 リテンション期間を使用してメールボックスを非アクティブにする場合は、対応するユーザー アカウントを削除する前に、メールボックスのユーザー プリンシパル名 (UPN) を変更または削除しないでください。 また、メールボックスを非アクティブにする前に、プライマリ SMTP アドレス (UPN から派生) を変更したり、メールボックスに関連付けられているセカンダリ SMTP アドレスの一覧からこの電子メール アドレスを削除したりしないでください。
> 
> UPN または電子メール アドレス (保持設定が適用された時点でメールボックスに割り当てられたもの) を変更し、ユーザー アカウントを削除してメールボックスを非アクティブにした場合、保持する必要がなくなった場合は、非アクティブなメールボックスを削除することはできません。 これは、保持設定がメールボックスに最初に適用されたときとは異なる UPN または電子メール アドレス (非アクティブなメールボックスを識別するため) を使用して、ポリシーから非アクティブなメールボックスを削除できないためです。 非アクティブなメールボックスの削除の詳細については、「[Office 365で非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)」を参照してください。

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>非アクティブなメールボックスと電子情報開示のケース保持

Microsoft Purview コンプライアンス ポータルの[電子情報開示ケース](./get-started-core-ediscovery.md)に関連付けられているホールドがメールボックスに配置され、メールボックスまたはユーザーのアカウントが削除された場合、メールボックスは非アクティブなメールボックスになります。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. また、時間ベースの電子情報開示ホールドを作成することはできません。 つまり、非アクティブなメールボックス内のコンテンツは、保持が削除されて非アクティブなメールボックスが削除されるまで、永続的に保持されます。 そのため、非アクティブなメールボックスには Microsoft 365 リテンション期間を使用することをお勧めします。

電子情報開示の保持と Microsoft 365 リテンション期間の違いの詳細については、「 [アイテム保持ポリシーと保持ラベルまたは電子情報開示保留をいつ使用](retention.md#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)するか」を参照してください。

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>非アクティブなメールボックスと自動展開アーカイブ

自動展開アーカイブを使用して構成された非アクティブなメールボックスは、回復または復元できません。 自動展開アーカイブを使用して非アクティブなメールボックスからデータを回復する必要がある場合は、コンテンツ検索ツールを使用してメールボックスからデータをエクスポートしてから別のメールボックスにインポートすることをお勧めします。 非アクティブなメールボックスを検索し、検索結果をエクスポートする手順については、次を参照してください。

- [コンテンツ検索](content-search.md)

- [コンテンツ検索結果をエクスポートする](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非アクティブなメールボックスと Exchange MRM アイテム保持ポリシー

Exchange アイテム保持ポリシー (Exchange Onlineのメッセージング レコード管理または MRM 機能) を適用しても、ユーザー アカウントが削除されたときに非アクティブなメールボックスは作成されません。

ただし、この MRM アイテム保持ポリシーが非アクティブになる前にメールボックスに適用された場合、削除ポリシー ( **削除** アクションで構成された MRM 保持タグ) は、非アクティブなメールボックスで引き続き処理されます。 つまり、MRM 削除ポリシーでタグ付けされたアイテムは、保持期間の有効期限が切れると [、回復可能なアイテム フォルダー](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) に移動されます。 それらのアイテムは保持期間を過ぎると非アクティブなメールボックスから消去されます。 非アクティブなメールボックスの保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは無期限に保持されます。

逆に、非アクティブなメールボックスに割り当てられている MRM アイテム保持ポリシーに含まれるアーカイブ ポリシー ( **MoveToArchive** アクションで構成された MRM リテンション タグ) は無視されます。 つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。 それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。 無期限に保持されます。

## <a name="next-steps"></a>次の手順

メールボックスを非アクティブにして、回復、復元、削除などの管理を行うには、「 [非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
