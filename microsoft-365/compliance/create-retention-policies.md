---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーを作成して構成する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーを使用すると、コンテンツを保持するか、コンテンツを削除するか、またはその両方かを積極的に決定できます。コンテンツを保持してから削除する、組織全体または特定の場所またはユーザーに単一のポリシーを適用する、すべてのコンテンツまたは特定の条件を満たすコンテンツにポリシーを適用する、などです。
ms.openlocfilehash: 12b0c15186a27a1583403214a657367c1dd3b1a9
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844753"
---
# <a name="create-and-configure-retention-policies"></a>アイテム保持ポリシーを作成して構成する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

アイテム保持ポリシーを使用して、コンテンツを保持するか、コンテンツを削除するか、またはその両方を行う (コンテンツを保持した後に削除する) かを事前に決定すします。 

アイテム保持ポリシーの仕組みについては、「[アイテム保持ポリシーの詳細](retention-policies.md)」をご覧ください。

## <a name="before-you-begin"></a>はじめに

アイテム保持ポリシーを作成して管理するコンプライアンス チームのメンバーには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)へのアクセス許可が必要です。 既定により、テナント管理者 (グローバル管理者) はこの場所にアクセスでき、コンプライアンス責任者やその他のユーザーにテナント管理者のすべての権限を与えることなくアクセスできます。この制限された管理に権限を付与するには、ユーザーを [**コンプライアンス管理者**] の管理者役割グループに追加することをお勧めします。 手順については、「[ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)」を参照してください。

これらのアクセス許可は、アイテム保持ポリシーを作成して適用するためにのみ必要です。 アイテム保持ポリシーを構成するユーザーは、コンテンツへのアクセスを必要としません。

## <a name="create-and-configure-a-retention-policy"></a>アイテム保持ポリシーを作成して構成する

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、[**ポリシー**] > [**保持**] の順に選択します。

2. [**新しいアイテム保持ポリシー**] を選択するか、既存のアイテム保持ポリシーを編集します。

3. [**設定**] では、最初にコンテンツを保持および削除するための構成オプションを指定します。 削除せずにコンテンツを保持するだけのアイテム保持ポリシーを作成し、指定した期間が経過した後に保持してから削除するか、指定した期間が経過した後にコンテンツを削除するだけです。 詳細については、このページの「[コンテンツを保持および削除するための設定](#settings-for-retaining-and-deleting-content)」を参照してください。
    
    次に、アイテム保持ポリシーをすべてのコンテンツに適用するか、特定の条件を満たすコンテンツに適用するかを決定します。 これらの高度な保持設定の詳細については、このページの「[特定の条件を満たすコンテンツを特定するための詳細設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)」をご覧ください。 

4. [**場所の選択**] ページで、アイテム保持ポリシーを組織全体でサポートされているすべての場所に適用するか、場所を指定するかを選択します。 特定の場所を選択した場合は、対象と除外を指定することもできます。 
    
    Microsoft Teams の場合: 
    - Teams のチャネル メッセージまたは Teams のチャットを削除または保持する場合は、特定の場所を選択するオプションを選択する必要があります。 これらのオプションのいずれかを場所として選択すると、この Teams データを含むアイテム保持ポリシーにその他の場所を含めることができないため、その他の場所は自動的に除外されます。 
    - **Teams のチャネル メッセージ**の場合、標準チャネルからのメッセージが含まれますが、[プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels)は含まれません。 プライベート チームからのメッセージは、**Teams のチャット**の場所を選択すると、グループ チャットとしてユーザーに表示されます。
    
    組織または特定の場所のアイテム保持ポリシーを選択する方法の詳細については、このページの「[アイテム保持ポリシーを組織全体または特定の場所に適用する](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」を参照してください。
    
    **Office 365 グループ**および **Skype for Business** に固有の情報については、次のセクション、「[Microsoft 365 グループの構成情報](#configuration-information-for-microsoft-365-groups)」および「[Skype for Business の構成情報](#configuration-information-for-skype-for-business)」を参照してください。

5. ウィザードを完了して、設定を保存します。

アイテム保持ポリシーが複数ある場合は、「[保持の原則、すなわち優先順位について](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)」をご覧ください。

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 グループの構成情報

Microsoft 365 グループ (以前の Office 365 グループ) のコンテンツを保持または削除するには、アイテム保持ポリシーの場所を選択するときに **Office 365 グループ**の場所を選択します。 Microsoft 365 グループには Exchange メールボックスがありますが、**Exchange メール**の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。 また、最初は **Exchange メール**の場所でグループ メールボックスを含めるか除外するかを指定できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では「RemoteGroupMailbox」を選択できないことを示すエラーを受け取ります。

Microsoft 365 グループに適用されるアイテム保持ポリシーには、グループ メールボックスおよびサイトの両方が含まれます。 Microsoft 365 グループに適用されるアイテム保持ポリシーは、Microsoft Teams を含む Microsoft 365 グループによって作成されたリソースを保護します。

### <a name="configuration-information-for-skype-for-business"></a>Skype for Business の構成情報

Exchange メールとは異なり Skype の場所の状態をオンに切り替えてすべてのユーザーを含めることはできませんが、そのロケーションをオンにしてから、会話を保持するユーザーを手動で選択できます。

![アイテム保持ポリシーの Skype の場所を選択する](../media/skype-location-retention-policies.png)
  
[**ユーザーの選択**] を選択すると、列ヘッダーの [**名前**] ボックスを選択して、すべてのユーザーをすばやく含めることができます。 ただし、各ユーザーはポリシーの特定のインクルージョンとしてカウントされることを理解することが重要です。 したがって、1,000 人を超えるユーザーを含める場合は、前のセクションで述べた制限が適用されます。 ここですべての Skype ユーザーを選択することは、組織全体のポリシーに規定ですべての Skype ユーザーを含めることができた場合と同じではありません。 
  
![Skype ユーザーの選択ページ](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.


## <a name="settings-for-retaining-and-deleting-content"></a>コンテンツを保持および削除するための設定

アイテム保持ポリシーでコンテンツを保持および削除するための設定を選択すると、アイテム保持ポリシーは、指定された期間、次のいずれかの構成になります。

- 保持のみ
- 保持してから削除
- 削除のみ

### <a name="retaining-content-for-a-specific-period-of-time"></a>コンテンツを特定の期間保持する

アイテム保持ポリシーを構成するときは、コンテンツを無期限に、または特定の日数、月数、または年数の間保持することを選択します。 コンテンツが保持される期間は、アイテム保持ポリシーが適用された時点からではなくコンテンツの経過時間から計算されます。 経過時間は、コンテンツが作成された日時に基づく場合と、(OneDrive および SharePoint の場合) コンテンツが最後に変更された日時に基づく場合から選択できます。

例:
  
- SharePoint: サイト コレクションのコンテンツを最後に変更してから 7 年間保持する場合に、そのサイト コレクションのドキュメントが 6 年変更されていないと、そのドキュメントが変更されなければあと 1 年間しか保持されません。 そのドキュメントがもう一度編集された場合、ドキュメントの古さは最後に変更された日付から計算され、その後 7 年間保留にされます。
  
- Exchange: メールボックスのコンテンツを 7 年間保持する場合、あるメッセージが 6 年前に送信されているときは、あと 1 年間のみ保持されます。 Exchange コンテンツの場合、経過時間は受信メールの受信日または送信メールの送信日に基づいています。 最終更新日に基づいてコンテンツを保持するポリシーは、OneDrive および SharePoint のコンテンツ サイトにのみ適用されます。
  
保持期間の終了時にコンテンツを完全に削除するかどうかを選択します。
  
![[アイテム保持設定] ページ](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>特定の経過時間を超えた古いコンテンツを削除する

アイテム保持ポリシーは、コンテンツを保持してから削除することも、古いコンテンツを保持せずに削除することもできます。
  
アイテム保持ポリシーによってコンテンツを削除する場合、アイテム保持ポリシーに指定した期間は、ポリシーが割り当てられた時点からではなく、コンテンツが作成または変更された時点から計算されることを理解しておくことが重要です。
  
![[削除の設定]](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
たとえば、保持して 3 年間を過ぎたコンテンツを削除するアイテム保持ポリシーを作成し、それをすべての OneDrive アカウントに割り当てるとします。アカウントには、4 から 5 年前に作成されたコンテンツが数多く含まれています。 このような場合、最初にアイテム保持ポリシーが割り当てられてすぐに、コンテンツの多くが削除されます。 このような理由から、コンテンツを削除するアイテム保持ポリシーは、コンテンツにかなりの影響を与える可能性があることを理解することが重要です。 
  
Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.
  
![コンテンツの削除に関する警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>特定の条件を満たすコンテンツを特定するための詳細設定

アイテム保持ポリシーは、その場所に含まれるすべてのコンテンツに適用することも、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ適用するように選択することもできます。
  
![高度なアイテム保持のオプション](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>特定のキーワードを含むコンテンツを特定する

特定の条件を満たすコンテンツにのみアイテム保持ポリシーを適用し、そのコンテンツだけを保持することができます。 利用できる条件で、特定の単語または語句を含むコンテンツにアイテム保持ポリシーを適用するようになります。 AND、OR、NOT などの検索演算子を使用して、クエリを絞り込むことができます。 このような演算子の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
検索可能なプロパティ (**件名:** など) の追加については間もなくサポートされます。
  
クエリベースの保持では、検索インデックスを使用してコンテンツを識別します。
  
![クエリ エディター](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>機密情報が含まれているコンテンツを特定する

You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.
  
![機密情報の種類のページ](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
注:
  
- 機密情報に対応する高度な保持は、Exchange のパブリック フォルダーや Skype for Business には適用されません (これらの場所が機密情報の種類をサポートしていないため)。
    
- Exchange Online はメール フロー ルール (トランスポート ルールとも呼ばれます) を使用して機密情報を特定するため、既にメールボックスに保存されているすべてのアイテムにではなく、送受信するメッセージにのみ有効です。 つまり、Exchange Online の場合、アイテム保持ポリシーは、ポリシーがメールボックスに適用された**後**に受信したメッセージに対してのみ機密情報を特定して、保持することができます  前のセクションで説明したクエリ ベースの保持では、コンテンツを特定する際に検索インデックスが使用されるため、このような制限がありません。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>アイテム保持ポリシーを組織全体または特定の場所に適用する

アイテム保持ポリシーは、組織全体、場所全体、または特定の場所やユーザーのみに簡単に適用できます。
  
### <a name="org-wide-policy"></a>組織全体のポリシー

アイテム保持ポリシーの強力な機能の 1 つとして、Microsoft 365 全体の場所に適用されます。これには、次の場所が含まれます。
  
- Exchange メール
    
- SharePoint サイト コレクション
    
- OneDrive アカウント
    
- Microsoft 365 グループ (グループのメールボックス、および関連する SharePoint サイトのコンテンツに適用されます)。
    
- Exchange パブリック フォルダー
    

![すべての場所のオプション](../media/retention-policies-all-locations.png)

その他の組織全体のアイテム保持ポリシーに関する重要な機能は、次のとおりです。
  
- ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。
    
- Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。
  
### <a name="a-policy-that-applies-to-entire-locations"></a>場所全体に適用されるポリシー

場所を選択すると、Exchange メールや OneDrive アカウントなど、場所全体を簡単に含めたり除外したりできます。 これを行うには、その場所の [**状態**] をオンまたはオフに切り替えます。 
  
組織全体のポリシーと同様に、場所全体の任意の組み合わせにポリシーが適用される場合、ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。 

たとえば、ポリシーにすべての Exchange メールとすべての SharePoint サイトが含まれている場合、数に関係なくすべてのサイトとメールボックスが含められます。 また、Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>特定の追加または除外を含むポリシー

特定のユーザー、特定の Microsoft 365 グループ、または特定のサイトにアイテム保持ポリシーを適用することもできます。 そのためには、目的の場所の [**状態**] をオンに切り替えた上で、リンクを使用して特定のユーザー、Microsoft 365 グループ、またはサイトを含めたり除外したりします。 
  
ただし、この設定を使用すると、保持ポリシーに 1,000 を超える特定の場所が含まれている場合、または除外される場合、いくつかの制限があります。
  
- アイテム保持ポリシーの最大数:
    - 1,000 個のメールボックス
    - 1,000 個の Microsoft 365 グループ
    - Teams のプライベート チャットのユーザー 1,000 人
    - 100 個のサイト (OneDrive または SharePoint)

テナントでサポートされるポリシーの最大数は 10,000 です。 これらのアイテムには、アイテム保持ポリシー、保持ラベル ポリシー、および自動適用アイテム保持ポリシーが含まれます。

アイテム保持ポリシーがこれらの制限の影響を受ける可能性がある場合は、場所全体に適用される構成オプションを選択するか、組織全体のポリシーを使用します。

## <a name="updating-retention-policies"></a>アイテム保持ポリシーの更新

アイテム保持ポリシーを編集し、コンテンツが既にアイテム保持ポリシーの元の設定の対象となっている場合、更新された設定は、新しく特定されたコンテンツに加えて、このコンテンツに自動的に適用されます。

通常、この更新はかなり迅速ですが、数日かかる場合があります。 Microsoft 365 の場所間でのポリシーの複製が完了すると、Microsoft 365 コンプライアンス センターの保持ポリシーの状態が [**On (保留中)**] から [**オン (成功)**] に変わります。

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>アイテム保持ポリシーの PowerShell コマンドレットを検索する

アイテム保持ポリシーのコマンドレットを使用するには:
  
1. [Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a>PowerShell を使用してアイテム保持ポリシーをロックする

規制要件に準拠するために [[保持ロック](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)] を使用する必要がある場合は、PowerShell を使用する必要があります。

1. [Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. アイテム保持ポリシーを一覧表示し、`Get-RetentionCompliancePolicy` を実行してロックするポリシーの名前を検索します。
    
    ![PowerShell のアイテム保持ポリシーの一覧](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. アイテム保持ポリシーに [保持ロック] を設定するには `Set-RetentionCompliancePolicy` を実行しますが、その際に `RestrictiveRetention` パラメーターを true に設定する必要があります。 以下に例を示します。
    
        Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
    
    ![PowerShell の RestrictiveRetention パラメーター](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    そのコマンドレットを実行した後、[**すべてはい**]を選択します。
    
    ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

アイテム保持ポリシーに保持ロックが設定されました。 `Get-RetentionCompliancePolicy`を実行すると、`RestrictiveRetention`パラメーターは true に設定されます。 次に例を示します。

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

